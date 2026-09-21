# Computer Vision Learning Guide (Beginner → Confident)

> A hands-on, one-file guide to Computer Vision with **Python + OpenCV**, finishing with **CNNs, YOLO and Vision Transformers**.
> Every topic follows the same rhythm: **Concept → Code → What happens → Try it yourself → Check yourself.**

---

## How to Use This Guide

| Step | What to do |
|------|-----------|
| 1 | Read the concept (short, plain English) |
| 2 | Copy the code into a `.py` file or a Jupyter/VS Code notebook and **run it** |
| 3 | Do the **Try it yourself** challenge (change a number, see what breaks) |
| 4 | Open the **Check yourself** dropdown only after you've answered in your head |
| 5 | Tick the progress box at the end of each section |

**Recommended pace:** 1 section per day → about 3 weeks. Sections 1–14 are the *foundation*; 15–22 are the *AI-powered* part.

---

## Table of Contents

**Part A – Foundations**
1. [What is Computer Vision?](#1-what-is-computer-vision)
2. [The Big Picture: The CV Pipeline](#2-the-big-picture-the-cv-pipeline)
3. [Setup](#3-setup)
4. [How Images Work (Pixels, Channels, BGR)](#4-how-images-work-pixels-channels-bgr)
5. [Read, Show, Save an Image](#5-read-show-save-an-image)
6. [Grayscale & Color Spaces](#6-grayscale--color-spaces)
7. [Resize, Crop, Rotate, Flip](#7-resize-crop-rotate-flip)
8. [Drawing Shapes & Text](#8-drawing-shapes--text)
9. [Blur & Noise Removal](#9-blur--noise-removal)
10. [Thresholding](#10-thresholding)
11. [Morphological Operations](#11-morphological-operations)
12. [Edge Detection](#12-edge-detection)
13. [Contours](#13-contours)
14. [Histograms & Contrast](#14-histograms--contrast)

**Part B – Video & Classic Detection**
15. [Color Detection with HSV](#15-color-detection-with-hsv)
16. [Webcam & Video](#16-webcam--video)
17. [Face Detection (Haar Cascade)](#17-face-detection-haar-cascade)
18. [Feature Matching & Template Matching](#18-feature-matching--template-matching)

**Part C – Deep Learning for Vision**
19. [Normalization & Preprocessing for AI Models](#19-normalization--preprocessing-for-ai-models)
20. [CNN – Image Classification](#20-cnn--image-classification)
21. [Object Detection with YOLO](#21-object-detection-with-yolo)
22. [Segmentation & Vision Transformers](#22-segmentation--vision-transformers)

**Part D – Practice**
23. [Mini Projects](#23-mini-projects)
24. [Common Errors & Fixes](#24-common-errors--fixes)
25. [Final Quiz](#25-final-quiz)
26. [Cheat Sheet](#26-cheat-sheet)
27. [Learning Roadmap & Repo Structure](#27-learning-roadmap--repo-structure)

---

# PART A — FOUNDATIONS

---

## 1. What is Computer Vision?

**Computer Vision (CV)** = teaching computers to *understand* images and video.

A human looks at a photo and instantly says *"a cat on a sofa."* A computer sees only a **grid of numbers**. CV is the bridge between those numbers and meaning.

### Real-world examples

| Area | Example |
|------|---------|
| Phone | Face unlock, portrait mode, QR scanning |
| Automotive | Lane detection, pedestrian detection |
| Healthcare | Finding tumours in X-rays |
| Retail | Cashier-less stores, shelf monitoring |
| Industry | Defect detection on assembly lines |
| Agriculture | Crop disease detection from drone images |
| Security | Face recognition, number-plate reading (ANPR) |

### Main CV tasks (you will meet all of these)

```
Classification  →  "What is in this image?"          → cat
Detection       →  "What and WHERE?"                  → cat + box
Segmentation    →  "Which pixels belong to what?"     → cat-shaped mask
Tracking        →  "Follow that object over time"     → same cat, frame 1→100
Recognition     →  "WHO is this?"                     → face → Alice
OCR             →  "What text is written?"            → "STOP"
```

**Progress:** `[ ]` I can explain CV in one sentence.

---

## 2. The Big Picture: The CV Pipeline

Almost every CV project follows this flow. Keep this diagram in your head — the rest of the guide is just zooming into each box.

```
        Camera / Image
              |
              ▼
      OpenCV (Read Image)
              |
           Resize
              |
     Grayscale (Optional)
              |
        Noise Removal
              |
  Edge Detection / Face Detection
              |
          Normalize
              ▼
   CNN / YOLO / Vision Transformer
              |
          Prediction
              ▼
            Output
```

### Two worlds of CV

| | Classic CV | Deep Learning CV |
|---|---|---|
| Tools | OpenCV functions | CNN, YOLO, ViT |
| Needs training data? | No | Yes (or a pretrained model) |
| Good for | Simple, controlled problems | Complex, real-world problems |
| Example | Detect a red ball | Detect 80 kinds of objects |
| This guide | Sections 4–18 | Sections 19–22 |

> **Key idea:** Classic steps (resize, blur, grayscale…) are used **to prepare** an image so the AI model performs better.

**Progress:** `[ ]` I can name at least 5 boxes in the pipeline in order.

<details>
<summary>Check yourself: Why do we remove noise <em>before</em> detecting edges?</summary>

Noise creates thousands of tiny fake "edges". Blurring first keeps only the real, strong edges.
</details>

---

## 3. Setup

This guide uses **[uv](https://docs.astral.sh/uv/)** for Python and package management. It creates the virtual environment for you, so there is no manual activate step.

### Step 1 – Create the project

```bash
uv init computer-vision-learning
cd computer-vision-learning
```

This creates `pyproject.toml`, `.python-version` and a starter `main.py`. (Already inside an existing folder? Run `uv init` there instead.)

### Step 2 – Add libraries

```bash
uv add opencv-python numpy matplotlib

# For notebooks (VS Code / Jupyter):
uv add ipykernel

# Needed later (Part C):
uv add torch torchvision ultralytics transformers pillow
```

`uv add` installs the package into the project's `.venv` and records it in `pyproject.toml` and `uv.lock`.

> Use `opencv-python`, not `opencv-python-headless`. The headless build has no GUI support, so `cv2.imshow` will not work.

### Step 3 – Verify

```python
import cv2
import numpy as np

print("OpenCV version:", cv2.__version__)
print("NumPy version :", np.__version__)
```

Run it with uv (no need to activate anything):

```bash
uv run python check.py
```

> **Notebooks in VS Code:** open the `.ipynb`, click *Select Kernel*, and choose the `.venv` inside your project folder.

### Step 4 – Get a test image

Save any photo as `cat.jpg` in your project folder (all examples use this name).

### Notebook vs Script — important!

| Environment | How to show an image |
|-------------|----------------------|
| Python script (`.py`) | `cv2.imshow()` + `cv2.waitKey(0)` |
| Jupyter / Colab / VS Code notebook | `matplotlib.pyplot.imshow()` (convert BGR→RGB first) |

Reusable helper for notebooks — paste it once at the top:

```python
import cv2
import matplotlib.pyplot as plt

def show(img, title="Image", cmap=None):
    """Display any OpenCV image correctly inside a notebook."""
    if len(img.shape) == 3:                       # colour image
        img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    plt.figure(figsize=(6, 6))
    plt.imshow(img, cmap=cmap or (None if len(img.shape) == 3 else "gray"))
    plt.title(title)
    plt.axis("off")
    plt.show()
```

**Progress:** `[ ]` `cv2.__version__` prints without errors.

---

## 4. How Images Work (Pixels, Channels, BGR)

### An image is just a NumPy array of numbers

A **pixel** = one tiny square of the image. Its value is a number from **0 (black) to 255 (white)**.

**Grayscale image** → 2D grid (height × width):

```
 0   50  100 200        0 = black
 30  80  150 220      255 = white
 60 120  180 255
```

**Colour image** → 3D grid (height × width × 3 channels):

```
Pixel = [ Blue, Green, Red ]     ← OpenCV uses BGR, NOT RGB!

[255,   0,   0] = pure Blue
[  0, 255,   0] = pure Green
[  0,   0, 255] = pure Red
[  0,   0,   0] = Black
[255, 255, 255] = White
```

### Inspect an image

```python
import cv2

image = cv2.imread("cat.jpg")

print(type(image))        # <class 'numpy.ndarray'>
print(image.shape)        # (height, width, channels) e.g. (480, 640, 3)
print(image.dtype)        # uint8  → values 0..255
print(image.size)         # total number of values
print(image[100, 50])     # BGR value of the pixel at row=100, col=50
```

### The 3 biggest beginner confusions

| Confusion | Truth |
|-----------|-------|
| "Is it RGB?" | OpenCV loads **BGR**. Matplotlib expects **RGB**. Convert with `cv2.cvtColor(img, cv2.COLOR_BGR2RGB)`. |
| "Is shape (width, height)?" | `img.shape` = **(height, width, channels)**. |
| "Is pixel access `[x, y]`?" | It is **`[row, col]` = `[y, x]`**. |

### Try it yourself
1. Print `image.shape` of your photo. What are the height and width?
2. Set the top-left 100×100 block to pure red: `image[0:100, 0:100] = (0, 0, 255)` then display it.

<details>
<summary>Check yourself: What does shape <code>(480, 640, 3)</code> mean?</summary>

480 pixels tall, 640 pixels wide, 3 colour channels (B, G, R). Total pixels = 480 × 640 = 307,200.
</details>

**Progress:** `[ ]` I know OpenCV = BGR and shape = (H, W, C).

---

## 5. Read, Show, Save an Image

### 1. Read an Image

```python
import cv2

image = cv2.imread("cat.jpg")

cv2.imshow("Image", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**What each line does**

| Line | Meaning |
|------|---------|
| `cv2.imread("cat.jpg")` | Loads the file into a NumPy array |
| `cv2.imshow("Image", image)` | Opens a window titled "Image" |
| `cv2.waitKey(0)` | Waits **forever** for any key press (window stays open) |
| `cv2.destroyAllWindows()` | Closes all windows |

> Without `waitKey`, the window flashes and disappears instantly.

### Read modes

```python
img_color = cv2.imread("cat.jpg", cv2.IMREAD_COLOR)       # default, BGR
img_gray  = cv2.imread("cat.jpg", cv2.IMREAD_GRAYSCALE)   # loads directly as gray
img_alpha = cv2.imread("logo.png", cv2.IMREAD_UNCHANGED)  # keeps transparency
```

### Save an image

```python
cv2.imwrite("cat_copy.png", image)   # format decided by the extension
```

### Always check that the image loaded

`imread` does **not** raise an error if the file is missing — it silently returns `None`.

```python
image = cv2.imread("cat.jpg")
if image is None:
    raise FileNotFoundError("Could not load cat.jpg — check path & spelling")
```

### Try it yourself
Load the image as grayscale using `IMREAD_GRAYSCALE`, print its `.shape`, and compare with the colour version. What changed?

<details>
<summary>Check yourself</summary>

The colour shape is `(H, W, 3)`; the gray shape is `(H, W)` — the channel dimension disappears.
</details>

**Progress:** `[ ]` I can read, show and save an image.

---

## 6. Grayscale & Color Spaces

### 2. Convert to Grayscale

```python
import cv2

image = cv2.imread("cat.jpg")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

cv2.imshow("Gray", gray)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Why grayscale?**
- 3 channels → 1 channel = **3× less data**, faster processing
- Many algorithms (edges, faces, thresholds) only need **brightness**, not colour
- It's *optional* — skip it when colour matters (e.g., detecting a red ball)

### Other colour spaces

| Space | Channels | Best for |
|-------|----------|----------|
| **BGR/RGB** | Blue, Green, Red | Display, storage |
| **Gray** | Brightness | Edges, faces, thresholding |
| **HSV** | Hue, Saturation, Value | **Colour detection** (see Section 15) |
| **LAB** | Lightness, a, b | Colour correction |

```python
hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
lab = cv2.cvtColor(image, cv2.COLOR_BGR2LAB)
rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```

### Split & merge channels

```python
b, g, r = cv2.split(image)
merged  = cv2.merge([b, g, r])
```

### Try it yourself
Display only the **red** channel. Bright areas = lots of red. Which parts of your photo are brightest?

**Progress:** `[ ]` I can convert BGR → Gray / HSV / RGB.

---

## 7. Resize, Crop, Rotate, Flip

### 3. Resize an Image

```python
import cv2

image = cv2.imread("cat.jpg")

image = cv2.resize(image, (224, 224))

cv2.imshow("Resized", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

> `cv2.resize` takes **(width, height)** — the opposite order of `shape`!

**Why resize?** Neural networks need a **fixed input size** (e.g., 224×224 for many CNNs, 640×640 for YOLO). Smaller images also run faster.

### Resize by scale factor (keeps things proportional)

```python
half = cv2.resize(image, None, fx=0.5, fy=0.5)
```

### Interpolation (how new pixels are computed)

| Flag | Use when |
|------|----------|
| `cv2.INTER_AREA` | **Shrinking** (best quality) |
| `cv2.INTER_LINEAR` | Default, general purpose |
| `cv2.INTER_CUBIC` | **Enlarging** (slower, smoother) |

```python
small = cv2.resize(image, (100, 100), interpolation=cv2.INTER_AREA)
```

### Keep the aspect ratio (avoid squashed images)

```python
def resize_keep_ratio(img, new_width):
    h, w = img.shape[:2]
    ratio = new_width / w
    return cv2.resize(img, (new_width, int(h * ratio)))
```

### Crop (it's just NumPy slicing!)

```python
# image[y1:y2, x1:x2]
crop = image[50:250, 100:300]
```

### Rotate & Flip

```python
# Flip: 1 = horizontal, 0 = vertical, -1 = both
flipped = cv2.flip(image, 1)

# Rotate 90°
rotated90 = cv2.rotate(image, cv2.ROTATE_90_CLOCKWISE)

# Rotate by any angle around the centre
h, w = image.shape[:2]
M = cv2.getRotationMatrix2D((w // 2, h // 2), 45, 1.0)   # centre, angle, scale
rotated = cv2.warpAffine(image, M, (w, h))
```

### Try it yourself
Crop only the cat's face using slicing. Tip: guess coordinates, view, adjust.

<details>
<summary>Check yourself: Which is correct for an image 300 tall × 500 wide → 100 tall × 200 wide?</summary>

`cv2.resize(img, (200, 100))` — width first, then height.
</details>

**Progress:** `[ ]` I can resize, crop, rotate and flip.

---

## 8. Drawing Shapes & Text

### 6. Draw a Rectangle

```python
import cv2

image = cv2.imread("cat.jpg")

cv2.rectangle(image, (50, 50), (250, 250), (0, 255, 0), 2)

cv2.imshow("Rectangle", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Reading the arguments**

```
cv2.rectangle( image, (50, 50), (250, 250), (0, 255, 0), 2 )
                 │       │          │           │        │
              target   top-left  bottom-right  colour   thickness
              image    (x, y)       (x, y)     (B,G,R)   (px)
```

> Thickness `-1` fills the shape. Drawing **modifies the original image**, so use `image.copy()` if you want to keep it clean.

### More drawing tools

```python
canvas = image.copy()

cv2.circle(canvas, (150, 150), 60, (0, 0, 255), 3)                 # centre, radius
cv2.line(canvas, (0, 0), (300, 300), (255, 0, 0), 2)               # start, end
cv2.putText(canvas, "Cat!", (50, 40),
            cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)       # text, org, font, scale, colour, thickness
cv2.rectangle(canvas, (300, 100), (400, 200), (0, 255, 255), -1)   # filled
```

> **Why this matters:** every object detector (YOLO, face detection) shows results by **drawing rectangles + labels** on the image — exactly this code.

### Try it yourself
Draw a box with a label `"Face"` just above it, like a real detector.

**Progress:** `[ ]` I can draw a labelled bounding box.

---

## 9. Blur & Noise Removal

### 4. Blur an Image

```python
import cv2

image = cv2.imread("cat.jpg")

blur = cv2.GaussianBlur(image, (5, 5), 0)

cv2.imshow("Blur", blur)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**How blurring works:** a small window (the **kernel**) slides over the image. Each pixel is replaced by a weighted average of its neighbours → sharp noise smooths out.

```
Kernel (5,5) slides →   [ · · · · · ]
                        [ · · · · · ]
                        [ · · X · · ]  ← pixel replaced by average of its neighbours
                        [ · · · · · ]
                        [ · · · · · ]
```

### Types of blur — pick the right tool

| Function | Best for | Example |
|----------|----------|---------|
| `cv2.blur` | Simple average | `cv2.blur(img, (5,5))` |
| `cv2.GaussianBlur` | **General noise removal** | `cv2.GaussianBlur(img, (5,5), 0)` |
| `cv2.medianBlur` | **Salt-and-pepper noise** (white/black dots) | `cv2.medianBlur(img, 5)` |
| `cv2.bilateralFilter` | Smooth **but keep edges sharp** | `cv2.bilateralFilter(img, 9, 75, 75)` |

### Rules
- Kernel size **must be odd**: 3, 5, 7, 9…
- **Bigger kernel = more blur** (and more lost detail)

### Try it yourself
Blur with kernel sizes (3,3), (15,15), (51,51). At what size does the cat become unrecognisable?

<details>
<summary>Check yourself: Which blur removes white/black speckles best?</summary>

`cv2.medianBlur` — it picks the median value, ignoring extreme outliers.
</details>

**Progress:** `[ ]` I know 4 blur types and when to use each.

---

## 10. Thresholding

**Thresholding** turns a grayscale image into pure **black & white** (binary): *is each pixel brighter than a cut-off?*

```python
import cv2

gray = cv2.imread("cat.jpg", cv2.IMREAD_GRAYSCALE)

# pixel > 127 → 255 (white) else 0 (black)
_, binary = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

# Otsu: OpenCV picks the best threshold automatically
_, otsu = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Adaptive: different threshold for each region (great for uneven lighting)
adaptive = cv2.adaptiveThreshold(gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                 cv2.THRESH_BINARY, 11, 2)
```

| Method | Use when |
|--------|----------|
| `THRESH_BINARY` | Lighting is even, you know the cut-off |
| `THRESH_OTSU` | You don't know the cut-off |
| `adaptiveThreshold` | Shadows / uneven lighting (e.g., scanned documents) |

### Try it yourself
Photograph a page of text under a lamp. Compare global vs. adaptive threshold — which reads better?

**Progress:** `[ ]` I can create a binary image.

---

## 11. Morphological Operations

Operations on **binary** images that clean shapes. They use a **kernel** just like blur.

```python
import cv2
import numpy as np

kernel = np.ones((5, 5), np.uint8)

erosion  = cv2.erode(binary, kernel, iterations=1)             # shrinks white areas
dilation = cv2.dilate(binary, kernel, iterations=1)            # grows white areas
opening  = cv2.morphologyEx(binary, cv2.MORPH_OPEN, kernel)    # erode → dilate
closing  = cv2.morphologyEx(binary, cv2.MORPH_CLOSE, kernel)   # dilate → erode
```

| Operation | Effect | Use |
|-----------|--------|-----|
| **Erosion** | Shrinks white, removes tiny specks | Remove noise |
| **Dilation** | Grows white | Fill gaps, join broken parts |
| **Opening** | Erode then dilate | Remove small white noise |
| **Closing** | Dilate then erode | Fill small black holes |

**Progress:** `[ ]` I can clean a binary mask.

---

## 12. Edge Detection

**Edges** = places where brightness changes sharply — the outlines of objects.

```python
import cv2

image = cv2.imread("cat.jpg")
gray  = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
blur  = cv2.GaussianBlur(gray, (5, 5), 0)          # remove noise first!

edges = cv2.Canny(blur, 100, 200)                   # low, high threshold

cv2.imshow("Edges", edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### How Canny thresholds work

```
gradient > 200 (high)  → definitely an edge
gradient < 100 (low)   → definitely NOT an edge
between 100 and 200    → edge only if connected to a strong edge
```

### Sobel (direction-aware edges)

```python
sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)   # vertical edges
sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)   # horizontal edges
```

### Try it yourself
Run Canny with thresholds (50,100), (100,200), (200,300). Which shows the most detail? Which the cleanest?

<details>
<summary>Check yourself: Why blur before Canny?</summary>

Noise pixels look like tiny edges. Blur removes them so Canny finds only real outlines.
</details>

**Progress:** `[ ]` I can extract edges with Canny.

---

## 13. Contours

A **contour** = a curve joining all continuous boundary points of a shape. It lets you **find, count and measure** objects.

```python
import cv2

image = cv2.imread("shapes.png")
gray  = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
blur  = cv2.GaussianBlur(gray, (5, 5), 0)
_, thresh = cv2.threshold(blur, 0, 255, cv2.THRESH_BINARY_INV + cv2.THRESH_OTSU)

contours, _ = cv2.findContours(thresh, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
print("Objects found:", len(contours))

for c in contours:
    area = cv2.contourArea(c)
    if area < 100:            # skip tiny noise
        continue
    x, y, w, h = cv2.boundingRect(c)
    cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)
    cv2.putText(image, f"{int(area)}", (x, y - 5),
                cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 0, 255), 1)

cv2.imshow("Contours", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

> Pipeline used here: **Grayscale → Blur → Threshold → Contours → Draw** — a classic mini-pipeline you'll reuse often.

### Try it yourself
Draw coins on a plain paper, photograph them, and **count** them automatically.

**Progress:** `[ ]` I can count objects in an image.

---

## 14. Histograms & Contrast

A **histogram** shows how many pixels exist at each brightness (0–255). It tells you if an image is dark, bright or low-contrast.

```python
import cv2
import matplotlib.pyplot as plt

gray = cv2.imread("cat.jpg", cv2.IMREAD_GRAYSCALE)

plt.hist(gray.ravel(), bins=256, range=(0, 256))
plt.title("Brightness histogram")
plt.show()

# Improve contrast
equalized = cv2.equalizeHist(gray)

# Better for uneven lighting: CLAHE
clahe = cv2.createCLAHE(clipLimit=2.0, tileGridSize=(8, 8))
enhanced = clahe.apply(gray)
```

```
Dark image:   ██████░░░░░░░░░░   (values bunched on the left)
Bright image: ░░░░░░░░░░██████   (values bunched on the right)
Good image:   ░░███████████░░░   (spread out)
```

### Brightness & contrast quick tweak

```python
bright = cv2.convertScaleAbs(image, alpha=1.2, beta=30)   # alpha = contrast, beta = brightness
```

**Progress:** `[ ]` I can read a histogram and boost contrast.

---

# PART B — VIDEO & CLASSIC DETECTION

---

## 15. Color Detection with HSV

**Why HSV?** In BGR, "red" changes with lighting in all 3 channels. In HSV, colour is one number (**Hue**), so detection is far easier.

```
H = Hue        → the colour itself (0–179 in OpenCV)
S = Saturation → how vivid (0 = gray, 255 = pure colour)
V = Value      → brightness (0 = black, 255 = bright)
```

```python
import cv2
import numpy as np

image = cv2.imread("cat.jpg")
hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)

# Detect BLUE
lower = np.array([100, 150, 50])
upper = np.array([130, 255, 255])

mask   = cv2.inRange(hsv, lower, upper)           # white where colour matches
result = cv2.bitwise_and(image, image, mask=mask) # keep only matching pixels

cv2.imshow("Mask", mask)
cv2.imshow("Result", result)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Approximate Hue ranges (OpenCV: 0–179)

| Colour | Hue range |
|--------|-----------|
| Red | 0–10 **and** 170–179 (wraps around!) |
| Orange | 10–25 |
| Yellow | 25–35 |
| Green | 35–85 |
| Blue | 100–130 |
| Purple | 130–160 |

### Try it yourself
Hold a coloured object in front of your webcam (combine with Section 16) and draw a box around it.

**Progress:** `[ ]` I can isolate a colour from an image.

---

## 16. Webcam & Video

### 7. Webcam Capture

```python
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    cv2.imshow("Webcam", frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

**Line by line**

| Code | Meaning |
|------|---------|
| `cv2.VideoCapture(0)` | Open camera #0 (default webcam). Use a filename for a video file |
| `cap.read()` | Grab **one frame**. `ret` = success flag, `frame` = the image |
| `cv2.waitKey(1)` | Wait 1 ms for a key → keeps the video flowing |
| `& 0xFF == ord('q')` | Was the pressed key `q`? → then stop |
| `cap.release()` | Free the camera (**always do this!**) |

> **Key insight:** video = **a fast loop of images**. Everything you learned for one image works on every frame.

### Safer version (checks `ret`)

```python
import cv2

cap = cv2.VideoCapture(0)
if not cap.isOpened():
    raise RuntimeError("Cannot open camera")

while True:
    ret, frame = cap.read()
    if not ret:
        print("No frame received — exiting")
        break

    gray  = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    edges = cv2.Canny(gray, 100, 200)          # apply ANY operation per frame

    cv2.imshow("Webcam", frame)
    cv2.imshow("Edges", edges)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### Read a video file & save output

```python
cap = cv2.VideoCapture("video.mp4")

w   = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH))
h   = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT))
fps = cap.get(cv2.CAP_PROP_FPS) or 30

out = cv2.VideoWriter("output.mp4", cv2.VideoWriter_fourcc(*"mp4v"), fps, (w, h))

while True:
    ret, frame = cap.read()
    if not ret:
        break
    out.write(frame)

cap.release()
out.release()
```

### Show FPS (speed) on screen

```python
import time
prev = time.time()
# inside the loop:
now = time.time()
fps = 1 / (now - prev)
prev = now
cv2.putText(frame, f"FPS: {fps:.1f}", (10, 30),
            cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 255, 0), 2)
```

### Try it yourself
Add `frame = cv2.flip(frame, 1)` right after `cap.read()` to make a mirror view.

<details>
<summary>Check yourself: What does <code>waitKey(0)</code> vs <code>waitKey(1)</code> do?</summary>

`0` = wait forever (good for still images). `1` = wait 1 ms then continue (needed for video loops).
</details>

**Progress:** `[ ]` I can process live webcam frames.

---

## 17. Face Detection (Haar Cascade)

A **Haar Cascade** is a classic, fast, pre-trained detector that ships **inside OpenCV** — no download needed.

```python
import cv2

face_cascade = cv2.CascadeClassifier(
    cv2.data.haarcascades + "haarcascade_frontalface_default.xml"
)

image = cv2.imread("people.jpg")
gray  = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)      # cascades work on gray

faces = face_cascade.detectMultiScale(
    gray,
    scaleFactor=1.1,     # how much the image shrinks each pass
    minNeighbors=5,      # higher = fewer false positives
    minSize=(30, 30)     # ignore tiny detections
)

print("Faces found:", len(faces))

for (x, y, w, h) in faces:
    cv2.rectangle(image, (x, y), (x + w, y + h), (0, 255, 0), 2)

cv2.imshow("Faces", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Live face detection on webcam

```python
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    if not ret:
        break
    gray  = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    faces = face_cascade.detectMultiScale(gray, 1.1, 5)
    for (x, y, w, h) in faces:
        cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 2)
    cv2.imshow("Face Detection", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

### Haar vs modern detectors

| | Haar Cascade | DNN / MediaPipe / YOLO-face |
|---|---|---|
| Speed | Very fast on CPU | Fast |
| Accuracy | Okay (front-facing only) | Much better (angles, lighting) |
| Setup | Built into OpenCV | Extra install |

> **Detection ≠ Recognition.** Detection = *"there is a face here."* Recognition = *"this face is Alice."*

**Progress:** `[ ]` I can detect faces in an image and live video.

---

## 18. Feature Matching & Template Matching

### Template matching — find a small image inside a big one

```python
import cv2

scene    = cv2.imread("scene.jpg")
template = cv2.imread("template.jpg")
h, w     = template.shape[:2]

result = cv2.matchTemplate(scene, template, cv2.TM_CCOEFF_NORMED)
_, max_val, _, max_loc = cv2.minMaxLoc(result)

if max_val > 0.8:
    cv2.rectangle(scene, max_loc, (max_loc[0] + w, max_loc[1] + h), (0, 255, 0), 2)

cv2.imshow("Match", scene)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

Works only if size & rotation are the same. For robust matching use **features**.

### Feature matching with ORB (rotation & scale tolerant)

```python
import cv2

img1 = cv2.imread("book.jpg", cv2.IMREAD_GRAYSCALE)
img2 = cv2.imread("scene.jpg", cv2.IMREAD_GRAYSCALE)

orb = cv2.ORB_create(1000)
kp1, des1 = orb.detectAndCompute(img1, None)
kp2, des2 = orb.detectAndCompute(img2, None)

bf = cv2.BFMatcher(cv2.NORM_HAMMING, crossCheck=True)
matches = sorted(bf.match(des1, des2), key=lambda m: m.distance)

out = cv2.drawMatches(img1, kp1, img2, kp2, matches[:30], None, flags=2)
cv2.imshow("ORB Matches", out)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Keypoints** = distinctive spots (corners, blobs). **Descriptors** = numeric "fingerprints" of those spots. Matching descriptors = finding the same object.

**Progress:** `[ ]` I understand keypoints & descriptors.

---

# PART C — DEEP LEARNING FOR VISION

---

## 19. Normalization & Preprocessing for AI Models

Neural networks expect images in a **specific format**. The pipeline's *Resize → Normalize* steps prepare that.

```python
import cv2
import numpy as np

image = cv2.imread("cat.jpg")

# 1. Resize to model's expected size
image = cv2.resize(image, (224, 224))

# 2. BGR → RGB  (most models were trained on RGB!)
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# 3. Scale 0–255 → 0–1
image = image.astype(np.float32) / 255.0

# 4. (Optional) standardise with ImageNet mean/std
mean = np.array([0.485, 0.456, 0.406], dtype=np.float32)
std  = np.array([0.229, 0.224, 0.225], dtype=np.float32)
image = (image - mean) / std

# 5. Height×Width×Channel → Channel×Height×Width, add batch dimension
image = np.transpose(image, (2, 0, 1))      # (3, 224, 224)
image = np.expand_dims(image, axis=0)       # (1, 3, 224, 224)

print(image.shape)
```

| Step | Why |
|------|-----|
| Resize | Fixed input size |
| BGR→RGB | Models expect RGB |
| ÷ 255 | Small numbers train/predict better |
| Mean/Std | Matches how the model was trained |
| Transpose | PyTorch wants `C×H×W` |
| Batch dim | Models process *batches*, even a batch of 1 |

> **#1 silent bug in CV projects:** forgetting BGR→RGB or using different normalization than training. The model still runs — it just gives poor results.

**Progress:** `[ ]` I can turn an OpenCV image into a model-ready tensor.

<details>
<summary>Check yourself: What shape does a batch of 8 RGB 224×224 images have in PyTorch?</summary>

`(8, 3, 224, 224)` → (batch, channels, height, width).
</details>

---

## 20. CNN – Image Classification

### What is a CNN?

A **Convolutional Neural Network** learns filters automatically. Early layers find **edges**, middle layers find **shapes/textures**, deep layers find **objects**.

```
Input Image
    │
    ▼
[ Conv + ReLU ] → learns edges
    │
[ Pooling ]     → shrinks size, keeps key info
    │
[ Conv + ReLU ] → learns shapes
    │
[ Pooling ]
    │
[ Flatten ]
    │
[ Dense layers ] → combine features
    │
[ Softmax ]      → probabilities
    ▼
"cat: 94%"  "dog: 5%"  "car: 1%"
```

| Layer | Job |
|-------|-----|
| **Convolution** | Slides small filters to detect patterns |
| **ReLU** | Adds non-linearity (negative → 0) |
| **Pooling** | Downsamples; adds tolerance to small shifts |
| **Fully connected** | Makes the final decision |
| **Softmax** | Converts scores to probabilities (sum = 1) |

### Use a pretrained CNN in ~15 lines (PyTorch)

```python
import torch
from torchvision import models
from torchvision.models import ResNet18_Weights
from PIL import Image

weights = ResNet18_Weights.DEFAULT
model   = models.resnet18(weights=weights)
model.eval()

preprocess = weights.transforms()                  # resize + normalise, done for you
img   = Image.open("cat.jpg").convert("RGB")
batch = preprocess(img).unsqueeze(0)

with torch.no_grad():
    probs = torch.softmax(model(batch)[0], dim=0)

top3 = torch.topk(probs, 3)
for p, idx in zip(top3.values, top3.indices):
    print(f"{weights.meta['categories'][idx]:<25} {p.item()*100:.1f}%")
```

### Build a tiny CNN from scratch (learning purpose)

```python
import torch.nn as nn

class TinyCNN(nn.Module):
    def __init__(self, num_classes=10):
        super().__init__()
        self.features = nn.Sequential(
            nn.Conv2d(3, 16, 3, padding=1), nn.ReLU(), nn.MaxPool2d(2),   # 32→16
            nn.Conv2d(16, 32, 3, padding=1), nn.ReLU(), nn.MaxPool2d(2),  # 16→8
        )
        self.classifier = nn.Sequential(
            nn.Flatten(),
            nn.Linear(32 * 8 * 8, 64), nn.ReLU(),
            nn.Linear(64, num_classes),
        )

    def forward(self, x):
        return self.classifier(self.features(x))
```

(Input assumed 32×32 RGB, e.g. CIFAR-10.)

### Transfer learning — the beginner's superpower

Don't train from zero. Take a pretrained model, **replace the last layer**, and train only that on your small dataset.

```python
import torch.nn as nn
from torchvision import models

model = models.resnet18(weights="DEFAULT")
for p in model.parameters():
    p.requires_grad = False                   # freeze the backbone

model.fc = nn.Linear(model.fc.in_features, 3) # e.g. 3 custom classes
```

### Beginner glossary

| Term | Meaning |
|------|---------|
| **Epoch** | One full pass over the training data |
| **Batch** | Group of images processed at once |
| **Loss** | How wrong the model is (lower = better) |
| **Overfitting** | Memorises training data, fails on new data |
| **Augmentation** | Random flips/rotations to create more training variety |
| **Train / Val / Test** | Learn / tune / final honest score |

**Progress:** `[ ]` I ran a pretrained classifier on my own image.

<details>
<summary>Check yourself: Why use transfer learning?</summary>

It needs far less data and time, because the backbone has already learned general visual features (edges, textures, shapes) from millions of images.
</details>

---

## 21. Object Detection with YOLO

**YOLO = "You Only Look Once."** It finds **many objects at once** and returns, for each: **class + confidence + bounding box**.

```
Classification: "cat"
Detection:      "cat at [x1,y1,x2,y2] with 92% confidence" + "dog at [...]"
```

### Run YOLO in 5 lines

```bash
uv add ultralytics
```

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")           # 'n' = nano (smallest, fastest). Auto-downloads.
results = model("cat.jpg")

results[0].show()                    # display
results[0].save("yolo_output.jpg")   # save
```

### Read the results yourself

```python
for r in results:
    for box in r.boxes:
        x1, y1, x2, y2 = map(int, box.xyxy[0])
        conf  = float(box.conf[0])
        label = model.names[int(box.cls[0])]
        print(f"{label}: {conf:.2f} at ({x1},{y1},{x2},{y2})")
```

### YOLO + OpenCV webcam (real-time detection)

```python
import cv2
from ultralytics import YOLO

model = YOLO("yolov8n.pt")
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break

    results   = model(frame, verbose=False)
    annotated = results[0].plot()          # draws boxes + labels for you

    cv2.imshow("YOLO Webcam", annotated)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### Key detection concepts

| Term | Meaning |
|------|---------|
| **Bounding box** | Rectangle around an object |
| **Confidence** | How sure the model is (0–1) |
| **NMS** (Non-Max Suppression) | Removes duplicate overlapping boxes |
| **IoU** (Intersection over Union) | Overlap score between two boxes (1 = perfect) |
| **mAP** | Standard accuracy score for detectors |

```
IoU = Area of overlap / Area of union
```

### Train YOLO on your own data (outline)

1. Collect images → label them (Roboflow, LabelImg, CVAT)
2. Organise into `train/` and `val/` with a `data.yaml`
3. Train:
   ```python
   model = YOLO("yolov8n.pt")
   model.train(data="data.yaml", epochs=50, imgsz=640)
   ```
4. Evaluate with `model.val()`, then run predictions on new images

**Progress:** `[ ]` I ran YOLO on an image and on my webcam.

---

## 22. Segmentation & Vision Transformers

### Segmentation — pixel-level understanding

| Type | Output |
|------|--------|
| **Semantic** | Every pixel gets a class (all "person" pixels are one colour) |
| **Instance** | Each object gets its own mask (person 1, person 2 …) |
| **Panoptic** | Semantic + Instance combined |

```python
from ultralytics import YOLO

model = YOLO("yolov8n-seg.pt")       # segmentation version
results = model("people.jpg")
results[0].show()
```

Popular models: **U-Net** (medical), **Mask R-CNN**, **YOLO-seg**, **SAM (Segment Anything)**.

### Vision Transformers (ViT)

Instead of sliding filters, ViT **cuts the image into patches** and lets them "pay attention" to each other.

```
Image → split into 16×16 patches → flatten each → add position info
      → Transformer encoder (self-attention) → class prediction
```

| | CNN | Vision Transformer |
|---|---|---|
| Looks at | Local neighbourhoods first | Whole image relationships |
| Data needs | Works with less | Needs more data (or pretraining) |
| Strength | Efficient, great baseline | State-of-the-art at scale |
| Examples | ResNet, EfficientNet | ViT, DINOv2, CLIP, SAM |

### Quick ViT usage (Hugging Face)

```bash
uv add transformers
```

```python
from transformers import pipeline

classifier = pipeline("image-classification", model="google/vit-base-patch16-224")
print(classifier("cat.jpg")[:3])
```

### Choosing the right tool

```
"What is this image?"            → Classification (ResNet / ViT)
"What & where?"                  → Detection (YOLO)
"Exact outline / pixels?"        → Segmentation (YOLO-seg / SAM / U-Net)
"Who is it?"                     → Face recognition (embeddings)
"Read the text"                  → OCR (Tesseract / EasyOCR)
"Describe in words / search"     → Vision-language models (CLIP, multimodal LLMs)
```

**Progress:** `[ ]` I can pick the right task type for a problem.

---

# PART D — PRACTICE

---

## 23. Mini Projects

| # | Project | Skills used | Level |
|---|---------|-------------|-------|
| 1 | **Photo Editor** — grayscale / blur / edges / flip with keypress | Sections 5–9, 16 | Easy |
| 2 | **Document Scanner** — detect page, flatten perspective, threshold | 10, 12, 13 | Medium |
| 3 | **Colour Tracker** — follow a coloured ball on webcam | 15, 16 | Easy |
| 4 | **Coin / Object Counter** | 9, 10, 13 | Easy |
| 5 | **Face Detector + Blur Faces** (privacy filter) | 9, 17 | Medium |
| 6 | **Motion Detector** — frame differencing | 6, 9, 10, 16 | Medium |
| 7 | **Cat/Dog Classifier** with transfer learning | 19, 20 | Medium |
| 8 | **Real-time Object Detector** with YOLO | 21 | Medium |
| 9 | **Emotion / Expression Recognition** | 17, 19, 20 | Hard |
| 10 | **Custom YOLO** on your own labelled dataset | 21 | Hard |

### Starter: Motion detector (Project 6)

```python
import cv2

cap = cv2.VideoCapture(0)
_, prev = cap.read()
prev = cv2.GaussianBlur(cv2.cvtColor(prev, cv2.COLOR_BGR2GRAY), (21, 21), 0)

while True:
    ret, frame = cap.read()
    if not ret:
        break

    gray = cv2.GaussianBlur(cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY), (21, 21), 0)
    diff = cv2.absdiff(prev, gray)                        # what changed?
    _, thresh = cv2.threshold(diff, 25, 255, cv2.THRESH_BINARY)
    thresh = cv2.dilate(thresh, None, iterations=2)

    contours, _ = cv2.findContours(thresh, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
    for c in contours:
        if cv2.contourArea(c) > 800:
            x, y, w, h = cv2.boundingRect(c)
            cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 2)

    prev = gray
    cv2.imshow("Motion", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

### Starter: Blur every face (Project 5)

```python
import cv2

face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    for (x, y, w, h) in face_cascade.detectMultiScale(gray, 1.1, 5):
        face = frame[y:y + h, x:x + w]
        frame[y:y + h, x:x + w] = cv2.GaussianBlur(face, (51, 51), 0)
    cv2.imshow("Privacy Filter", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

---

## 24. Common Errors & Fixes

| Error / Symptom | Cause | Fix |
|-----------------|-------|-----|
| `AttributeError: 'NoneType' object has no attribute 'shape'` | `imread` couldn't find the file | Check path, extension, working directory |
| `error: (-215:Assertion failed) !_src.empty()` | Empty image passed to a function | Same as above; also check webcam `ret` |
| Window opens then vanishes | Missing `waitKey` | Add `cv2.waitKey(0)` |
| Window freezes / "Not Responding" | Missing `waitKey(1)` in loop | Add it inside the `while` loop |
| Colours look wrong (blue skin!) | BGR shown as RGB in matplotlib | `cv2.cvtColor(img, cv2.COLOR_BGR2RGB)` |
| Resize gives a squashed image | Wrong (w, h) order or ignoring aspect ratio | Use `(width, height)`; keep ratio |
| `cv2.imshow` crashes in Jupyter/Colab | GUI not supported | Use `matplotlib` or `cv2_imshow` (Colab) |
| Webcam won't open | Wrong index / app already using it | Try `VideoCapture(1)`, close other apps |
| Kernel size error in blur | Even number kernel | Use odd sizes (3, 5, 7…) |
| Model gives poor predictions | Wrong colour order or normalization | Match the training preprocessing exactly |
| Drawn shape ruins the original | Drawing is in-place | Work on `image.copy()` |
| Slow processing | Big images / heavy models | Resize first, use smaller models, GPU |

---

## 25. Final Quiz

Test yourself — answers are hidden.

**Q1.** What colour order does OpenCV use by default?
<details><summary>Answer</summary>BGR.</details>

**Q2.** What does `img.shape` return for a colour image?
<details><summary>Answer</summary>`(height, width, channels)`.</details>

**Q3.** Which function takes `(width, height)`: `img.shape` or `cv2.resize`?
<details><summary>Answer</summary>`cv2.resize`.</details>

**Q4.** Why do we blur before Canny edge detection?
<details><summary>Answer</summary>To remove noise that would create false edges.</details>

**Q5.** Which colour space is best for detecting a specific colour?
<details><summary>Answer</summary>HSV.</details>

**Q6.** What does `cap.read()` return?
<details><summary>Answer</summary>A tuple `(ret, frame)` — success flag and the image.</details>

**Q7.** Difference between face *detection* and face *recognition*?
<details><summary>Answer</summary>Detection finds where faces are; recognition identifies who the face belongs to.</details>

**Q8.** What does IoU measure?
<details><summary>Answer</summary>Overlap between two boxes: intersection area ÷ union area.</details>

**Q9.** Why must images be normalised before feeding a neural network?
<details><summary>Answer</summary>Models are trained on a specific value range/distribution; matching it gives correct, stable predictions.</details>

**Q10.** Which task gives pixel-level masks: classification, detection or segmentation?
<details><summary>Answer</summary>Segmentation.</details>

**Scoring:** 9–10 ready for projects · 6–8 review weak sections · ≤5 re-read Part A.

---

## 26. Cheat Sheet

```python
# ── I/O ──────────────────────────────────────────────
img = cv2.imread("f.jpg")                 # read
cv2.imwrite("out.jpg", img)               # save
cv2.imshow("win", img); cv2.waitKey(0); cv2.destroyAllWindows()

# ── Basic ops ────────────────────────────────────────
gray   = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
hsv    = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
rgb    = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
small  = cv2.resize(img, (224, 224))              # (w, h)
crop   = img[y1:y2, x1:x2]
flip   = cv2.flip(img, 1)

# ── Filtering ────────────────────────────────────────
blur   = cv2.GaussianBlur(img, (5, 5), 0)
median = cv2.medianBlur(img, 5)
edges  = cv2.Canny(gray, 100, 200)
_, bw  = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

# ── Drawing ──────────────────────────────────────────
cv2.rectangle(img, (x1, y1), (x2, y2), (0, 255, 0), 2)
cv2.circle(img, (cx, cy), r, (0, 0, 255), 2)
cv2.putText(img, "txt", (x, y), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)

# ── Video ────────────────────────────────────────────
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cap.release()

# ── Detection helpers ────────────────────────────────
mask = cv2.inRange(hsv, lower, upper)
contours, _ = cv2.findContours(bw, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
```

### Pipeline memory trick

> **R**ead → **R**esize → **G**ray → **B**lur → **D**etect → **N**ormalize → **P**redict
> *"Really Ready Girls Bake Dark Nutty Pies"*

---

## 27. Learning Roadmap & Repo Structure

### 3-Week Roadmap

| Week | Focus | Goal |
|------|-------|------|
| **1** | Sections 3–9 | Read, transform, draw, blur — build the Photo Editor |
| **2** | Sections 10–18 | Threshold, edges, contours, HSV, webcam, faces — build Colour Tracker + Face Blur |
| **3** | Sections 19–22 | Preprocess, classify, YOLO — build a Real-time Detector |
| **After** | Mini Projects 9–10 | Emotion recognition, custom-trained YOLO |

### Suggested GitHub repo layout

```
computer-vision-learning/
│
├── README.md                     ← this guide
├── pyproject.toml                ← dependencies (managed by uv)
├── uv.lock                       ← exact locked versions
├── .python-version
├── images/                       ← sample images (cat.jpg, people.jpg …)
│
├── 01_basics/
│   ├── 01_read_show_save.py
│   ├── 02_grayscale_colorspaces.py
│   ├── 03_resize_crop_rotate.py
│   ├── 04_drawing.py
│   └── 05_blur_noise.py
│
├── 02_processing/
│   ├── 06_threshold.py
│   ├── 07_morphology.py
│   ├── 08_edges.py
│   ├── 09_contours.py
│   └── 10_histograms.py
│
├── 03_video/
│   ├── 11_hsv_color_detection.py
│   ├── 12_webcam.py
│   ├── 13_face_detection.py
│   └── 14_feature_matching.py
│
├── 04_deep_learning/
│   ├── 15_preprocessing.py
│   ├── 16_cnn_pretrained.py
│   ├── 17_transfer_learning.ipynb
│   ├── 18_yolo_detection.py
│   └── 19_segmentation.py
│
└── projects/
    ├── photo_editor/
    ├── colour_tracker/
    ├── face_blur/
    ├── motion_detector/
    └── realtime_yolo/
```

`pyproject.toml` (created by `uv init`, filled in by `uv add`)

```toml
[project]
name = "computer-vision-learning"
version = "0.1.0"
requires-python = ">=3.10"
dependencies = [
    "opencv-python",
    "numpy",
    "matplotlib",
    "ipykernel",
    "torch",
    "torchvision",
    "ultralytics",
    "transformers",
    "pillow",
]
```

**Everyday uv commands**

```bash
uv sync                          # recreate the exact environment on a new machine
uv run python 01_basics/01_read_show_save.py   # run any script in the project env
uv add <package>                 # add a dependency
uv remove <package>              # remove a dependency
```

### Where to go next

- **OpenCV docs & tutorials:** https://docs.opencv.org/
- **PyTorch vision tutorials:** https://pytorch.org/vision/
- **Ultralytics YOLO docs:** https://docs.ultralytics.com/
- **Datasets:** COCO, ImageNet, CIFAR-10, Open Images, Roboflow Universe
- **Book:** *Computer Vision: Algorithms and Applications* — Richard Szeliski (free online)
- **Course:** Stanford CS231n (CNNs for Visual Recognition)

---

## You Made It!

You now understand the **full CV journey**:

```
Pixels → Filters → Edges & Shapes → Video → Faces → CNN → YOLO → Transformers
```

**Golden rules to remember**
1. An image is just numbers — inspect `shape` and `dtype` when confused.
2. Always check `imread` / `cap.read()` succeeded.
3. Preprocessing decides model quality — match training preprocessing exactly.
4. Start simple (classic OpenCV), then add deep learning only where needed.
5. Build projects — you learn CV by *breaking and fixing* code.

*Happy learning — now go build something that sees!*
