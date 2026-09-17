# Computer Vision from Zero to Advanced

_A complete, single-file version of the full learning repo — every README and every code sample, in order._


---


# Overview / README


> File: `README.md`

# Computer Vision from Zero to Advanced

A hands-on, beginner-friendly Computer Vision curriculum with **runnable sample code** for every concept — from reading your first image with OpenCV all the way to YOLO object detection, image segmentation, Vision Transformers, tracking, 3D vision, and deployment.

Every folder is a self-contained module: a `README.md` explains the theory in plain language, and numbered scripts let you *run and see* what each concept actually does.

> 💡 **How to use this repo:** Go in order (01 → 10). Each module builds on the last. Don't skip the READMEs — the code makes a lot more sense once you know *why* the technique exists.

---

## Learning Path

| # | Module | What you'll learn |
|---|--------|--------------------|
| 01 | [Basics](01_basics/) | Reading/writing images, color spaces, transformations, thresholding, filtering, edges, morphology, histograms |
| 02 | [Intermediate](02_intermediate/) | Contours, feature detection (SIFT/ORB), template matching, watershed segmentation, optical flow, camera calibration |
| 03 | [Classical ML for Vision](03_classical_ml/) | HOG + SVM, Haar Cascades, K-Means color segmentation |
| 04 | [Deep Learning Basics](04_deep_learning_basics/) | CNNs from scratch (PyTorch), transfer learning, data augmentation, custom datasets |
| 05 | [Object Detection](05_object_detection/) | Sliding window, R-CNN family, **YOLO (v5–v8) — theory + inference + custom training**, real-time webcam detection |
| 06 | [Segmentation](06_segmentation/) | Semantic segmentation (U-Net), instance segmentation (Mask R-CNN), YOLOv8-seg, Segment Anything (SAM) |
| 07 | [Advanced Architectures](07_advanced_architectures/) | Vision Transformers (ViT), GANs, Autoencoders for anomaly detection, CLIP zero-shot classification |
| 08 | [Tracking & Video](08_tracking_and_video/) | OpenCV trackers, DeepSORT + YOLO multi-object tracking, pose estimation (MediaPipe) |
| 09 | [3D & Depth](09_3d_and_depth/) | Stereo depth estimation, monocular depth (MiDaS), point clouds |
| 10 | [Deployment](10_deployment/) | Exporting to ONNX, serving a model with Flask, building a Streamlit CV app |
| | [Projects](projects/) | End-to-end mini projects combining multiple techniques |

---

## Setup

```bash
git clone <your-repo-url>
cd cv-learning-repo
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Each module may also list extra optional dependencies in its own README (e.g. `ultralytics` for YOLO, `mediapipe` for pose estimation) — install them only when you reach that module so your environment stays light.

Most scripts accept an image/video path as an argument and fall back to a sample or your webcam if none is given. Read the top comment of each file before running it.

---

## 🧭 Suggested Pace

- **Week 1–2:** Modules 01–02 (core OpenCV toolbox)
- **Week 3:** Module 03 (classical ML — understand what came before deep learning)
- **Week 4–5:** Module 04 (deep learning fundamentals)
- **Week 6–7:** Module 05 (object detection + YOLO deep dive)
- **Week 8:** Module 06 (segmentation)
- **Week 9:** Module 07 (advanced architectures)
- **Week 10:** Modules 08–09 (video, tracking, 3D)
- **Week 11:** Module 10 + projects (ship something real)

See [LEARNING_PATH.md](LEARNING_PATH.md) for a topic-by-topic checklist you can tick off.

---

## 📁 Repo Structure

```
cv-learning-repo/
├── 01_basics/
├── 02_intermediate/
├── 03_classical_ml/
├── 04_deep_learning_basics/
├── 05_object_detection/      ⭐ YOLO lives here
├── 06_segmentation/
├── 07_advanced_architectures/
├── 08_tracking_and_video/
├── 09_3d_and_depth/
├── 10_deployment/
├── projects/
├── requirements.txt
├── LEARNING_PATH.md
└── README.md
```

## 🤝 Contributing
Found a bug or want to add a technique? PRs welcome — keep the beginner-first, one-concept-per-file philosophy.

## 📜 License
MIT — use freely for learning, teaching, or building on top of.




# Learning Path Checklist


> File: `LEARNING_PATH.md`

# Learning Path Checklist

Tick these off as you go. Each item links to the file that teaches/demonstrates it.

## Module 01 — Basics
- [ ] Reading, displaying, writing images/video — `01_basics/01_image_read_write.py`
- [ ] Color spaces (BGR, RGB, HSV, Gray) — `01_basics/02_color_spaces.py`
- [ ] Resizing, cropping, rotation, flipping, translation — `01_basics/03_image_transformations.py`
- [ ] Thresholding (binary, Otsu, adaptive) — `01_basics/04_thresholding.py`
- [ ] Blurring/filtering (Gaussian, median, bilateral) — `01_basics/05_filtering_blurring.py`
- [ ] Edge detection (Sobel, Canny, Laplacian) — `01_basics/06_edge_detection.py`
- [ ] Morphological ops (erode, dilate, open, close) — `01_basics/07_morphological_operations.py`
- [ ] Histograms & equalization (incl. CLAHE) — `01_basics/08_histogram_equalization.py`

## Module 02 — Intermediate
- [ ] Contours & shape analysis — `02_intermediate/01_contours.py`
- [ ] Feature detection: SIFT, ORB, keypoint matching — `02_intermediate/02_feature_detection_sift_orb.py`
- [ ] Template matching — `02_intermediate/03_template_matching.py`
- [ ] Watershed segmentation — `02_intermediate/04_image_segmentation_watershed.py`
- [ ] Optical flow (Lucas-Kanade, Farneback) — `02_intermediate/05_optical_flow.py`
- [ ] Camera calibration & distortion correction — `02_intermediate/06_camera_calibration.py`

## Module 03 — Classical ML
- [ ] HOG features + Linear SVM classifier — `03_classical_ml/01_hog_svm_classifier.py`
- [ ] Haar Cascade face/eye detection — `03_classical_ml/02_haar_cascade_face_detection.py`
- [ ] K-Means color-based segmentation — `03_classical_ml/03_kmeans_color_segmentation.py`

## Module 04 — Deep Learning Basics
- [ ] CNN from scratch in PyTorch — `04_deep_learning_basics/01_cnn_from_scratch_pytorch.py`
- [ ] Transfer learning (ResNet fine-tuning) — `04_deep_learning_basics/02_transfer_learning_resnet.py`
- [ ] Data augmentation techniques — `04_deep_learning_basics/03_data_augmentation.py`
- [ ] Custom Dataset & DataLoader — `04_deep_learning_basics/04_custom_dataset_dataloader.py`

## Module 05 — Object Detection (incl. YOLO)
- [ ] Sliding window detector (first principles) — `05_object_detection/01_sliding_window_detection.py`
- [ ] R-CNN → Fast R-CNN → Faster R-CNN explained — `05_object_detection/02_rcnn_family_explained.md`
- [ ] How YOLO actually works (grid, anchors, loss) — `05_object_detection/03_yolo_explained.md`
- [ ] YOLOv8 inference on images/video — `05_object_detection/04_yolov8_inference.py`
- [ ] Training YOLOv8 on a custom dataset — `05_object_detection/05_yolov8_custom_training.py`
- [ ] Real-time webcam YOLO detection — `05_object_detection/06_yolo_realtime_webcam.py`
- [ ] Faster R-CNN via torchvision — `05_object_detection/07_faster_rcnn_torchvision.py`

## Module 06 — Segmentation
- [ ] Semantic segmentation with U-Net — `06_segmentation/01_unet_semantic_segmentation.py`
- [ ] Instance segmentation with Mask R-CNN — `06_segmentation/02_mask_rcnn_instance_segmentation.py`
- [ ] YOLOv8-seg (instance segmentation) — `06_segmentation/03_yolov8_segmentation.py`
- [ ] Segment Anything Model (SAM) — `06_segmentation/04_segment_anything_sam.py`

## Module 07 — Advanced Architectures
- [ ] Vision Transformer (ViT) image classification — `07_advanced_architectures/01_vision_transformer_vit.py`
- [ ] GAN for image generation (DCGAN) — `07_advanced_architectures/02_dcgan_image_generation.py`
- [ ] Autoencoder for anomaly detection — `07_advanced_architectures/03_autoencoder_anomaly_detection.py`
- [ ] CLIP zero-shot image classification — `07_advanced_architectures/04_clip_zero_shot_classification.py`
- [ ] Diffusion models explained — `07_advanced_architectures/05_diffusion_models_explained.md`

## Module 08 — Tracking & Video
- [ ] Built-in OpenCV trackers (CSRT, KCF) — `08_tracking_and_video/01_opencv_object_tracking.py`
- [ ] Multi-object tracking: YOLO + DeepSORT — `08_tracking_and_video/02_yolo_deepsort_tracking.py`
- [ ] Pose estimation with MediaPipe — `08_tracking_and_video/03_pose_estimation_mediapipe.py`

## Module 09 — 3D & Depth
- [ ] Stereo depth estimation — `09_3d_and_depth/01_stereo_depth_estimation.py`
- [ ] Monocular depth estimation (MiDaS) — `09_3d_and_depth/02_monocular_depth_midas.py`

## Module 10 — Deployment
- [ ] Export a model to ONNX + run inference — `10_deployment/01_onnx_export_inference.py`
- [ ] Serve a CV model with Flask — `10_deployment/02_flask_api_deployment.py`
- [ ] Build an interactive Streamlit CV app — `10_deployment/03_streamlit_cv_app.py`

## Projects
- [ ] Real-time face & eye detector — `projects/face_eye_realtime_detector/`
- [ ] People counting with YOLO + tracking — `projects/people_counting_yolo/`




# requirements.txt


```text
# Core
numpy
matplotlib
opencv-python
opencv-contrib-python
Pillow
scikit-image
scikit-learn

# Deep learning
torch
torchvision
timm

# Object detection / segmentation
ultralytics          # YOLOv8 / YOLO11
pycocotools

# Video / tracking / pose
deep-sort-realtime
mediapipe

# Advanced
open-clip-torch
segment-anything

# Deployment
onnx
onnxruntime
flask
streamlit

# Utilities
tqdm
requests

```


---

# Module 01_basics


## 01_basics — Module Overview


> File: `01_basics/README.md`

# 01 — Computer Vision Basics

The foundation. Everything downstream (deep learning, YOLO, segmentation) is still just pixels underneath — these scripts make sure you're fluent in manipulating them.

## Concepts covered
| File | Concept |
|------|---------|
| `01_image_read_write.py` | Reading images/video with OpenCV, understanding the pixel array, saving output |
| `02_color_spaces.py` | BGR vs RGB, grayscale, HSV and why HSV is used for color-based filtering |
| `03_image_transformations.py` | Resize, crop, rotate, flip, translate |
| `04_thresholding.py` | Binary thresholding, Otsu's method, adaptive thresholding |
| `05_filtering_blurring.py` | Gaussian/median/bilateral blur and why you'd pick one over another |
| `06_edge_detection.py` | Sobel, Laplacian, Canny edge detectors |
| `07_morphological_operations.py` | Erosion, dilation, opening, closing — cleaning up binary masks |
| `08_histogram_equalization.py` | Histograms, global equalization, CLAHE for local contrast |

## Key idea
An image is just a NumPy array: `shape = (height, width, channels)`. Once that clicks, most of OpenCV is just array manipulation with helper functions.

## Run
```bash
python 01_image_read_write.py path/to/image.jpg
```
If you don't pass a path, most scripts generate a synthetic test image so you can still see the effect.




## `01_basics/01_image_read_write.py`


```python
"""
01 - Reading, Displaying, and Writing Images
=============================================
Concept: An image loaded by OpenCV is a NumPy array of shape (H, W, 3) in BGR order
(NOT RGB — this trips up every beginner at least once).

Run:
    python 01_image_read_write.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def load_image_or_placeholder(path=None):
    """Load an image from disk, or synthesize one if no path is given."""
    if path:
        img = cv2.imread(path)
        if img is None:
            raise FileNotFoundError(f"Could not read image at: {path}")
        return img

    # Synthetic placeholder: a gradient with a drawn circle, so every script
    # in this repo runs out-of-the-box without requiring sample images.
    img = np.zeros((400, 600, 3), dtype=np.uint8)
    for x in range(600):
        img[:, x] = (int(255 * x / 600), 120, int(255 * (1 - x / 600)))
    cv2.circle(img, (300, 200), 80, (255, 255, 255), thickness=3)
    cv2.putText(img, "sample image", (150, 350), cv2.FONT_HERSHEY_SIMPLEX,
                1, (255, 255, 255), 2)
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img = load_image_or_placeholder(path)

    print(f"Image shape (H, W, C): {img.shape}")
    print(f"Data type: {img.dtype}  (uint8 = values 0-255)")
    print(f"Pixel at (0,0) in BGR: {img[0, 0]}")

    out_path = "output_saved_image.png"
    cv2.imwrite(out_path, img)
    print(f"Saved a copy to {out_path}")

    # Display (comment out if running headless / no GUI available)
    try:
        cv2.imshow("Image", img)
        print("Press any key on the image window to close it...")
        cv2.waitKey(0)
        cv2.destroyAllWindows()
    except cv2.error:
        print("No display available (headless environment) — skipped imshow.")


if __name__ == "__main__":
    main()

```


## `01_basics/02_color_spaces.py`


```python
"""
02 - Color Spaces
==================
Concept: BGR (OpenCV default) vs RGB vs Grayscale vs HSV.
HSV (Hue, Saturation, Value) separates COLOR from BRIGHTNESS, which makes it
much easier to filter "all red objects" regardless of lighting conditions —
this is the trick behind most classic color-based object detectors.

Run:
    python 02_color_spaces.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img = cv2.imread(path) if path else None
    if img is None:
        img = np.zeros((300, 300, 3), dtype=np.uint8)
        cv2.rectangle(img, (50, 50), (250, 250), (0, 0, 255), -1)  # red in BGR

    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

    cv2.imwrite("output_gray.png", gray)
    cv2.imwrite("output_rgb_saved_as_bgr.png", rgb)  # note: saving RGB via imwrite flips colors visually
    cv2.imwrite("output_hsv.png", hsv)

    # Practical demo: isolate "red" objects using an HSV range
    lower_red1, upper_red1 = np.array([0, 100, 100]), np.array([10, 255, 255])
    lower_red2, upper_red2 = np.array([160, 100, 100]), np.array([179, 255, 255])
    mask = cv2.bitwise_or(cv2.inRange(hsv, lower_red1, upper_red1),
                           cv2.inRange(hsv, lower_red2, upper_red2))
    result = cv2.bitwise_and(img, img, mask=mask)
    cv2.imwrite("output_red_isolated.png", result)

    print("Saved: output_gray.png, output_hsv.png, output_red_isolated.png")
    print("Try changing the HSV lower/upper bounds to isolate a different color!")


if __name__ == "__main__":
    main()

```


## `01_basics/03_image_transformations.py`


```python
"""
03 - Geometric Transformations
================================
Concept: resizing, cropping, rotating, flipping and translating images.
These are the bread-and-butter preprocessing steps used before feeding
images into almost any CV pipeline (classical or deep learning).

Run:
    python 03_image_transformations.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def placeholder():
    img = np.zeros((300, 400, 3), dtype=np.uint8)
    cv2.rectangle(img, (50, 50), (350, 250), (0, 200, 255), -1)
    cv2.putText(img, "CV", (150, 170), cv2.FONT_HERSHEY_SIMPLEX, 3, (0, 0, 0), 4)
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img = cv2.imread(path) if path else placeholder()
    h, w = img.shape[:2]

    # Resize
    resized = cv2.resize(img, (w // 2, h // 2), interpolation=cv2.INTER_AREA)

    # Crop (NumPy slicing — no special OpenCV function needed)
    cropped = img[0:h // 2, 0:w // 2]

    # Rotate around the center by 45 degrees
    center = (w // 2, h // 2)
    rot_matrix = cv2.getRotationMatrix2D(center, angle=45, scale=1.0)
    rotated = cv2.warpAffine(img, rot_matrix, (w, h))

    # Flip: 0 = vertical, 1 = horizontal, -1 = both
    flipped = cv2.flip(img, 1)

    # Translate (shift) by (tx, ty)
    tx, ty = 50, 30
    trans_matrix = np.float32([[1, 0, tx], [0, 1, ty]])
    translated = cv2.warpAffine(img, trans_matrix, (w, h))

    for name, im in [("resized", resized), ("cropped", cropped),
                      ("rotated", rotated), ("flipped", flipped),
                      ("translated", translated)]:
        cv2.imwrite(f"output_{name}.png", im)

    print("Saved: output_resized.png, output_cropped.png, output_rotated.png, "
          "output_flipped.png, output_translated.png")


if __name__ == "__main__":
    main()

```


## `01_basics/04_thresholding.py`


```python
"""
04 - Thresholding
===================
Concept: convert a grayscale image into a binary (black/white) image by
choosing a cutoff pixel value. This is often the first step before finding
contours or shapes.

- Simple threshold: one global cutoff you choose manually.
- Otsu's method: automatically computes the best global cutoff.
- Adaptive threshold: computes a *local* cutoff per region — essential when
  lighting is uneven across the image.

Run:
    python 04_thresholding.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def placeholder():
    img = np.full((300, 300), 200, dtype=np.uint8)
    cv2.circle(img, (150, 150), 80, 50, -1)
    noise = np.random.normal(0, 15, img.shape).astype(np.int16)
    return np.clip(img.astype(np.int16) + noise, 0, 255).astype(np.uint8)


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    gray = cv2.imread(path, cv2.IMREAD_GRAYSCALE) if path else placeholder()

    _, simple = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)
    otsu_val, otsu = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
    adaptive = cv2.adaptiveThreshold(gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                      cv2.THRESH_BINARY, blockSize=11, C=2)

    print(f"Otsu automatically chose threshold = {otsu_val}")

    cv2.imwrite("output_simple_threshold.png", simple)
    cv2.imwrite("output_otsu_threshold.png", otsu)
    cv2.imwrite("output_adaptive_threshold.png", adaptive)
    print("Saved: output_simple_threshold.png, output_otsu_threshold.png, "
          "output_adaptive_threshold.png")


if __name__ == "__main__":
    main()

```


## `01_basics/05_filtering_blurring.py`


```python
"""
05 - Filtering & Blurring
===========================
Concept: smoothing removes noise but each filter has a different trade-off:
- Gaussian blur: smooth, fast, blurs edges too.
- Median blur: excellent at removing salt-and-pepper noise, preserves edges better.
- Bilateral filter: smooths flat regions while KEEPING edges sharp (slower).

Run:
    python 05_filtering_blurring.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def noisy_placeholder():
    img = np.full((300, 300, 3), 180, dtype=np.uint8)
    cv2.rectangle(img, (60, 60), (240, 240), (30, 30, 30), -1)
    noise = np.random.randint(0, 60, img.shape, dtype=np.uint8)
    salt_pepper = img.copy()
    mask = np.random.random(img.shape[:2])
    salt_pepper[mask < 0.02] = 255
    salt_pepper[mask > 0.98] = 0
    return cv2.add(salt_pepper, noise)


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img = cv2.imread(path) if path else noisy_placeholder()

    gaussian = cv2.GaussianBlur(img, (7, 7), sigmaX=0)
    median = cv2.medianBlur(img, 7)
    bilateral = cv2.bilateralFilter(img, d=9, sigmaColor=75, sigmaSpace=75)

    cv2.imwrite("output_gaussian_blur.png", gaussian)
    cv2.imwrite("output_median_blur.png", median)
    cv2.imwrite("output_bilateral_filter.png", bilateral)
    print("Saved: output_gaussian_blur.png, output_median_blur.png, output_bilateral_filter.png")
    print("Tip: on salt-and-pepper noise, compare median vs gaussian closely — median wins.")


if __name__ == "__main__":
    main()

```


## `01_basics/06_edge_detection.py`


```python
"""
06 - Edge Detection
=====================
Concept: edges = places where pixel intensity changes sharply. Detecting
them is the basis of shape analysis, contour detection, and was the
backbone of object detection before deep learning.

- Sobel: computes intensity gradients in X and Y directions.
- Laplacian: second derivative, detects edges regardless of direction.
- Canny: multi-stage algorithm (blur -> gradient -> non-max suppression ->
  hysteresis thresholding) — the industry-standard edge detector.

Run:
    python 06_edge_detection.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def placeholder():
    img = np.zeros((300, 300), dtype=np.uint8)
    cv2.rectangle(img, (60, 60), (240, 240), 255, -1)
    cv2.circle(img, (150, 150), 50, 0, -1)
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    gray = cv2.imread(path, cv2.IMREAD_GRAYSCALE) if path else placeholder()
    gray = cv2.GaussianBlur(gray, (5, 5), 0)  # reduce noise before edge detection

    sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
    sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)
    sobel_combined = cv2.convertScaleAbs(cv2.magnitude(sobel_x, sobel_y))

    laplacian = cv2.convertScaleAbs(cv2.Laplacian(gray, cv2.CV_64F))

    canny = cv2.Canny(gray, threshold1=50, threshold2=150)

    cv2.imwrite("output_sobel.png", sobel_combined)
    cv2.imwrite("output_laplacian.png", laplacian)
    cv2.imwrite("output_canny.png", canny)
    print("Saved: output_sobel.png, output_laplacian.png, output_canny.png")
    print("Canny is generally the best default choice for most tasks.")


if __name__ == "__main__":
    main()

```


## `01_basics/07_morphological_operations.py`


```python
"""
07 - Morphological Operations
================================
Concept: operations on BINARY images using a small "kernel" (structuring
element) that either shrinks (erosion) or grows (dilation) white regions.
Combining them cleans up noisy masks — critical after thresholding.

- Erosion: shrinks white blobs, removes small noise specks.
- Dilation: grows white blobs, fills small holes.
- Opening = erosion then dilation -> removes small noise, keeps blob size.
- Closing = dilation then erosion -> fills small holes, keeps blob size.

Run:
    python 07_morphological_operations.py [path/to/binary_image.jpg]
"""
import sys
import cv2
import numpy as np


def noisy_binary_placeholder():
    img = np.zeros((300, 300), dtype=np.uint8)
    cv2.rectangle(img, (80, 80), (220, 220), 255, -1)
    rng = np.random.default_rng(0)
    # sprinkle noise
    ys, xs = rng.integers(0, 300, 200), rng.integers(0, 300, 200)
    img[ys, xs] = 255 - img[ys, xs]
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    if path:
        gray = cv2.imread(path, cv2.IMREAD_GRAYSCALE)
        _, binary = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)
    else:
        binary = noisy_binary_placeholder()

    kernel = np.ones((5, 5), np.uint8)

    erosion = cv2.erode(binary, kernel, iterations=1)
    dilation = cv2.dilate(binary, kernel, iterations=1)
    opening = cv2.morphologyEx(binary, cv2.MORPH_OPEN, kernel)
    closing = cv2.morphologyEx(binary, cv2.MORPH_CLOSE, kernel)
    gradient = cv2.morphologyEx(binary, cv2.MORPH_GRADIENT, kernel)  # outline

    for name, im in [("erosion", erosion), ("dilation", dilation),
                      ("opening", opening), ("closing", closing),
                      ("gradient", gradient)]:
        cv2.imwrite(f"output_{name}.png", im)

    print("Saved 5 outputs. Try 'opening' on salt noise and 'closing' on a mask with tiny holes.")


if __name__ == "__main__":
    main()

```


## `01_basics/08_histogram_equalization.py`


```python
"""
08 - Histograms & Equalization
================================
Concept: a histogram shows the distribution of pixel intensities. If most
pixels are bunched in a narrow range (low contrast, e.g. a dark photo),
"equalizing" the histogram spreads values out across the full 0-255 range,
improving contrast.

- Global equalization (cv2.equalizeHist): simple but can over-brighten.
- CLAHE (Contrast Limited Adaptive Histogram Equalization): equalizes in
  small local tiles — much better for real photos, avoids over-amplifying noise.

Run:
    python 08_histogram_equalization.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def low_contrast_placeholder():
    img = np.random.randint(90, 140, (300, 300), dtype=np.uint8)  # narrow intensity band
    cv2.circle(img, (150, 150), 60, 130, -1)
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    gray = cv2.imread(path, cv2.IMREAD_GRAYSCALE) if path else low_contrast_placeholder()

    equalized = cv2.equalizeHist(gray)

    clahe = cv2.createCLAHE(clipLimit=2.0, tileGridSize=(8, 8))
    clahe_result = clahe.apply(gray)

    cv2.imwrite("output_original.png", gray)
    cv2.imwrite("output_equalized.png", equalized)
    cv2.imwrite("output_clahe.png", clahe_result)

    # Save a histogram plot for comparison
    try:
        import matplotlib.pyplot as plt
        fig, axes = plt.subplots(1, 3, figsize=(12, 3))
        for ax, (title, im) in zip(axes, [("Original", gray), ("Equalized", equalized),
                                           ("CLAHE", clahe_result)]):
            ax.hist(im.ravel(), bins=256, range=(0, 255))
            ax.set_title(title)
        plt.tight_layout()
        plt.savefig("output_histograms_comparison.png")
        print("Saved output_histograms_comparison.png")
    except ImportError:
        pass

    print("Saved: output_original.png, output_equalized.png, output_clahe.png")
    print("CLAHE almost always looks better on real photos than global equalization.")


if __name__ == "__main__":
    main()

```


---

# Module 02_intermediate


## 02_intermediate — Module Overview


> File: `02_intermediate/README.md`

# 02 — Intermediate Computer Vision

Now that pixels, thresholds and filters are second nature, this module covers
shape analysis, feature matching, motion, and camera geometry — the tools
that power panorama stitching, AR, and classic object recognition.

| File | Concept |
|------|---------|
| `01_contours.py` | Finding, drawing, and analyzing object outlines (area, perimeter, bounding boxes) |
| `02_feature_detection_sift_orb.py` | SIFT & ORB keypoints, descriptors, and matching between two images |
| `03_template_matching.py` | Finding a small template image inside a larger image |
| `04_image_segmentation_watershed.py` | Watershed algorithm for separating touching objects |
| `05_optical_flow.py` | Tracking pixel motion between video frames (Lucas-Kanade & Farneback) |
| `06_camera_calibration.py` | Correcting lens distortion using a checkerboard pattern |

## Why this matters
These are still used **inside** modern pipelines: feature matching powers SLAM/AR,
optical flow feeds video trackers, and camera calibration is a prerequisite for any
3D vision work (see Module 09).




## `02_intermediate/01_contours.py`


```python
"""
01 - Contours
===============
Concept: contours are curves joining continuous points along a boundary of
the same intensity. After thresholding an image into binary, cv2.findContours
lets you extract each connected shape and compute properties like area,
perimeter, and bounding boxes — the basis of classic shape-based detection.

Run:
    python 01_contours.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np


def placeholder():
    img = np.zeros((300, 400, 3), dtype=np.uint8)
    cv2.rectangle(img, (30, 30), (150, 150), (255, 255, 255), -1)
    cv2.circle(img, (280, 90), 60, (255, 255, 255), -1)
    pts = np.array([[200, 200], [260, 280], [140, 280]])
    cv2.fillPoly(img, [pts], (255, 255, 255))
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img = cv2.imread(path) if path else placeholder()
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    _, binary = cv2.threshold(gray, 50, 255, cv2.THRESH_BINARY)

    contours, hierarchy = cv2.findContours(binary, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
    print(f"Found {len(contours)} contours")

    output = img.copy()
    cv2.drawContours(output, contours, -1, (0, 255, 0), 2)

    for i, c in enumerate(contours):
        area = cv2.contourArea(c)
        perimeter = cv2.arcLength(c, closed=True)
        x, y, w, h = cv2.boundingRect(c)
        cv2.rectangle(output, (x, y), (x + w, y + h), (0, 0, 255), 1)
        cv2.putText(output, f"#{i} A={int(area)}", (x, y - 5),
                    cv2.FONT_HERSHEY_SIMPLEX, 0.4, (255, 0, 0), 1)
        print(f"Contour {i}: area={area:.1f}, perimeter={perimeter:.1f}, bbox=({x},{y},{w},{h})")

    cv2.imwrite("output_contours.png", output)
    print("Saved output_contours.png")


if __name__ == "__main__":
    main()

```


## `02_intermediate/02_feature_detection_sift_orb.py`


```python
"""
02 - Feature Detection & Matching (SIFT / ORB)
=================================================
Concept: keypoints are distinctive, repeatable points in an image (corners,
blobs). Each keypoint gets a "descriptor" vector describing its local
neighborhood. Matching descriptors between two images lets you find the
same object even if rotated, scaled, or viewed from a different angle.

- SIFT: very accurate, scale/rotation invariant, patent-free since 2020.
- ORB: free, fast, binary descriptors — great for real-time applications.

Run:
    python 02_feature_detection_sift_orb.py
(Generates two synthetic related images automatically; pass two image paths
to use your own: python 02_feature_detection_sift_orb.py img1.jpg img2.jpg)
"""
import sys
import cv2
import numpy as np


def make_pair():
    base = np.zeros((300, 300, 3), dtype=np.uint8)
    cv2.rectangle(base, (60, 60), (240, 240), (255, 255, 255), -1)
    cv2.circle(base, (150, 150), 40, (0, 0, 0), -1)
    cv2.putText(base, "CV", (100, 280), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)

    # Second image = rotated + scaled version of the first (simulates a different viewpoint)
    center = (150, 150)
    M = cv2.getRotationMatrix2D(center, angle=20, scale=0.85)
    rotated = cv2.warpAffine(base, M, (300, 300))
    return base, rotated


def main():
    if len(sys.argv) > 2:
        img1 = cv2.imread(sys.argv[1])
        img2 = cv2.imread(sys.argv[2])
    else:
        img1, img2 = make_pair()

    gray1 = cv2.cvtColor(img1, cv2.COLOR_BGR2GRAY)
    gray2 = cv2.cvtColor(img2, cv2.COLOR_BGR2GRAY)

    # --- ORB (always available, no extra dependency) ---
    orb = cv2.ORB_create(nfeatures=500)
    kp1, des1 = orb.detectAndCompute(gray1, None)
    kp2, des2 = orb.detectAndCompute(gray2, None)

    bf = cv2.BFMatcher(cv2.NORM_HAMMING, crossCheck=True)
    matches = sorted(bf.match(des1, des2), key=lambda m: m.distance)

    print(f"ORB: {len(kp1)} keypoints in img1, {len(kp2)} in img2, {len(matches)} matches found")

    match_img = cv2.drawMatches(img1, kp1, img2, kp2, matches[:30], None,
                                 flags=cv2.DrawMatchesFlags_NOT_DRAW_SINGLE_POINTS)
    cv2.imwrite("output_orb_matches.png", match_img)

    # --- SIFT (available in opencv-contrib-python) ---
    try:
        sift = cv2.SIFT_create()
        kp1s, des1s = sift.detectAndCompute(gray1, None)
        kp2s, des2s = sift.detectAndCompute(gray2, None)
        bf_sift = cv2.BFMatcher(cv2.NORM_L2, crossCheck=True)
        matches_sift = sorted(bf_sift.match(des1s, des2s), key=lambda m: m.distance)
        print(f"SIFT: {len(kp1s)} keypoints in img1, {len(matches_sift)} matches found")
        match_img_sift = cv2.drawMatches(img1, kp1s, img2, kp2s, matches_sift[:30], None,
                                          flags=cv2.DrawMatchesFlags_NOT_DRAW_SINGLE_POINTS)
        cv2.imwrite("output_sift_matches.png", match_img_sift)
        print("Saved output_sift_matches.png")
    except cv2.error:
        print("SIFT not available — install opencv-contrib-python")

    print("Saved output_orb_matches.png")


if __name__ == "__main__":
    main()

```


## `02_intermediate/03_template_matching.py`


```python
"""
03 - Template Matching
=========================
Concept: slide a small "template" image over a larger image and compute a
similarity score at every position to find where the template appears.
Simple and fast, but breaks down with rotation/scale changes or lighting
differences — this is exactly the limitation that motivated feature-based
matching (previous file) and, later, learned detectors like YOLO.

Run:
    python 03_template_matching.py
"""
import cv2
import numpy as np


def main():
    scene = np.full((300, 400, 3), 50, dtype=np.uint8)
    cv2.rectangle(scene, (250, 150), (330, 230), (0, 200, 255), -1)  # the "object"
    cv2.circle(scene, (100, 100), 30, (100, 100, 100), -1)           # a distractor

    template = scene[150:230, 250:330].copy()

    result = cv2.matchTemplate(scene, template, cv2.TM_CCOEFF_NORMED)
    _, max_val, _, max_loc = cv2.minMaxLoc(result)

    top_left = max_loc
    h, w = template.shape[:2]
    bottom_right = (top_left[0] + w, top_left[1] + h)

    output = scene.copy()
    cv2.rectangle(output, top_left, bottom_right, (0, 0, 255), 2)
    cv2.putText(output, f"match score: {max_val:.2f}", (top_left[0], top_left[1] - 10),
                cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 0, 255), 1)

    cv2.imwrite("output_template.png", template)
    cv2.imwrite("output_match_result.png", output)
    print(f"Best match score: {max_val:.3f} at {top_left}")
    print("Saved output_template.png and output_match_result.png")


if __name__ == "__main__":
    main()

```


## `02_intermediate/04_image_segmentation_watershed.py`


```python
"""
04 - Watershed Segmentation
==============================
Concept: treats a grayscale image like a topographic surface and "floods"
it from marker points to separate touching/overlapping objects that simple
thresholding + contours would merge into one blob (classic example: touching coins).

Run:
    python 04_image_segmentation_watershed.py
"""
import cv2
import numpy as np


def make_touching_circles():
    img = np.zeros((300, 400, 3), dtype=np.uint8)
    cv2.circle(img, (150, 150), 70, (255, 255, 255), -1)
    cv2.circle(img, (250, 150), 70, (255, 255, 255), -1)  # overlaps the first circle
    return img


def main():
    img = make_touching_circles()
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    _, binary = cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

    kernel = np.ones((3, 3), np.uint8)
    opened = cv2.morphologyEx(binary, cv2.MORPH_OPEN, kernel, iterations=2)
    sure_bg = cv2.dilate(opened, kernel, iterations=3)

    dist_transform = cv2.distanceTransform(opened, cv2.DIST_L2, 5)
    _, sure_fg = cv2.threshold(dist_transform, 0.5 * dist_transform.max(), 255, 0)
    sure_fg = np.uint8(sure_fg)

    unknown = cv2.subtract(sure_bg, sure_fg)

    _, markers = cv2.connectedComponents(sure_fg)
    markers = markers + 1
    markers[unknown == 255] = 0  # mark "unknown" region as 0 for watershed to fill

    markers = cv2.watershed(img, markers)
    img[markers == -1] = [0, 0, 255]  # boundaries drawn in red

    n_objects = markers.max() - 1  # excluding background/boundary labels
    print(f"Watershed separated the blob into {n_objects} distinct objects")

    cv2.imwrite("output_watershed_boundaries.png", img)
    print("Saved output_watershed_boundaries.png — note the red line splitting the two circles")


if __name__ == "__main__":
    main()

```


## `02_intermediate/05_optical_flow.py`


```python
"""
05 - Optical Flow
===================
Concept: estimates the motion of pixels/objects between two consecutive
video frames.

- Lucas-Kanade (sparse): tracks a small set of good feature points frame-to-frame.
- Farneback (dense): estimates motion for EVERY pixel — slower but complete.

This underlies video stabilization, action recognition, and simple motion-based
tracking before dedicated trackers (Module 08).

Run:
    python 05_optical_flow.py
(Generates a synthetic moving-square video sequence automatically.)
"""
import cv2
import numpy as np


def synthetic_frames(n=20):
    frames = []
    for i in range(n):
        frame = np.zeros((300, 300, 3), dtype=np.uint8)
        x = 30 + i * 8
        cv2.rectangle(frame, (x, 120), (x + 50, 170), (0, 200, 0), -1)
        frames.append(frame)
    return frames


def lucas_kanade_demo(frames):
    gray0 = cv2.cvtColor(frames[0], cv2.COLOR_BGR2GRAY)
    p0 = cv2.goodFeaturesToTrack(gray0, maxCorners=50, qualityLevel=0.3, minDistance=7)

    mask = np.zeros_like(frames[0])
    prev_gray = gray0
    for frame in frames[1:]:
        gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
        p1, status, _ = cv2.calcOpticalFlowPyrLK(prev_gray, gray, p0, None)
        good_new = p1[status == 1]
        good_old = p0[status == 1]

        for new, old in zip(good_new, good_old):
            a, b = new.ravel()
            c, d = old.ravel()
            mask = cv2.line(mask, (int(a), int(b)), (int(c), int(d)), (0, 0, 255), 2)
            frame = cv2.circle(frame, (int(a), int(b)), 3, (0, 255, 0), -1)

        prev_gray = gray
        p0 = good_new.reshape(-1, 1, 2)

    combined = cv2.add(frames[-1], mask)
    cv2.imwrite("output_lucas_kanade_tracks.png", combined)
    print("Saved output_lucas_kanade_tracks.png (red lines = tracked point trajectories)")


def farneback_demo(frames):
    prev_gray = cv2.cvtColor(frames[0], cv2.COLOR_BGR2GRAY)
    curr_gray = cv2.cvtColor(frames[10], cv2.COLOR_BGR2GRAY)

    flow = cv2.calcOpticalFlowFarneback(prev_gray, curr_gray, None,
                                         pyr_scale=0.5, levels=3, winsize=15,
                                         iterations=3, poly_n=5, poly_sigma=1.2, flags=0)

    magnitude, angle = cv2.cartToPolar(flow[..., 0], flow[..., 1])
    hsv = np.zeros_like(frames[0])
    hsv[..., 1] = 255
    hsv[..., 0] = angle * 180 / np.pi / 2
    hsv[..., 2] = cv2.normalize(magnitude, None, 0, 255, cv2.NORM_MINMAX)
    flow_rgb = cv2.cvtColor(hsv, cv2.COLOR_HSV2BGR)

    cv2.imwrite("output_farneback_flow.png", flow_rgb)
    print("Saved output_farneback_flow.png (color = direction, brightness = motion speed)")


def main():
    frames = synthetic_frames()
    lucas_kanade_demo(frames)
    farneback_demo(frames)


if __name__ == "__main__":
    main()

```


## `02_intermediate/06_camera_calibration.py`


```python
"""
06 - Camera Calibration
==========================
Concept: real camera lenses distort images (barrel/pincushion distortion).
By photographing a known checkerboard pattern from several angles, OpenCV
can compute the camera's intrinsic matrix and distortion coefficients, then
undistort any future image from that camera. This is a REQUIRED step before
any accurate 3D vision / stereo depth work (see Module 09).

This script demonstrates the full API using synthetic checkerboard corner
points (no physical camera/checkerboard needed to understand the flow).

Run:
    python 06_camera_calibration.py
"""
import cv2
import numpy as np

CHECKERBOARD = (7, 6)  # inner corners per row/column of a standard chessboard


def synthetic_checkerboard_image():
    """Draws a chessboard pattern so cv2.findChessboardCorners can actually find it."""
    square = 40
    img = np.zeros(((CHECKERBOARD[1] + 2) * square, (CHECKERBOARD[0] + 2) * square, 3), dtype=np.uint8)
    img[:] = 255
    for r in range(CHECKERBOARD[1] + 2):
        for c in range(CHECKERBOARD[0] + 2):
            if (r + c) % 2 == 0:
                y0, y1 = r * square, (r + 1) * square
                x0, x1 = c * square, (c + 1) * square
                img[y0:y1, x0:x1] = 0
    return img


def main():
    objp = np.zeros((CHECKERBOARD[0] * CHECKERBOARD[1], 3), np.float32)
    objp[:, :2] = np.mgrid[0:CHECKERBOARD[0], 0:CHECKERBOARD[1]].T.reshape(-1, 2)

    img = synthetic_checkerboard_image()
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

    found, corners = cv2.findChessboardCorners(gray, CHECKERBOARD, None)
    print(f"Chessboard corners found: {found}")

    if found:
        criteria = (cv2.TERM_CRITERIA_EPS + cv2.TERM_CRITERIA_MAX_ITER, 30, 0.001)
        corners_refined = cv2.cornerSubPix(gray, corners, (11, 11), (-1, -1), criteria)

        drawn = img.copy()
        cv2.drawChessboardCorners(drawn, CHECKERBOARD, corners_refined, found)
        cv2.imwrite("output_detected_corners.png", drawn)

        # In a REAL calibration you'd collect objpoints/imgpoints from 15-20 images
        # taken from different angles, then call cv2.calibrateCamera once with all of them:
        #
        #   ret, camera_matrix, dist_coeffs, rvecs, tvecs = cv2.calibrateCamera(
        #       objpoints_list, imgpoints_list, gray.shape[::-1], None, None)
        #
        # Then undistort any new frame with:
        #   undistorted = cv2.undistort(new_frame, camera_matrix, dist_coeffs)
        print("Saved output_detected_corners.png")
        print("NOTE: real calibration needs 15-20 images of the SAME physical checkerboard")
        print("      from different angles — see the commented cv2.calibrateCamera call above.")
    else:
        print("Could not detect the synthetic checkerboard — adjust CHECKERBOARD dimensions.")


if __name__ == "__main__":
    main()

```


---

# Module 03_classical_ml


## 03_classical_ml — Module Overview


> File: `03_classical_ml/README.md`

# 03 — Classical Machine Learning for Vision

Before deep learning, object detection/recognition relied on hand-crafted
features fed into classical ML classifiers. Understanding this era makes
you appreciate *why* CNNs were such a breakthrough (they learn the features
automatically instead of you hand-designing them).

| File | Concept |
|------|---------|
| `01_hog_svm_classifier.py` | Histogram of Oriented Gradients (HOG) features + SVM classifier — the pre-deep-learning standard for pedestrian/person detection |
| `02_haar_cascade_face_detection.py` | Haar Cascades — the classic (2001) real-time face detector, still shipped with OpenCV |
| `03_kmeans_color_segmentation.py` | Unsupervised K-Means clustering to segment an image by color |

## Why this still matters
- Haar Cascades are still genuinely useful for lightweight face detection on constrained devices.
- HOG+SVM concepts (gradient-based features) directly inspired parts of early CNN design.
- K-Means segmentation is a fast baseline you should try before reaching for a deep segmentation model.




## `03_classical_ml/01_hog_svm_classifier.py`


```python
"""
01 - HOG Features + SVM Classifier
======================================
Concept: Histogram of Oriented Gradients (HOG) describes an image patch by
the distribution of edge directions in local cells — very effective for
capturing "shape" while ignoring exact pixel values. Feed HOG feature
vectors into a Support Vector Machine (SVM) and you get a strong classical
object classifier. This exact combo (Dalal & Triggs, 2005) was the state of
the art for pedestrian detection before deep learning.

This script:
1. Uses OpenCV's built-in pretrained HOG+SVM PEOPLE detector (ready to use).
2. Also shows how you'd train your OWN HOG+SVM classifier on custom image patches.

Run:
    python 01_hog_svm_classifier.py [path/to/image_or_video.jpg]
"""
import sys
import cv2
import numpy as np
from sklearn.svm import LinearSVC


def demo_pretrained_people_detector(path=None):
    hog = cv2.HOGDescriptor()
    hog.setSVMDetector(cv2.HOGDescriptor_getDefaultPeopleDetector())

    if path:
        img = cv2.imread(path)
    else:
        img = np.full((300, 200, 3), 220, dtype=np.uint8)
        cv2.putText(img, "no people", (10, 150), cv2.FONT_HERSHEY_SIMPLEX, 0.6, (0, 0, 0), 1)

    boxes, weights = hog.detectMultiScale(img, winStride=(8, 8))
    for (x, y, w, h) in boxes:
        cv2.rectangle(img, (x, y), (x + w, y + h), (0, 255, 0), 2)

    cv2.imwrite("output_hog_people_detection.png", img)
    print(f"Pretrained HOG detector found {len(boxes)} person(s). Saved output_hog_people_detection.png")


def demo_train_custom_hog_svm():
    """
    Minimal illustration: extract HOG features from small synthetic patches
    (circles vs squares) and train a LinearSVC to tell them apart — the same
    recipe you'd use for e.g. "cat vs dog" patches, just at toy scale.
    """
    hog = cv2.HOGDescriptor(_winSize=(64, 64), _blockSize=(16, 16),
                             _blockStride=(8, 8), _cellSize=(8, 8), _nbins=9)

    def make_patch(shape_type):
        img = np.zeros((64, 64), dtype=np.uint8)
        if shape_type == "circle":
            cv2.circle(img, (32, 32), 20, 255, -1)
        else:
            cv2.rectangle(img, (12, 12), (52, 52), 255, -1)
        return img

    X, y = [], []
    for label, shape in enumerate(["circle", "square"]):
        for _ in range(30):
            patch = make_patch(shape)
            noise = np.random.randint(0, 20, patch.shape, dtype=np.uint8)
            patch = cv2.add(patch, noise)
            X.append(hog.compute(patch).flatten())
            y.append(label)

    X, y = np.array(X), np.array(y)
    clf = LinearSVC(max_iter=5000)
    clf.fit(X, y)

    test_circle = hog.compute(make_patch("circle")).flatten().reshape(1, -1)
    test_square = hog.compute(make_patch("square")).flatten().reshape(1, -1)
    print(f"Trained custom HOG+SVM. Predicted 'circle' patch as class: "
          f"{['circle','square'][clf.predict(test_circle)[0]]}")
    print(f"Predicted 'square' patch as class: "
          f"{['circle','square'][clf.predict(test_square)[0]]}")


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    demo_pretrained_people_detector(path)
    demo_train_custom_hog_svm()


if __name__ == "__main__":
    main()

```


## `03_classical_ml/02_haar_cascade_face_detection.py`


```python
"""
02 - Haar Cascade Face Detection
====================================
Concept: Haar Cascades (Viola-Jones, 2001) detect objects by sliding
rectangular "Haar-like features" (differences of dark/light region sums)
across the image at multiple scales, using a cascade of increasingly strict
classifiers to reject non-faces early (making it fast). It was the first
real-time face detector and still ships built into OpenCV.

Run:
    python 02_haar_cascade_face_detection.py [path/to/image.jpg]
    python 02_haar_cascade_face_detection.py --webcam
"""
import sys
import cv2


def get_cascades():
    face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")
    eye_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_eye.xml")
    return face_cascade, eye_cascade


def detect_and_draw(frame, face_cascade, eye_cascade):
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    faces = face_cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5, minSize=(30, 30))

    for (x, y, w, h) in faces:
        cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 2)
        roi_gray = gray[y:y + h, x:x + w]
        roi_color = frame[y:y + h, x:x + w]
        eyes = eye_cascade.detectMultiScale(roi_gray)
        for (ex, ey, ew, eh) in eyes:
            cv2.rectangle(roi_color, (ex, ey), (ex + ew, ey + eh), (255, 0, 0), 2)

    return frame, len(faces)


def main():
    face_cascade, eye_cascade = get_cascades()

    if "--webcam" in sys.argv:
        cap = cv2.VideoCapture(0)
        print("Press 'q' to quit the webcam window.")
        while True:
            ret, frame = cap.read()
            if not ret:
                break
            frame, n = detect_and_draw(frame, face_cascade, eye_cascade)
            cv2.imshow("Haar Cascade Face Detection", frame)
            if cv2.waitKey(1) & 0xFF == ord('q'):
                break
        cap.release()
        cv2.destroyAllWindows()
        return

    path = sys.argv[1] if len(sys.argv) > 1 else None
    if path:
        img = cv2.imread(path)
    else:
        print("No image path given and --webcam not passed.")
        print("Usage: python 02_haar_cascade_face_detection.py path/to/photo_with_a_face.jpg")
        print("       python 02_haar_cascade_face_detection.py --webcam")
        return

    result, n = detect_and_draw(img, face_cascade, eye_cascade)
    cv2.imwrite("output_face_detection.png", result)
    print(f"Detected {n} face(s). Saved output_face_detection.png")


if __name__ == "__main__":
    main()

```


## `03_classical_ml/03_kmeans_color_segmentation.py`


```python
"""
03 - K-Means Color Segmentation
===================================
Concept: K-Means is an UNSUPERVISED clustering algorithm. Treat every pixel's
(B, G, R) value as a 3D point, cluster all pixels into K groups by color
similarity, then repaint each pixel with its cluster's average color. This
gives a fast "poster-ized" segmentation with no training data required —
a great baseline before jumping to deep segmentation models (Module 06).

Run:
    python 03_kmeans_color_segmentation.py [path/to/image.jpg] [k]
"""
import sys
import cv2
import numpy as np


def placeholder():
    img = np.zeros((300, 400, 3), dtype=np.uint8)
    img[:150, :200] = (200, 50, 50)
    img[:150, 200:] = (50, 200, 50)
    img[150:, :200] = (50, 50, 200)
    img[150:, 200:] = (200, 200, 50)
    noise = np.random.randint(0, 30, img.shape, dtype=np.uint8)
    return cv2.add(img, noise)


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    k = int(sys.argv[2]) if len(sys.argv) > 2 else 4

    img = cv2.imread(path) if path else placeholder()
    pixel_values = img.reshape((-1, 3)).astype(np.float32)

    criteria = (cv2.TERM_CRITERIA_EPS + cv2.TERM_CRITERIA_MAX_ITER, 100, 0.2)
    _, labels, centers = cv2.kmeans(pixel_values, k, None, criteria, attempts=10,
                                     flags=cv2.KMEANS_RANDOM_CENTERS)

    centers = np.uint8(centers)
    segmented = centers[labels.flatten()].reshape(img.shape)

    cv2.imwrite("output_kmeans_segmented.png", segmented)
    print(f"Segmented image into {k} color clusters. Saved output_kmeans_segmented.png")
    print(f"Cluster center colors (BGR): {centers.tolist()}")


if __name__ == "__main__":
    main()

```


---

# Module 04_deep_learning_basics


## 04_deep_learning_basics — Module Overview


> File: `04_deep_learning_basics/README.md`

# 04 — Deep Learning Basics for Vision

This is the turning point: instead of hand-crafting features (HOG, Haar,
edges), we let a neural network **learn** the best features directly from
data. Everything from here on (YOLO, segmentation, ViT) builds on these
fundamentals.

| File | Concept |
|------|---------|
| `01_cnn_from_scratch_pytorch.py` | Build and train a small CNN from scratch on synthetic image data — understand every layer |
| `02_transfer_learning_resnet.py` | Fine-tune a pretrained ResNet18 on a new small dataset — the real-world default approach |
| `03_data_augmentation.py` | Flip/rotate/color-jitter/crop to artificially grow your dataset and reduce overfitting |
| `04_custom_dataset_dataloader.py` | Write a PyTorch `Dataset` + `DataLoader` for your own folder of images |

## Key idea
A Convolutional Neural Network (CNN) learns a hierarchy of features automatically:
early layers learn edges/colors (similar to Sobel/Canny!), middle layers learn
textures and shapes, and deep layers learn whole object parts. This hierarchy is
*why* CNNs beat hand-crafted HOG/Haar features once enough data was available.

## Requirements
```bash
pip install torch torchvision
```




## `04_deep_learning_basics/01_cnn_from_scratch_pytorch.py`


```python
"""
01 - CNN From Scratch (PyTorch)
===================================
Concept: build the smallest possible Convolutional Neural Network and train
it on a toy synthetic dataset (circles vs squares) so you can see every
piece — conv layer, activation, pooling, fully connected layer, loss,
backprop — with nothing hidden behind a pretrained model.

Run:
    python 01_cnn_from_scratch_pytorch.py
"""
import numpy as np
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import Dataset, DataLoader


class SimpleCNN(nn.Module):
    """A minimal CNN: Conv -> ReLU -> Pool, twice, then a classifier head."""
    def __init__(self, num_classes=2):
        super().__init__()
        self.features = nn.Sequential(
            nn.Conv2d(1, 8, kernel_size=3, padding=1),   # 1 input channel (grayscale) -> 8 feature maps
            nn.ReLU(),
            nn.MaxPool2d(2),                              # 32x32 -> 16x16
            nn.Conv2d(8, 16, kernel_size=3, padding=1),
            nn.ReLU(),
            nn.MaxPool2d(2),                              # 16x16 -> 8x8
        )
        self.classifier = nn.Sequential(
            nn.Flatten(),
            nn.Linear(16 * 8 * 8, 32),
            nn.ReLU(),
            nn.Linear(32, num_classes),
        )

    def forward(self, x):
        x = self.features(x)
        return self.classifier(x)


class ShapesDataset(Dataset):
    """Synthetic dataset: 32x32 grayscale images of circles (label 0) or squares (label 1)."""
    def __init__(self, n_samples=400, size=32):
        self.size = size
        self.data, self.labels = [], []
        for i in range(n_samples):
            img = np.zeros((size, size), dtype=np.float32)
            label = i % 2
            if label == 0:
                import cv2
                cv2.circle(img, (size // 2, size // 2), size // 3, 1.0, -1)
            else:
                import cv2
                cv2.rectangle(img, (size // 4, size // 4), (3 * size // 4, 3 * size // 4), 1.0, -1)
            img += np.random.normal(0, 0.05, img.shape).astype(np.float32)  # a little noise
            self.data.append(img)
            self.labels.append(label)

    def __len__(self):
        return len(self.data)

    def __getitem__(self, idx):
        img = torch.tensor(self.data[idx]).unsqueeze(0)  # add channel dim -> (1, H, W)
        return img, self.labels[idx]


def main():
    torch.manual_seed(0)
    train_ds = ShapesDataset(n_samples=300)
    test_ds = ShapesDataset(n_samples=60)
    train_loader = DataLoader(train_ds, batch_size=16, shuffle=True)
    test_loader = DataLoader(test_ds, batch_size=16)

    model = SimpleCNN(num_classes=2)
    optimizer = optim.Adam(model.parameters(), lr=1e-3)
    criterion = nn.CrossEntropyLoss()

    print("Training a tiny CNN to distinguish circles from squares...")
    for epoch in range(5):
        model.train()
        total_loss = 0
        for imgs, labels in train_loader:
            optimizer.zero_grad()
            outputs = model(imgs)
            loss = criterion(outputs, labels)
            loss.backward()
            optimizer.step()
            total_loss += loss.item()
        print(f"Epoch {epoch+1}/5 - loss: {total_loss / len(train_loader):.4f}")

    # Evaluate
    model.eval()
    correct, total = 0, 0
    with torch.no_grad():
        for imgs, labels in test_loader:
            preds = model(imgs).argmax(dim=1)
            correct += (preds == labels).sum().item()
            total += labels.size(0)
    print(f"Test accuracy: {100 * correct / total:.1f}%")
    print("\nThis is exactly what a real CNN does at scale — more layers, more classes, real images.")


if __name__ == "__main__":
    main()

```


## `04_deep_learning_basics/02_transfer_learning_resnet.py`


```python
"""
02 - Transfer Learning with ResNet18
========================================
Concept: training a CNN from scratch needs LOTS of data. Instead, take a
model already trained on ImageNet (1.4M images, 1000 classes) — it has
already learned excellent general-purpose visual features — and just
replace + retrain its final layer(s) for YOUR task. This is what ~90% of
real-world CV projects actually do.

Two common strategies:
1. Feature extraction: freeze all pretrained layers, train only the new head.
   (Fast, needs less data, good when your data is small/similar to ImageNet.)
2. Fine-tuning: unfreeze some/all layers and train with a small learning rate.
   (Needs more data, but adapts the features more to your specific task.)

Run:
    python 02_transfer_learning_resnet.py
"""
import torch
import torch.nn as nn
import torch.optim as optim
from torchvision import models, transforms


def build_model(num_classes=3, freeze_backbone=True):
    model = models.resnet18(weights=models.ResNet18_Weights.IMAGENET1K_V1)

    if freeze_backbone:
        for param in model.parameters():
            param.requires_grad = False  # freeze everything...

    # ...then replace the final classification layer (always trainable)
    num_features = model.fc.in_features
    model.fc = nn.Linear(num_features, num_classes)
    return model


def main():
    model = build_model(num_classes=3, freeze_backbone=True)
    print(model.fc)  # only this new layer will be trained in "feature extraction" mode

    trainable_params = [p for p in model.parameters() if p.requires_grad]
    print(f"Trainable parameters: {sum(p.numel() for p in trainable_params):,} "
          f"(out of {sum(p.numel() for p in model.parameters()):,} total)")

    # Standard ImageNet preprocessing — required so the pretrained weights behave correctly
    preprocess = transforms.Compose([
        transforms.Resize(256),
        transforms.CenterCrop(224),
        transforms.ToTensor(),
        transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225]),
    ])

    # Demo forward pass with a random "image" (replace with your real DataLoader)
    dummy_batch = torch.randn(4, 3, 224, 224)
    optimizer = optim.Adam(trainable_params, lr=1e-3)
    criterion = nn.CrossEntropyLoss()
    dummy_labels = torch.tensor([0, 1, 2, 0])

    model.train()
    outputs = model(dummy_batch)
    loss = criterion(outputs, dummy_labels)
    loss.backward()
    optimizer.step()
    print(f"\nOne training step completed. Loss: {loss.item():.4f}")
    print("\nSwap `dummy_batch`/`dummy_labels` for a real DataLoader (see 04_custom_dataset_dataloader.py)")
    print("to fine-tune on your own image folders.")


if __name__ == "__main__":
    main()

```


## `04_deep_learning_basics/03_data_augmentation.py`


```python
"""
03 - Data Augmentation
=========================
Concept: neural networks are data-hungry and prone to overfitting on small
datasets. Data augmentation artificially expands your training set by
applying random, label-preserving transformations (flip, rotate, crop,
color jitter) every epoch, so the model never sees the exact same image
twice and generalizes better.

Run:
    python 03_data_augmentation.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np
from torchvision import transforms
from PIL import Image


def placeholder_pil():
    arr = np.zeros((200, 200, 3), dtype=np.uint8)
    cv2.rectangle(arr, (40, 40), (160, 160), (0, 180, 255), -1)
    cv2.putText(arr, "AUG", (55, 110), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)
    return Image.fromarray(cv2.cvtColor(arr, cv2.COLOR_BGR2RGB))


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img = Image.open(path).convert("RGB") if path else placeholder_pil()

    augment = transforms.Compose([
        transforms.RandomHorizontalFlip(p=0.5),
        transforms.RandomRotation(degrees=25),
        transforms.ColorJitter(brightness=0.4, contrast=0.4, saturation=0.4, hue=0.1),
        transforms.RandomResizedCrop(size=img.size, scale=(0.7, 1.0)),
    ])

    grid_cols, grid_rows = 4, 2
    cell_w, cell_h = img.size
    grid = Image.new("RGB", (cell_w * grid_cols, cell_h * grid_rows))
    grid.paste(img, (0, 0))  # top-left cell = original

    idx = 1
    for r in range(grid_rows):
        for c in range(grid_cols):
            if r == 0 and c == 0:
                continue
            augmented = augment(img)
            grid.paste(augmented, (c * cell_w, r * cell_h))
            idx += 1

    grid.save("output_augmentation_grid.png")
    print("Saved output_augmentation_grid.png — top-left is the original, rest are random augmentations.")
    print("Run again to see different random augmentations each time.")


if __name__ == "__main__":
    main()

```


## `04_deep_learning_basics/04_custom_dataset_dataloader.py`


```python
"""
04 - Custom Dataset & DataLoader
===================================
Concept: PyTorch expects your data wrapped in a `Dataset` (defines how to
get one sample) fed into a `DataLoader` (handles batching, shuffling,
parallel loading). This is the standard scaffolding you'll reuse for every
real project — classification, detection, or segmentation.

Expected folder layout for a real project:
    my_dataset/
        class_a/
            img1.jpg
            img2.jpg
        class_b/
            img3.jpg
            ...

Run:
    python 04_custom_dataset_dataloader.py [path/to/my_dataset]
(Falls back to an auto-generated synthetic dataset folder if no path given.)
"""
import os
import sys
import cv2
import numpy as np
import torch
from torch.utils.data import Dataset, DataLoader
from torchvision import transforms


class ImageFolderDataset(Dataset):
    def __init__(self, root_dir, transform=None):
        self.root_dir = root_dir
        self.transform = transform
        self.classes = sorted(os.listdir(root_dir))
        self.class_to_idx = {c: i for i, c in enumerate(self.classes)}
        self.samples = []
        for cls in self.classes:
            cls_dir = os.path.join(root_dir, cls)
            for fname in os.listdir(cls_dir):
                self.samples.append((os.path.join(cls_dir, fname), self.class_to_idx[cls]))

    def __len__(self):
        return len(self.samples)

    def __getitem__(self, idx):
        path, label = self.samples[idx]
        img = cv2.cvtColor(cv2.imread(path), cv2.COLOR_BGR2RGB)
        if self.transform:
            img = self.transform(img)
        return img, label


def make_synthetic_dataset_folder(root="synthetic_dataset"):
    os.makedirs(f"{root}/circle", exist_ok=True)
    os.makedirs(f"{root}/square", exist_ok=True)
    for i in range(10):
        c = np.zeros((64, 64, 3), dtype=np.uint8)
        cv2.circle(c, (32, 32), 20, (255, 255, 255), -1)
        cv2.imwrite(f"{root}/circle/circle_{i}.png", c)

        s = np.zeros((64, 64, 3), dtype=np.uint8)
        cv2.rectangle(s, (12, 12), (52, 52), (255, 255, 255), -1)
        cv2.imwrite(f"{root}/square/square_{i}.png", s)
    return root


def main():
    root_dir = sys.argv[1] if len(sys.argv) > 1 else make_synthetic_dataset_folder()

    transform = transforms.Compose([
        transforms.ToTensor(),
    ])

    dataset = ImageFolderDataset(root_dir, transform=transform)
    print(f"Found {len(dataset)} images across classes: {dataset.classes}")

    loader = DataLoader(dataset, batch_size=4, shuffle=True, num_workers=0)
    imgs, labels = next(iter(loader))
    print(f"One batch shape: {imgs.shape}  (batch, channels, H, W)")
    print(f"Labels in this batch: {labels.tolist()}")
    print("\nThis `loader` is ready to plug directly into a training loop "
          "(see 01_cnn_from_scratch_pytorch.py or 02_transfer_learning_resnet.py).")


if __name__ == "__main__":
    main()

```


---

# Module 05_object_detection


## 05_object_detection — Module Overview


> File: `05_object_detection/README.md`

# 05 — Object Detection (incl. YOLO Deep Dive) ⭐

Detection = localizing (bounding boxes) **and** classifying multiple objects
in one image. This module traces the field's evolution from brute-force
sliding windows to today's real-time YOLO models.

| File | Concept |
|------|---------|
| `01_sliding_window_detection.py` | The naive first-principles approach: slide a classifier window across the image at multiple scales |
| `02_rcnn_family_explained.md` | R-CNN → Fast R-CNN → Faster R-CNN — how region proposals evolved |
| `03_yolo_explained.md` | **How YOLO actually works**: grid cells, anchor boxes, IoU, NMS, the loss function |
| `04_yolov8_inference.py` | Run YOLOv8 inference on an image in ~10 lines |
| `05_yolov8_custom_training.py` | Train YOLOv8 on your OWN custom dataset |
| `06_yolo_realtime_webcam.py` | Real-time object detection on a live webcam feed |
| `07_faster_rcnn_torchvision.py` | Faster R-CNN via torchvision — the two-stage alternative to YOLO |

## The big picture: one-stage vs two-stage detectors
- **Two-stage** (R-CNN family, Faster R-CNN): first propose candidate regions, then classify each. More accurate historically, slower.
- **One-stage** (YOLO, SSD): predict boxes and classes directly in a single pass. Much faster, now equally (or more) accurate — this is why YOLO dominates real-time applications (robotics, video, edge devices).

## Requirements
```bash
pip install ultralytics torchvision
```

Start with `03_yolo_explained.md` before running the YOLO scripts — it explains what the numbers you'll see (confidence, class, IoU) actually mean.




## `05_object_detection/01_sliding_window_detection.py`


```python
"""
01 - Sliding Window Detection (First Principles)
====================================================
Concept: before any "smart" detection algorithm existed, the naive approach
was: slide a fixed-size window across the entire image (at multiple scales
via an "image pyramid"), classify each window as object/not-object, and
keep the high-confidence ones. It's simple but extremely slow (thousands of
windows per image) — this exact bottleneck is what motivated every
detector since (R-CNN's region proposals, YOLO's single-pass grid).

Run:
    python 01_sliding_window_detection.py
"""
import cv2
import numpy as np


def make_scene():
    img = np.full((300, 400, 3), 40, dtype=np.uint8)
    cv2.rectangle(img, (250, 100), (330, 180), (0, 200, 255), -1)  # the "target"
    return img


def simple_classifier(window, target_color=(0, 200, 255), tolerance=30):
    """Toy 'classifier': is this window mostly the target color? (stand-in for a real ML model)"""
    mean_color = window.reshape(-1, 3).mean(axis=0)
    return np.all(np.abs(mean_color - np.array(target_color)) < tolerance)


def image_pyramid(img, scale=1.5, min_size=(60, 60)):
    yield img
    while True:
        w = int(img.shape[1] / scale)
        h = int(img.shape[0] / scale)
        img = cv2.resize(img, (w, h))
        if w < min_size[0] or h < min_size[1]:
            break
        yield img


def sliding_window(img, step_size, window_size):
    for y in range(0, img.shape[0] - window_size[1], step_size):
        for x in range(0, img.shape[1] - window_size[0], step_size):
            yield x, y, img[y:y + window_size[1], x:x + window_size[0]]


def main():
    scene = make_scene()
    window_size = (80, 80)
    detections = []
    windows_checked = 0

    for level, scaled in enumerate(image_pyramid(scene)):
        scale_factor = scene.shape[1] / scaled.shape[1]
        for x, y, window in sliding_window(scaled, step_size=20, window_size=window_size):
            windows_checked += 1
            if simple_classifier(window):
                orig_box = (int(x * scale_factor), int(y * scale_factor),
                            int((x + window_size[0]) * scale_factor),
                            int((y + window_size[1]) * scale_factor))
                detections.append(orig_box)

    print(f"Checked {windows_checked} windows across the image pyramid")
    print(f"Raw detections before merging: {len(detections)} (many overlapping boxes around the same object!)")

    # This overlap problem is exactly what Non-Max Suppression solves — see 03_yolo_explained.md
    boxes = np.array(detections)
    if len(boxes) > 0:
        indices = cv2.dnn.NMSBoxes(
            [[x, y, x2 - x, y2 - y] for x, y, x2, y2 in boxes],
            [1.0] * len(boxes), score_threshold=0.5, nms_threshold=0.3)
        output = scene.copy()
        for i in np.array(indices).flatten():
            x, y, x2, y2 = boxes[i]
            cv2.rectangle(output, (x, y), (x2, y2), (0, 255, 0), 2)
        cv2.imwrite("output_sliding_window_detection.png", output)
        print(f"After Non-Max Suppression: {len(np.array(indices).flatten())} final detection(s)")
        print("Saved output_sliding_window_detection.png")


if __name__ == "__main__":
    main()

```


> File: `05_object_detection/02_rcnn_family_explained.md`

# The R-CNN Family: How Region-Based Detection Evolved

Two-stage detectors first find **where** objects might be (region proposals), then decide **what** each region contains. Here's how the idea was refined over four papers.

## 1. R-CNN (2014) — "Regions with CNN features"
**Pipeline:**
1. Run **Selective Search** (a classical algorithm) to propose ~2000 candidate regions per image.
2. Warp each region to a fixed size, run it through a CNN to extract features.
3. Classify each region's features with an SVM.
4. Refine each box with a separate linear regression model.

**Problem:** Steps 2–4 run *independently for all ~2000 regions, per image* → extremely slow (~47 seconds/image on GPU). Training was also a multi-stage pipeline (CNN, then SVMs, then box regressors trained separately).

## 2. Fast R-CNN (2015)
**Key fix:** stop re-running the CNN 2000 times per image.
1. Run the CNN **once** on the whole image to get a feature map.
2. For each region proposal (still from Selective Search), crop the *corresponding region of the feature map* using **RoI Pooling** instead of re-computing features from scratch.
3. A single network head then does both classification AND box regression jointly, trained end-to-end.

**Result:** ~25x faster than R-CNN. But region proposals (Selective Search) were still a slow, non-learned, CPU-bound bottleneck.

## 3. Faster R-CNN (2015)
**Key fix:** replace Selective Search with a learned **Region Proposal Network (RPN)** — a small CNN that slides over the feature map and directly predicts candidate boxes ("objectness" score + box coordinates) using a set of predefined **anchor boxes** at each location.

**Pipeline:**
1. Backbone CNN produces a feature map.
2. RPN proposes regions directly from that same feature map (shared computation — fast!).
3. RoI Pooling + classification/regression head, same as Fast R-CNN.

**Result:** Real-time-ish (~5-17 FPS depending on hardware/backbone), fully end-to-end trainable, and this anchor-box idea directly carried over into YOLO's early versions. See `07_faster_rcnn_torchvision.py` for a working implementation.

## Why this matters for understanding YOLO
YOLO (next file) throws away the "two stages" idea entirely — no separate proposal step. It predicts boxes and classes for the whole image in ONE forward pass, which is exactly why it's so much faster. But concepts introduced here — **anchor boxes**, **IoU**, **Non-Max Suppression** — are used by YOLO too. Read `03_yolo_explained.md` next.

## Quick comparison

| Model | Proposal method | Speed | Notes |
|---|---|---|---|
| R-CNN | Selective Search | ~47s/image | First deep-learning detector |
| Fast R-CNN | Selective Search | ~2s/image | Shared CNN features |
| Faster R-CNN | Learned RPN | ~0.2s/image | Fully end-to-end |
| YOLO | None (single pass) | ~0.01-0.03s/image | See next file |




> File: `05_object_detection/03_yolo_explained.md`

# YOLO Explained: You Only Look Once

YOLO reframes object detection as a **single regression problem**: one neural
network pass over the whole image directly outputs all bounding boxes and
class probabilities. No separate region-proposal stage. This is *why* it's
called "You Only Look Once" — one look, not thousands of sliding windows or
a two-stage pipeline.

## 1. The core idea: grid cells
YOLO divides the input image into an **S × S grid** (e.g. 13×13, 20×20 —
depends on version/resolution). Each grid cell is responsible for detecting
any object whose **center** falls inside it. Each cell predicts:
- A set of candidate **bounding boxes** (x, y, width, height)
- A **confidence score** = P(object exists) × IoU(predicted box, ground truth)
- **Class probabilities** for what's in the box (person, car, dog, ...)

## 2. Anchor boxes (YOLOv2 onward; modern YOLOv8+ is mostly anchor-free)
Instead of predicting raw box coordinates from nothing, earlier YOLO versions
predict *offsets* from a set of predefined "anchor" box shapes (e.g. tall-thin
for pedestrians, wide-short for cars) chosen ahead of time by clustering the
training set's box shapes (k-means on box dimensions). This gives the network
a much better starting point than guessing coordinates from scratch.
Newer YOLO versions (v8, v11) use an **anchor-free** design that predicts box
distances directly from each grid point, simplifying this step.

## 3. Intersection over Union (IoU) — how "correctness" is measured
```
IoU = (Area of Overlap) / (Area of Union)
```
IoU=1.0 means a perfect box match; IoU=0 means no overlap at all. IoU is used:
- **During training**, to decide which predicted box is "responsible" for a ground-truth object.
- **During evaluation**, as the threshold for counting a detection as correct (e.g. mAP@0.5 means IoU ≥ 0.5 counts as a hit).

## 4. Non-Max Suppression (NMS) — cleaning up duplicate boxes
A single object is often detected by MULTIPLE overlapping boxes (from
neighboring grid cells / anchors). NMS keeps only the highest-confidence box
and suppresses (deletes) all other boxes that overlap it above an IoU
threshold (e.g. 0.45). This is why you see one clean box per object in the
final output, not a cluster of near-duplicates.

## 5. The loss function (conceptually)
YOLO's training loss combines three parts:
1. **Box regression loss** — how far off are predicted (x, y, w, h) from the ground truth?
2. **Objectness/confidence loss** — did the model correctly predict "there IS an object here" vs "there is NOT"?
3. **Classification loss** — for cells that DO contain an object, is the predicted class correct?

These are added together (with different weights) into a single number the network minimizes end-to-end.

## 6. Evolution at a glance

| Version | Key improvement |
|---|---|
| YOLOv1 (2016) | Original single-pass grid idea |
| YOLOv2/v3 | Anchor boxes, multi-scale prediction, better backbone (Darknet) |
| YOLOv4/v5 | Better training tricks (mosaic augmentation, CSPDarknet backbone), huge usability improvements (v5 = PyTorch, pip-installable) |
| YOLOv7 | Further architecture + training efficiency gains |
| YOLOv8/v11 (Ultralytics) | Anchor-free head, unified library for detection **+ segmentation + pose + classification + tracking** |

## 7. What you'll actually run in this module
- `04_yolov8_inference.py` — load a pretrained YOLOv8 model and detect objects in an image in ~10 lines.
- `05_yolov8_custom_training.py` — fine-tune YOLOv8 on your own labeled dataset.
- `06_yolo_realtime_webcam.py` — run detection live on webcam frames.

## 8. Reading YOLO's output
When you run inference you'll see results like:
```
person 0.87  [x1=120, y1=45, x2=310, y2=400]
```
This means: **class** = person, **confidence** = 0.87 (the model is 87% sure),
and the **bounding box** corners in pixel coordinates. Anything below your
chosen confidence threshold (commonly 0.25-0.5) is discarded before display.




## `05_object_detection/04_yolov8_inference.py`


```python
"""
04 - YOLOv8 Inference
========================
Concept: run a pretrained YOLOv8 model (trained on the 80-class COCO
dataset) on an image and get bounding boxes, class names, and confidence
scores. This is the fastest way to get real object detection working.

Read 03_yolo_explained.md first if you haven't already.

Requirements:
    pip install ultralytics

Run:
    python 04_yolov8_inference.py [path/to/image.jpg]
(Downloads yolov8n.pt automatically on first run, ~6MB — the "nano" model,
fastest/smallest. Swap for yolov8s/m/l/x.pt for higher accuracy at the cost
of speed.)
"""
import sys


def main():
    try:
        from ultralytics import YOLO
    except ImportError:
        print("Install ultralytics first:  pip install ultralytics")
        return

    model = YOLO("yolov8n.pt")  # auto-downloads pretrained COCO weights

    path = sys.argv[1] if len(sys.argv) > 1 else \
        "https://ultralytics.com/images/bus.jpg"  # built-in sample image

    results = model(path, conf=0.4)  # conf = minimum confidence threshold to keep a detection

    for r in results:
        print(f"\nDetected {len(r.boxes)} object(s):")
        for box in r.boxes:
            cls_id = int(box.cls[0])
            cls_name = model.names[cls_id]
            conf = float(box.conf[0])
            x1, y1, x2, y2 = box.xyxy[0].tolist()
            print(f"  {cls_name:15s} conf={conf:.2f}  box=({x1:.0f},{y1:.0f},{x2:.0f},{y2:.0f})")

        r.save(filename="output_yolov8_detections.png")

    print("\nSaved output_yolov8_detections.png with boxes drawn")
    print("Tip: try yolov8s.pt / yolov8m.pt for better accuracy, or yolov8n.pt for max speed.")


if __name__ == "__main__":
    main()

```


## `05_object_detection/05_yolov8_custom_training.py`


```python
"""
05 - Training YOLOv8 on a Custom Dataset
============================================
Concept: pretrained YOLOv8 only knows the 80 COCO classes (person, car,
dog...). To detect YOUR objects (e.g. "defective part", "specific logo"),
you fine-tune it on your own labeled images.

Dataset format YOLO expects (Ultralytics/YOLO format):
    my_dataset/
        images/
            train/img1.jpg, img2.jpg, ...
            val/img10.jpg, ...
        labels/
            train/img1.txt, img2.txt, ...   <- one .txt per image
            val/img10.txt, ...
        data.yaml

Each label .txt file has one line per object:
    <class_id> <x_center> <y_center> <width> <height>
(all coordinates normalized 0-1, relative to image width/height)

data.yaml looks like:
    path: /absolute/path/to/my_dataset
    train: images/train
    val: images/val
    names:
      0: my_class_a
      1: my_class_b

Tools like Roboflow, CVAT, or LabelImg can generate this format for you from
raw images by drawing boxes visually — you rarely write these files by hand.

Requirements:
    pip install ultralytics

Run:
    python 05_yolov8_custom_training.py path/to/data.yaml
"""
import sys


def create_example_data_yaml(path="example_data.yaml"):
    content = """\
# EXAMPLE data.yaml — replace paths/names with your actual dataset
path: ./my_dataset
train: images/train
val: images/val
names:
  0: cat
  1: dog
"""
    with open(path, "w") as f:
        f.write(content)
    return path


def main():
    try:
        from ultralytics import YOLO
    except ImportError:
        print("Install ultralytics first:  pip install ultralytics")
        return

    if len(sys.argv) > 1:
        data_yaml = sys.argv[1]
    else:
        data_yaml = create_example_data_yaml()
        print(f"No data.yaml provided — wrote an EXAMPLE at {data_yaml}.")
        print("Edit it to point at your real labeled dataset, then re-run this script.")
        print("(Skipping actual training since this is just a template.)")
        return

    # Start from a pretrained checkpoint — this is transfer learning again,
    # exactly like 02_transfer_learning_resnet.py, just for detection instead
    # of classification.
    model = YOLO("yolov8n.pt")

    results = model.train(
        data=data_yaml,
        epochs=50,
        imgsz=640,
        batch=16,
        name="custom_yolov8_run",
    )

    print("\nTraining complete. Best weights saved under runs/detect/custom_yolov8_run/weights/best.pt")
    print("Use them for inference like this:")
    print('    from ultralytics import YOLO')
    print('    model = YOLO("runs/detect/custom_yolov8_run/weights/best.pt")')
    print('    model("your_test_image.jpg").show()')


if __name__ == "__main__":
    main()

```


## `05_object_detection/06_yolo_realtime_webcam.py`


```python
"""
06 - Real-Time YOLO Detection on Webcam
===========================================
Concept: apply YOLOv8 to every frame of a live video stream. This is the
same model as 04_yolov8_inference.py — the only new part is the video loop
that grabs frames, runs inference, and displays results in real time.

Requirements:
    pip install ultralytics opencv-python

Run:
    python 06_yolo_realtime_webcam.py
    python 06_yolo_realtime_webcam.py path/to/video.mp4   # run on a video file instead
"""
import sys
import time
import cv2


def main():
    try:
        from ultralytics import YOLO
    except ImportError:
        print("Install ultralytics first:  pip install ultralytics")
        return

    model = YOLO("yolov8n.pt")  # nano model for real-time speed

    source = sys.argv[1] if len(sys.argv) > 1 else 0  # 0 = default webcam
    cap = cv2.VideoCapture(source)
    if not cap.isOpened():
        print(f"Could not open video source: {source}")
        return

    print("Press 'q' to quit.")
    prev_time = time.time()

    while True:
        ret, frame = cap.read()
        if not ret:
            break

        results = model(frame, conf=0.4, verbose=False)
        annotated = results[0].plot()  # draws boxes + labels for you

        curr_time = time.time()
        fps = 1 / (curr_time - prev_time) if curr_time != prev_time else 0
        prev_time = curr_time
        cv2.putText(annotated, f"FPS: {fps:.1f}", (10, 30),
                    cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 255, 0), 2)

        cv2.imshow("YOLOv8 Real-Time Detection", annotated)
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    cap.release()
    cv2.destroyAllWindows()


if __name__ == "__main__":
    main()

```


## `05_object_detection/07_faster_rcnn_torchvision.py`


```python
"""
07 - Faster R-CNN via torchvision
=====================================
Concept: the two-stage alternative to YOLO (see 02_rcnn_family_explained.md).
torchvision ships a ready-to-use, COCO-pretrained Faster R-CNN so you can
compare its behavior/speed/accuracy directly against YOLOv8.

When to prefer Faster R-CNN over YOLO:
- Slightly higher accuracy on small objects in some benchmarks.
- When inference speed is not the bottleneck (e.g. offline batch processing).
YOLO usually wins on speed and is easier to deploy on edge devices/real-time video.

Requirements:
    pip install torchvision

Run:
    python 07_faster_rcnn_torchvision.py [path/to/image.jpg]
"""
import sys
import torch
import torchvision
from torchvision.transforms import functional as F
import cv2
import numpy as np

COCO_INSTANCE_CATEGORY_NAMES = [
    '__background__', 'person', 'bicycle', 'car', 'motorcycle', 'airplane', 'bus',
    'train', 'truck', 'boat', 'traffic light', 'fire hydrant', 'N/A', 'stop sign',
    'parking meter', 'bench', 'bird', 'cat', 'dog', 'horse', 'sheep', 'cow',
    'elephant', 'bear', 'zebra', 'giraffe', 'N/A', 'backpack', 'umbrella', 'N/A',
    'N/A', 'handbag', 'tie', 'suitcase', 'frisbee', 'skis', 'snowboard',
    'sports ball', 'kite', 'baseball bat', 'baseball glove', 'skateboard',
    'surfboard', 'tennis racket', 'bottle', 'N/A', 'wine glass', 'cup', 'fork',
    'knife', 'spoon', 'bowl', 'banana', 'apple', 'sandwich', 'orange', 'broccoli',
    'carrot', 'hot dog', 'pizza', 'donut', 'cake', 'chair', 'couch',
    'potted plant', 'bed', 'N/A', 'dining table', 'N/A', 'N/A', 'toilet', 'N/A',
    'tv', 'laptop', 'mouse', 'remote', 'keyboard', 'cell phone', 'microwave',
    'oven', 'toaster', 'sink', 'refrigerator', 'N/A', 'book', 'clock', 'vase',
    'scissors', 'teddy bear', 'hair drier', 'toothbrush'
]


def placeholder():
    img = np.full((300, 400, 3), 60, dtype=np.uint8)
    cv2.rectangle(img, (100, 80), (250, 260), (180, 180, 180), -1)
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img_bgr = cv2.imread(path) if path else placeholder()
    img_rgb = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2RGB)

    model = torchvision.models.detection.fasterrcnn_resnet50_fpn(
        weights=torchvision.models.detection.FasterRCNN_ResNet50_FPN_Weights.DEFAULT)
    model.eval()

    tensor_img = F.to_tensor(img_rgb)

    with torch.no_grad():
        predictions = model([tensor_img])[0]

    threshold = 0.6
    output = img_bgr.copy()
    n_kept = 0
    for box, label, score in zip(predictions["boxes"], predictions["labels"], predictions["scores"]):
        if score < threshold:
            continue
        n_kept += 1
        x1, y1, x2, y2 = box.int().tolist()
        class_name = COCO_INSTANCE_CATEGORY_NAMES[label.item()]
        cv2.rectangle(output, (x1, y1), (x2, y2), (0, 255, 0), 2)
        cv2.putText(output, f"{class_name} {score:.2f}", (x1, max(y1 - 5, 10)),
                    cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 255, 0), 1)
        print(f"{class_name}: {score:.2f} at ({x1},{y1},{x2},{y2})")

    cv2.imwrite("output_faster_rcnn_detections.png", output)
    print(f"\nKept {n_kept} detections above confidence {threshold}")
    print("Saved output_faster_rcnn_detections.png")
    print("Compare speed/output against 04_yolov8_inference.py on the same image!")


if __name__ == "__main__":
    main()

```


---

# Module 06_segmentation


## 06_segmentation — Module Overview


> File: `06_segmentation/README.md`

# 06 — Image Segmentation

Detection gives you a box around an object. Segmentation gives you the
**exact pixels** that belong to it — much finer-grained understanding,
needed for things like medical imaging, self-driving car lane/road masks,
and background removal.

| File | Concept |
|------|---------|
| `01_unet_semantic_segmentation.py` | U-Net architecture for semantic segmentation (every pixel gets a class label, but individual object instances aren't distinguished) |
| `02_mask_rcnn_instance_segmentation.py` | Mask R-CNN — detection AND per-instance pixel masks (distinguishes "dog #1" from "dog #2") |
| `03_yolov8_segmentation.py` | YOLOv8-seg — fast instance segmentation, same ecosystem as Module 05 |
| `04_segment_anything_sam.py` | Meta's Segment Anything Model (SAM) — a foundation model that segments ANY object from a point/box click, zero training required |

## Semantic vs Instance vs Panoptic segmentation
- **Semantic**: every pixel gets a class label (e.g. "road", "car", "sky") — doesn't separate multiple cars from each other.
- **Instance**: separates individual object instances (car #1 vs car #2), but usually ignores background "stuff" classes like sky/road.
- **Panoptic**: combines both — every pixel gets both a class label AND an instance ID.

## Requirements
```bash
pip install torch torchvision ultralytics segment-anything
```




## `06_segmentation/01_unet_semantic_segmentation.py`


```python
"""
01 - U-Net for Semantic Segmentation
========================================
Concept: U-Net (2015, originally for biomedical images) has an
"encoder-decoder" shape with skip connections:
- Encoder: repeatedly downsamples the image, extracting increasingly
  abstract features (like a normal CNN classifier).
- Decoder: repeatedly upsamples back to the original resolution, producing
  a full-resolution pixel-wise class prediction.
- Skip connections: copy feature maps from encoder to the matching decoder
  layer, so fine spatial detail (edges, boundaries) lost during downsampling
  is recovered — this is U-Net's key innovation and why segmentation
  boundaries come out sharp instead of blurry.

This script builds a small U-Net from scratch and trains it on a synthetic
segmentation task (mask = "which pixels are inside the circle").

Run:
    python 01_unet_semantic_segmentation.py
"""
import numpy as np
import cv2
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import Dataset, DataLoader


def conv_block(in_ch, out_ch):
    return nn.Sequential(
        nn.Conv2d(in_ch, out_ch, 3, padding=1), nn.ReLU(inplace=True),
        nn.Conv2d(out_ch, out_ch, 3, padding=1), nn.ReLU(inplace=True),
    )


class MiniUNet(nn.Module):
    """A small 2-level U-Net (real ones usually have 4-5 levels)."""
    def __init__(self):
        super().__init__()
        self.enc1 = conv_block(1, 16)
        self.pool1 = nn.MaxPool2d(2)
        self.enc2 = conv_block(16, 32)
        self.pool2 = nn.MaxPool2d(2)

        self.bottleneck = conv_block(32, 64)

        self.up2 = nn.ConvTranspose2d(64, 32, kernel_size=2, stride=2)
        self.dec2 = conv_block(64, 32)  # 64 = 32 (skip) + 32 (upsampled)
        self.up1 = nn.ConvTranspose2d(32, 16, kernel_size=2, stride=2)
        self.dec1 = conv_block(32, 16)  # 32 = 16 (skip) + 16 (upsampled)

        self.out_conv = nn.Conv2d(16, 1, kernel_size=1)

    def forward(self, x):
        e1 = self.enc1(x)
        e2 = self.enc2(self.pool1(e1))
        b = self.bottleneck(self.pool2(e2))

        d2 = self.up2(b)
        d2 = self.dec2(torch.cat([d2, e2], dim=1))  # <-- the skip connection
        d1 = self.up1(d2)
        d1 = self.dec1(torch.cat([d1, e1], dim=1))  # <-- another skip connection

        return self.out_conv(d1)  # raw logits, apply sigmoid for probability


class CircleMaskDataset(Dataset):
    def __init__(self, n=200, size=64):
        self.size = size
        self.n = n

    def __len__(self):
        return self.n

    def __getitem__(self, idx):
        size = self.size
        img = np.zeros((size, size), dtype=np.float32)
        mask = np.zeros((size, size), dtype=np.float32)
        cx, cy = np.random.randint(20, size - 20, 2)
        r = np.random.randint(10, 18)
        cv2.circle(img, (cx, cy), r, 1.0, -1)
        cv2.circle(mask, (cx, cy), r, 1.0, -1)
        img += np.random.normal(0, 0.05, img.shape).astype(np.float32)
        return torch.tensor(img).unsqueeze(0), torch.tensor(mask).unsqueeze(0)


def main():
    torch.manual_seed(0)
    train_ds = CircleMaskDataset(n=200)
    loader = DataLoader(train_ds, batch_size=8, shuffle=True)

    model = MiniUNet()
    optimizer = optim.Adam(model.parameters(), lr=1e-3)
    criterion = nn.BCEWithLogitsLoss()  # binary segmentation: circle vs background

    print("Training a mini U-Net to segment circles...")
    for epoch in range(8):
        total_loss = 0
        for imgs, masks in loader:
            optimizer.zero_grad()
            preds = model(imgs)
            loss = criterion(preds, masks)
            loss.backward()
            optimizer.step()
            total_loss += loss.item()
        print(f"Epoch {epoch+1}/8 - loss: {total_loss/len(loader):.4f}")

    # Visualize one prediction
    model.eval()
    test_img, test_mask = train_ds[0]
    with torch.no_grad():
        pred = torch.sigmoid(model(test_img.unsqueeze(0)))[0, 0].numpy()

    vis = np.hstack([test_img[0].numpy(), test_mask[0].numpy(), pred])
    cv2.imwrite("output_unet_segmentation.png", (vis * 255).astype(np.uint8))
    print("Saved output_unet_segmentation.png (left: input, middle: ground truth, right: prediction)")


if __name__ == "__main__":
    main()

```


## `06_segmentation/02_mask_rcnn_instance_segmentation.py`


```python
"""
02 - Mask R-CNN Instance Segmentation
=========================================
Concept: Mask R-CNN extends Faster R-CNN (Module 05) by adding a THIRD
output branch alongside "box" and "class": a small FCN (fully convolutional
network) that predicts a binary MASK for each detected object. This gives
you not just "there's a dog at this box" but the exact pixels of that dog —
and crucially, a SEPARATE mask per instance (dog #1 vs dog #2), unlike
plain semantic segmentation (previous file).

Requirements:
    pip install torchvision

Run:
    python 02_mask_rcnn_instance_segmentation.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np
import torch
import torchvision
from torchvision.transforms import functional as F


def placeholder():
    img = np.full((300, 400, 3), 60, dtype=np.uint8)
    cv2.circle(img, (130, 150), 70, (180, 180, 180), -1)
    cv2.circle(img, (280, 150), 70, (150, 150, 150), -1)
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img_bgr = cv2.imread(path) if path else placeholder()
    img_rgb = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2RGB)

    model = torchvision.models.detection.maskrcnn_resnet50_fpn(
        weights=torchvision.models.detection.MaskRCNN_ResNet50_FPN_Weights.DEFAULT)
    model.eval()

    tensor_img = F.to_tensor(img_rgb)
    with torch.no_grad():
        prediction = model([tensor_img])[0]

    threshold = 0.6
    output = img_bgr.copy()
    overlay = output.copy()
    kept = 0

    rng = np.random.default_rng(42)
    for mask, score, box in zip(prediction["masks"], prediction["scores"], prediction["boxes"]):
        if score < threshold:
            continue
        kept += 1
        color = rng.integers(0, 255, 3).tolist()
        binary_mask = (mask[0] > 0.5).numpy()
        overlay[binary_mask] = color

        x1, y1, x2, y2 = box.int().tolist()
        cv2.rectangle(output, (x1, y1), (x2, y2), color, 2)

    blended = cv2.addWeighted(output, 0.6, overlay, 0.4, 0)
    cv2.imwrite("output_mask_rcnn_instances.png", blended)
    print(f"Found {kept} instance(s) above confidence {threshold}, each with its own colored mask")
    print("Saved output_mask_rcnn_instances.png")


if __name__ == "__main__":
    main()

```


## `06_segmentation/03_yolov8_segmentation.py`


```python
"""
03 - YOLOv8 Instance Segmentation
=====================================
Concept: the same Ultralytics YOLOv8 framework from Module 05 also ships
segmentation model variants ("-seg"). It's dramatically faster than Mask
R-CNN while staying competitive on accuracy — the same one-stage speed
advantage YOLO has for detection carries over to segmentation.

Requirements:
    pip install ultralytics

Run:
    python 03_yolov8_segmentation.py [path/to/image.jpg]
"""
import sys


def main():
    try:
        from ultralytics import YOLO
    except ImportError:
        print("Install ultralytics first:  pip install ultralytics")
        return

    model = YOLO("yolov8n-seg.pt")  # segmentation variant, auto-downloads

    path = sys.argv[1] if len(sys.argv) > 1 else "https://ultralytics.com/images/bus.jpg"
    results = model(path, conf=0.4)

    for r in results:
        n_instances = 0 if r.masks is None else len(r.masks)
        print(f"Found {n_instances} segmented instance(s)")
        if r.boxes is not None:
            for box in r.boxes:
                cls_name = model.names[int(box.cls[0])]
                conf = float(box.conf[0])
                print(f"  {cls_name}: {conf:.2f}")
        r.save(filename="output_yolov8_segmentation.png")

    print("Saved output_yolov8_segmentation.png with instance masks drawn")


if __name__ == "__main__":
    main()

```


## `06_segmentation/04_segment_anything_sam.py`


```python
"""
04 - Segment Anything Model (SAM)
=====================================
Concept: SAM (Meta AI, 2023) is a "foundation model" for segmentation —
trained on 11 million images / 1 billion masks. Unlike U-Net/Mask R-CNN
which are trained for FIXED classes, SAM segments literally ANY object with
zero task-specific training, given a simple prompt:
- A point click (foreground point)
- A bounding box
- Or "segment everything" mode (automatic mask generation for the whole image)

This is why SAM is used as a labeling/annotation tool (auto-generate masks,
a human just corrects them) rather than a drop-in classifier replacement —
it doesn't tell you the object's CLASS, just its precise boundary.

Requirements:
    pip install segment-anything torch
    # Also download a checkpoint, e.g. sam_vit_b_01ec64.pth from:
    # https://github.com/facebookresearch/segment-anything#model-checkpoints

Run:
    python 04_segment_anything_sam.py path/to/image.jpg path/to/sam_checkpoint.pth
"""
import sys
import cv2
import numpy as np


def main():
    if len(sys.argv) < 3:
        print("Usage: python 04_segment_anything_sam.py <image.jpg> <sam_checkpoint.pth>")
        print("\nDownload a checkpoint first, e.g.:")
        print("  wget https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth")
        print("\n--- Conceptual code (what you'd run once you have both files) ---")
        print('''
from segment_anything import sam_model_registry, SamPredictor
import cv2

sam = sam_model_registry["vit_b"](checkpoint="sam_vit_b_01ec64.pth")
predictor = SamPredictor(sam)

image = cv2.cvtColor(cv2.imread("photo.jpg"), cv2.COLOR_BGR2RGB)
predictor.set_image(image)

# Prompt with a single foreground point (x, y) on the object you want segmented
input_point = np.array([[300, 200]])
input_label = np.array([1])  # 1 = foreground

masks, scores, _ = predictor.predict(
    point_coords=input_point, point_labels=input_label, multimask_output=True)
# masks[i] is a boolean array the same size as the image — the segmented object
''')
        return

    from segment_anything import sam_model_registry, SamPredictor

    image_path, checkpoint_path = sys.argv[1], sys.argv[2]
    image = cv2.cvtColor(cv2.imread(image_path), cv2.COLOR_BGR2RGB)

    sam = sam_model_registry["vit_b"](checkpoint=checkpoint_path)
    predictor = SamPredictor(sam)
    predictor.set_image(image)

    h, w = image.shape[:2]
    input_point = np.array([[w // 2, h // 2]])  # click the center of the image
    input_label = np.array([1])

    masks, scores, _ = predictor.predict(
        point_coords=input_point, point_labels=input_label, multimask_output=True)

    best_mask = masks[np.argmax(scores)]
    overlay = cv2.cvtColor(image, cv2.COLOR_RGB2BGR).copy()
    overlay[best_mask] = (0, 255, 0)
    blended = cv2.addWeighted(cv2.cvtColor(image, cv2.COLOR_RGB2BGR), 0.6, overlay, 0.4, 0)
    cv2.imwrite("output_sam_segmentation.png", blended)
    print(f"Best mask score: {scores.max():.3f}. Saved output_sam_segmentation.png")


if __name__ == "__main__":
    main()

```


---

# Module 07_advanced_architectures


## 07_advanced_architectures — Module Overview


> File: `07_advanced_architectures/README.md`

# 07 — Advanced Architectures

The current frontier: attention-based models, generative models, and
vision-language models that go beyond "classify/detect/segment fixed classes."

| File | Concept |
|------|---------|
| `01_vision_transformer_vit.py` | Vision Transformer (ViT) — applying the Transformer architecture (from NLP) to images |
| `02_dcgan_image_generation.py` | Generative Adversarial Network — two networks compete to generate realistic images from noise |
| `03_autoencoder_anomaly_detection.py` | Autoencoders — compress and reconstruct images; large reconstruction error flags anomalies |
| `04_clip_zero_shot_classification.py` | CLIP — classify images into categories you describe in plain text, with NO training |
| `05_diffusion_models_explained.md` | How Stable Diffusion / DALL-E-style models generate images from text |

## Requirements
```bash
pip install torch torchvision timm open-clip-torch
```




## `07_advanced_architectures/01_vision_transformer_vit.py`


```python
"""
01 - Vision Transformer (ViT)
=================================
Concept: CNNs process images with local convolutions (a 3x3 kernel only
sees its immediate neighborhood). Transformers, borrowed from NLP, instead
use SELF-ATTENTION, letting every part of the image directly relate to every
other part regardless of distance. ViT (2020) adapts this idea:

1. Split the image into fixed-size patches (e.g. 16x16 pixels each).
2. Flatten and linearly embed each patch (like turning each patch into a "word").
3. Add position embeddings (since attention has no innate sense of spatial order).
4. Feed the sequence of patch embeddings through a standard Transformer encoder.
5. A special [CLS] token's final representation is used for classification.

ViT needs MORE training data than CNNs to reach the same accuracy (it lacks
CNN's built-in assumptions like locality/translation-invariance), but scales
better and now underlies many state-of-the-art vision and vision-language systems.

Requirements:
    pip install timm torch torchvision

Run:
    python 01_vision_transformer_vit.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np
import torch


def placeholder():
    img = np.full((224, 224, 3), 100, dtype=np.uint8)
    cv2.circle(img, (112, 112), 60, (0, 180, 255), -1)
    return img


def main():
    try:
        import timm
        from torchvision import transforms
    except ImportError:
        print("Install timm first:  pip install timm")
        return

    path = sys.argv[1] if len(sys.argv) > 1 else None
    img_bgr = cv2.imread(path) if path else placeholder()
    img_rgb = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2RGB)

    model = timm.create_model("vit_base_patch16_224", pretrained=True)
    model.eval()

    preprocess = transforms.Compose([
        transforms.ToPILImage(),
        transforms.Resize((224, 224)),
        transforms.ToTensor(),
        transforms.Normalize(mean=[0.5, 0.5, 0.5], std=[0.5, 0.5, 0.5]),
    ])
    input_tensor = preprocess(img_rgb).unsqueeze(0)

    print(f"Patch size: 16x16 -> {(224 // 16) ** 2} patches fed into the Transformer")

    with torch.no_grad():
        logits = model(input_tensor)
    top5 = torch.topk(logits.softmax(dim=1), k=5)

    print("\nTop-5 ImageNet predictions (class indices — map to labels via imagenet_classes.txt):")
    for prob, idx in zip(top5.values[0], top5.indices[0]):
        print(f"  class {idx.item():4d}  confidence {prob.item():.3f}")

    print("\nCompare this architecture to the CNN in 04_deep_learning_basics/02_transfer_learning_resnet.py")
    print("— same task (ImageNet classification), fundamentally different mechanism.")


if __name__ == "__main__":
    main()

```


## `07_advanced_architectures/02_dcgan_image_generation.py`


```python
"""
02 - GAN Image Generation (DCGAN)
=====================================
Concept: a Generative Adversarial Network pits two networks against each
other in a minimax game:
- The GENERATOR takes random noise and tries to produce realistic images.
- The DISCRIMINATOR tries to tell real images from the generator's fakes.
They train together: the generator gets better at fooling the discriminator,
the discriminator gets better at catching fakes, and this competition
pushes the generator toward producing increasingly realistic images.

This script trains a small DCGAN (Deep Convolutional GAN) on a synthetic
dataset of simple shapes so you can watch the core training loop end-to-end
without needing a large real dataset or long training time.

Run:
    python 02_dcgan_image_generation.py
"""
import numpy as np
import cv2
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import Dataset, DataLoader

LATENT_DIM = 32
IMG_SIZE = 32


class Generator(nn.Module):
    def __init__(self):
        super().__init__()
        self.net = nn.Sequential(
            nn.Linear(LATENT_DIM, 128), nn.ReLU(),
            nn.Linear(128, 256), nn.ReLU(),
            nn.Linear(256, IMG_SIZE * IMG_SIZE), nn.Tanh(),
        )

    def forward(self, z):
        return self.net(z).view(-1, 1, IMG_SIZE, IMG_SIZE)


class Discriminator(nn.Module):
    def __init__(self):
        super().__init__()
        self.net = nn.Sequential(
            nn.Flatten(),
            nn.Linear(IMG_SIZE * IMG_SIZE, 256), nn.LeakyReLU(0.2),
            nn.Linear(256, 128), nn.LeakyReLU(0.2),
            nn.Linear(128, 1), nn.Sigmoid(),
        )

    def forward(self, x):
        return self.net(x)


class CircleDataset(Dataset):
    """Real images the discriminator learns from: circles of varying size/position."""
    def __init__(self, n=500):
        self.n = n

    def __len__(self):
        return self.n

    def __getitem__(self, idx):
        img = np.zeros((IMG_SIZE, IMG_SIZE), dtype=np.float32)
        cx, cy = np.random.randint(10, IMG_SIZE - 10, 2)
        r = np.random.randint(5, 10)
        cv2.circle(img, (cx, cy), r, 1.0, -1)
        img = img * 2 - 1  # scale to [-1, 1] to match Generator's Tanh output
        return torch.tensor(img).unsqueeze(0)


def main():
    torch.manual_seed(0)
    dataset = CircleDataset()
    loader = DataLoader(dataset, batch_size=32, shuffle=True)

    G, D = Generator(), Discriminator()
    opt_g = optim.Adam(G.parameters(), lr=2e-4)
    opt_d = optim.Adam(D.parameters(), lr=2e-4)
    criterion = nn.BCELoss()

    print("Training a tiny GAN to generate circle-like images...")
    for epoch in range(15):
        g_losses, d_losses = [], []
        for real_imgs in loader:
            batch_size = real_imgs.size(0)
            real_labels = torch.ones(batch_size, 1)
            fake_labels = torch.zeros(batch_size, 1)

            # --- Train Discriminator: tell real from fake ---
            z = torch.randn(batch_size, LATENT_DIM)
            fake_imgs = G(z)
            d_loss_real = criterion(D(real_imgs), real_labels)
            d_loss_fake = criterion(D(fake_imgs.detach()), fake_labels)
            d_loss = d_loss_real + d_loss_fake
            opt_d.zero_grad(); d_loss.backward(); opt_d.step()

            # --- Train Generator: fool the discriminator ---
            z = torch.randn(batch_size, LATENT_DIM)
            fake_imgs = G(z)
            g_loss = criterion(D(fake_imgs), real_labels)  # wants D to say "real"!
            opt_g.zero_grad(); g_loss.backward(); opt_g.step()

            g_losses.append(g_loss.item()); d_losses.append(d_loss.item())

        print(f"Epoch {epoch+1}/15 - G loss: {np.mean(g_losses):.3f}  D loss: {np.mean(d_losses):.3f}")

    # Generate and save a grid of sample outputs
    G.eval()
    with torch.no_grad():
        z = torch.randn(16, LATENT_DIM)
        samples = ((G(z) + 1) / 2 * 255).clamp(0, 255).byte().numpy()

    grid = np.zeros((IMG_SIZE * 4, IMG_SIZE * 4), dtype=np.uint8)
    for i in range(16):
        r, c = i // 4, i % 4
        grid[r*IMG_SIZE:(r+1)*IMG_SIZE, c*IMG_SIZE:(c+1)*IMG_SIZE] = samples[i, 0]

    cv2.imwrite("output_gan_generated_samples.png", grid)
    print("Saved output_gan_generated_samples.png — a 4x4 grid of GENERATED (fake) circle images")
    print("A real-world GAN (e.g. StyleGAN) uses the exact same adversarial idea at a much larger scale.")


if __name__ == "__main__":
    main()

```


## `07_advanced_architectures/03_autoencoder_anomaly_detection.py`


```python
"""
03 - Autoencoder for Anomaly Detection
==========================================
Concept: an autoencoder learns to COMPRESS an image into a small latent
vector (encoder) and then RECONSTRUCT it back (decoder), trained only on
"normal" data. Because it has only ever seen normal examples, it becomes
very good at reconstructing normal patterns but POOR at reconstructing
anomalies it's never seen — so a high reconstruction error signals "this
looks abnormal." Used heavily in manufacturing defect detection, medical
imaging anomaly flagging, and fraud-pattern detection on images.

Run:
    python 03_autoencoder_anomaly_detection.py
"""
import numpy as np
import cv2
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import Dataset, DataLoader

IMG_SIZE = 32


class Autoencoder(nn.Module):
    def __init__(self):
        super().__init__()
        self.encoder = nn.Sequential(
            nn.Conv2d(1, 16, 3, stride=2, padding=1), nn.ReLU(),   # 32->16
            nn.Conv2d(16, 32, 3, stride=2, padding=1), nn.ReLU(),  # 16->8
        )
        self.decoder = nn.Sequential(
            nn.ConvTranspose2d(32, 16, 3, stride=2, padding=1, output_padding=1), nn.ReLU(),  # 8->16
            nn.ConvTranspose2d(16, 1, 3, stride=2, padding=1, output_padding=1), nn.Sigmoid(),  # 16->32
        )

    def forward(self, x):
        return self.decoder(self.encoder(x))


class NormalCirclesDataset(Dataset):
    """'Normal' data: clean circles, always roughly centered."""
    def __init__(self, n=300):
        self.n = n

    def __len__(self):
        return self.n

    def __getitem__(self, idx):
        img = np.zeros((IMG_SIZE, IMG_SIZE), dtype=np.float32)
        cx = IMG_SIZE // 2 + np.random.randint(-3, 3)
        cy = IMG_SIZE // 2 + np.random.randint(-3, 3)
        cv2.circle(img, (cx, cy), 10, 1.0, -1)
        return torch.tensor(img).unsqueeze(0)


def make_anomaly():
    """'Abnormal' data: a shape the model has never seen — a star-ish blob off-center."""
    img = np.zeros((IMG_SIZE, IMG_SIZE), dtype=np.float32)
    pts = np.array([[5, 25], [15, 5], [25, 28], [8, 12], [27, 12]])
    cv2.fillPoly(img, [pts], 1.0)
    return torch.tensor(img).unsqueeze(0)


def main():
    torch.manual_seed(0)
    train_ds = NormalCirclesDataset()
    loader = DataLoader(train_ds, batch_size=16, shuffle=True)

    model = Autoencoder()
    optimizer = optim.Adam(model.parameters(), lr=1e-3)
    criterion = nn.MSELoss()

    print("Training autoencoder ONLY on normal (centered circle) images...")
    for epoch in range(15):
        total_loss = 0
        for imgs in loader:
            optimizer.zero_grad()
            recon = model(imgs)
            loss = criterion(recon, imgs)
            loss.backward()
            optimizer.step()
            total_loss += loss.item()
        print(f"Epoch {epoch+1}/15 - reconstruction loss: {total_loss/len(loader):.5f}")

    model.eval()
    with torch.no_grad():
        # Test on a NORMAL sample
        normal_sample = train_ds[0].unsqueeze(0)
        normal_recon = model(normal_sample)
        normal_error = criterion(normal_recon, normal_sample).item()

        # Test on an ANOMALY the model never trained on
        anomaly_sample = make_anomaly().unsqueeze(0)
        anomaly_recon = model(anomaly_sample)
        anomaly_error = criterion(anomaly_recon, anomaly_sample).item()

    print(f"\nReconstruction error on NORMAL sample:  {normal_error:.5f}")
    print(f"Reconstruction error on ANOMALY sample: {anomaly_error:.5f}")
    print(f"\n{'✓ Anomaly correctly flagged!' if anomaly_error > normal_error * 2 else 'Try training longer for a clearer gap.'}")

    combined = np.hstack([
        normal_sample[0, 0].numpy(), normal_recon[0, 0].numpy(),
        anomaly_sample[0, 0].numpy(), anomaly_recon[0, 0].numpy(),
    ])
    cv2.imwrite("output_autoencoder_comparison.png", (combined * 255).astype(np.uint8))
    print("Saved output_autoencoder_comparison.png (normal in / normal recon / anomaly in / anomaly recon)")


if __name__ == "__main__":
    main()

```


## `07_advanced_architectures/04_clip_zero_shot_classification.py`


```python
"""
04 - CLIP Zero-Shot Classification
======================================
Concept: CLIP (OpenAI, 2021) is trained on 400 million (image, text caption)
pairs from the internet, learning a SHARED embedding space where matching
images and text descriptions land close together. This lets you classify an
image into categories YOU write in plain English at inference time — with
ZERO training examples for those specific categories ("zero-shot").

How it works:
1. Encode the image into an embedding vector using CLIP's image encoder.
2. Encode each candidate text label (e.g. "a photo of a dog") into an
   embedding vector using CLIP's text encoder.
3. Compute cosine similarity between the image embedding and each text
   embedding — the highest similarity wins.

This is the foundation behind many modern "open vocabulary" vision systems
that aren't limited to a fixed list of trained classes.

Requirements:
    pip install open-clip-torch torch pillow

Run:
    python 04_clip_zero_shot_classification.py [path/to/image.jpg] [label1] [label2] ...
"""
import sys
import cv2
import numpy as np
from PIL import Image


def placeholder():
    arr = np.full((224, 224, 3), 30, dtype=np.uint8)
    cv2.circle(arr, (112, 90), 50, (0, 180, 255), -1)   # a "sun"-like shape
    cv2.rectangle(arr, (30, 160), (194, 210), (60, 120, 40), -1)  # "grass"
    return Image.fromarray(cv2.cvtColor(arr, cv2.COLOR_BGR2RGB))


def main():
    try:
        import open_clip
        import torch
    except ImportError:
        print("Install open-clip-torch first:  pip install open-clip-torch")
        return

    args = sys.argv[1:]
    image_path = None
    labels = args
    if args and (args[0].endswith((".jpg", ".png", ".jpeg"))):
        image_path = args[0]
        labels = args[1:]

    if not labels:
        labels = ["a sunny landscape", "a dog", "a city street", "a plate of food"]

    img = Image.open(image_path).convert("RGB") if image_path else placeholder()

    model, _, preprocess = open_clip.create_model_and_transforms(
        "ViT-B-32", pretrained="openai")
    tokenizer = open_clip.get_tokenizer("ViT-B-32")
    model.eval()

    image_input = preprocess(img).unsqueeze(0)
    text_inputs = tokenizer([f"a photo of {label}" for label in labels])

    with torch.no_grad():
        image_features = model.encode_image(image_input)
        text_features = model.encode_text(text_inputs)
        image_features /= image_features.norm(dim=-1, keepdim=True)
        text_features /= text_features.norm(dim=-1, keepdim=True)
        similarity = (100.0 * image_features @ text_features.T).softmax(dim=-1)

    print("Zero-shot classification results (no training on these specific labels!):")
    for label, score in sorted(zip(labels, similarity[0].tolist()), key=lambda x: -x[1]):
        print(f"  {label:30s} {score*100:.1f}%")

    print("\nTry passing your own labels: python 04_clip_zero_shot_classification.py photo.jpg \"a cat\" \"a car\" \"a tree\"")


if __name__ == "__main__":
    main()

```


> File: `07_advanced_architectures/05_diffusion_models_explained.md`

# Diffusion Models Explained (Stable Diffusion, DALL-E 2/3, Midjourney)

Diffusion models are the technology behind today's best text-to-image
generators. They work very differently from the GAN in `02_dcgan_image_generation.py`.

## The core idea: learn to reverse noise
1. **Forward process (training only):** take a real image and gradually add
   random Gaussian noise over many steps (e.g. 1000 steps) until it becomes
   pure static/noise.
2. **Reverse process (what the model learns):** train a neural network
   (usually a U-Net — see `06_segmentation/01_unet_semantic_segmentation.py`)
   to predict and remove a *small amount* of noise at each step, going backward.
3. **Generation (inference):** start from pure random noise and repeatedly
   apply the trained "denoising" network, step by step, until a clean,
   coherent image emerges.

## Why this works better than GANs for many use cases
- GANs can suffer from unstable training and "mode collapse" (generating only
  a limited variety of outputs).
- Diffusion models train more stably (simple regression loss: "how much noise
  did I add? predict it") and tend to produce more diverse, higher-fidelity outputs.
- Trade-off: diffusion models are much SLOWER to generate from (many denoising
  steps) compared to a GAN's single forward pass — though techniques like DDIM
  and distillation have cut this down enormously (some models now do it in 1-4 steps).

## Adding text control (text-to-image)
Models like Stable Diffusion condition the denoising U-Net on a text prompt's
embedding (produced by a text encoder like CLIP's, from the previous file!) at
every denoising step, via cross-attention layers inside the U-Net. This is how
"a photo of an astronaut riding a horse" steers the noise-removal process
toward an image matching that description.

## Where this connects to the rest of this repo
- The denoising network is a U-Net (Module 06).
- Text conditioning reuses CLIP-style text/image embeddings (previous file).
- The overall generative goal mirrors GANs (this module) but with a
  fundamentally different, more stable training mechanism.

Building a full diffusion model from scratch is beyond a "sample script,"
but the popular `diffusers` library (Hugging Face) lets you experiment with
pretrained diffusion models in a few lines:

```python
# pip install diffusers transformers accelerate
from diffusers import StableDiffusionPipeline
import torch

pipe = StableDiffusionPipeline.from_pretrained(
    "runwayml/stable-diffusion-v1-5", torch_dtype=torch.float16
).to("cuda")

image = pipe("a photo of an astronaut riding a horse").images[0]
image.save("output.png")
```




---

# Module 08_tracking_and_video


## 08_tracking_and_video — Module Overview


> File: `08_tracking_and_video/README.md`

# 08 — Tracking & Video

Detection tells you WHAT and WHERE in a single frame. Tracking maintains a
consistent identity for each object ACROSS frames — essential for counting
people, analyzing sports footage, or following a specific vehicle.

| File | Concept |
|------|---------|
| `01_opencv_object_tracking.py` | OpenCV's built-in single-object trackers (CSRT, KCF) |
| `02_yolo_deepsort_tracking.py` | Multi-object tracking: YOLO detects, DeepSORT maintains identity across frames |
| `03_pose_estimation_mediapipe.py` | Human pose/skeleton estimation (33 body landmarks) with MediaPipe |

## Detection vs Tracking
- **Detection** (Module 05) answers "what objects are in THIS frame?" — recomputed from scratch every frame.
- **Tracking** answers "is this the SAME object I saw 10 frames ago?" — it assigns and maintains a persistent ID.
Most production video pipelines combine both: detect every frame (or every N frames), track between detections.

## Requirements
```bash
pip install ultralytics deep-sort-realtime mediapipe
```




## `08_tracking_and_video/01_opencv_object_tracking.py`


```python
"""
01 - OpenCV Built-in Object Trackers
========================================
Concept: given a bounding box in the FIRST frame (usually from a detector
or manual selection), a tracker predicts where that same object moves to in
every subsequent frame — without re-running detection each time. Much
cheaper than re-detecting every frame.

- CSRT: more accurate, handles some occlusion/scale change, slower.
- KCF: faster, less robust to occlusion/fast motion.

Run:
    python 01_opencv_object_tracking.py
(Generates a synthetic moving-object video automatically.)
"""
import cv2
import numpy as np


def synthetic_video(n_frames=40):
    frames = []
    for i in range(n_frames):
        frame = np.full((300, 400, 3), 30, dtype=np.uint8)
        x = 20 + int(15 * i * (1 + 0.3 * np.sin(i / 5)))
        y = 130 + int(30 * np.sin(i / 8))
        cv2.rectangle(frame, (x, y), (x + 50, y + 50), (0, 200, 255), -1)
        frames.append(frame)
    return frames


def main():
    frames = synthetic_video()

    # Initialize tracker on the first frame's known bounding box
    tracker = cv2.legacy.TrackerCSRT_create() if hasattr(cv2, "legacy") else cv2.TrackerCSRT_create()
    init_bbox = (20, 130, 50, 50)  # (x, y, w, h) — normally comes from a detector like YOLO
    tracker.init(frames[0], init_bbox)

    output_frames = []
    successes = 0
    for frame in frames[1:]:
        success, bbox = tracker.update(frame)
        vis = frame.copy()
        if success:
            successes += 1
            x, y, w, h = [int(v) for v in bbox]
            cv2.rectangle(vis, (x, y), (x + w, y + h), (0, 255, 0), 2)
        else:
            cv2.putText(vis, "TRACKING LOST", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 0.7, (0, 0, 255), 2)
        output_frames.append(vis)

    print(f"Tracker succeeded on {successes}/{len(frames)-1} frames")

    # Save a few sample frames as images (since we can't display a real video window here)
    for idx in [0, len(output_frames)//2, -1]:
        cv2.imwrite(f"output_tracking_frame_{idx if idx >= 0 else 'last'}.png", output_frames[idx])
    print("Saved sample tracking frames as PNGs. In a real app, display frames in a loop with cv2.imshow.")


if __name__ == "__main__":
    main()

```


## `08_tracking_and_video/02_yolo_deepsort_tracking.py`


```python
"""
02 - Multi-Object Tracking: YOLO + DeepSORT
================================================
Concept: combine a detector (YOLO, finds WHAT and WHERE every frame) with a
tracker (DeepSORT, decides which detection in this frame corresponds to
which object seen in previous frames). DeepSORT does this using:
1. Motion prediction (a Kalman filter estimates where each tracked object
   SHOULD be this frame, based on its velocity).
2. Appearance matching (a small embedding network compares visual
   similarity, helping re-identify objects after brief occlusion).

This is exactly how real-world people-counting, vehicle-counting, and
sports-analytics systems are built (see also projects/people_counting_yolo/).

Requirements:
    pip install ultralytics deep-sort-realtime

Run:
    python 02_yolo_deepsort_tracking.py [path/to/video.mp4]
(Uses webcam if no path given.)
"""
import sys
import cv2


def main():
    try:
        from ultralytics import YOLO
        from deep_sort_realtime.deepsort_tracker import DeepSort
    except ImportError:
        print("Install requirements first:  pip install ultralytics deep-sort-realtime")
        return

    model = YOLO("yolov8n.pt")
    tracker = DeepSort(max_age=30)  # keep a track alive up to 30 frames without a matching detection

    source = sys.argv[1] if len(sys.argv) > 1 else 0
    cap = cv2.VideoCapture(source)
    if not cap.isOpened():
        print(f"Could not open source: {source}")
        return

    print("Press 'q' to quit.")
    while True:
        ret, frame = cap.read()
        if not ret:
            break

        results = model(frame, conf=0.4, classes=[0], verbose=False)  # class 0 = person, in COCO

        detections = []
        for box in results[0].boxes:
            x1, y1, x2, y2 = box.xyxy[0].tolist()
            conf = float(box.conf[0])
            detections.append(([x1, y1, x2 - x1, y2 - y1], conf, "person"))

        tracks = tracker.update_tracks(detections, frame=frame)

        for track in tracks:
            if not track.is_confirmed():
                continue
            track_id = track.track_id
            x1, y1, x2, y2 = [int(v) for v in track.to_ltrb()]
            cv2.rectangle(frame, (x1, y1), (x2, y2), (0, 255, 0), 2)
            cv2.putText(frame, f"ID {track_id}", (x1, y1 - 10),
                        cv2.FONT_HERSHEY_SIMPLEX, 0.6, (0, 255, 0), 2)

        cv2.imshow("YOLO + DeepSORT Multi-Object Tracking", frame)
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    cap.release()
    cv2.destroyAllWindows()


if __name__ == "__main__":
    main()

```


## `08_tracking_and_video/03_pose_estimation_mediapipe.py`


```python
"""
03 - Human Pose Estimation with MediaPipe
=============================================
Concept: pose estimation locates specific keypoints on a human body (nose,
shoulders, elbows, wrists, hips, knees, ankles — 33 landmarks in MediaPipe's
model) instead of just a bounding box. This enables fitness apps (rep
counting, form checking), sign language recognition, and gesture control.

Under the hood, MediaPipe's pose model is itself a CNN trained to regress
landmark (x, y, z, visibility) coordinates directly from an image crop of a
detected person.

Requirements:
    pip install mediapipe opencv-python

Run:
    python 03_pose_estimation_mediapipe.py [path/to/image_or_video.jpg]
    python 03_pose_estimation_mediapipe.py --webcam
"""
import sys
import cv2


def main():
    try:
        import mediapipe as mp
    except ImportError:
        print("Install mediapipe first:  pip install mediapipe")
        return

    mp_pose = mp.solutions.pose
    mp_drawing = mp.solutions.drawing_utils

    if "--webcam" in sys.argv:
        cap = cv2.VideoCapture(0)
        with mp_pose.Pose(min_detection_confidence=0.5, min_tracking_confidence=0.5) as pose:
            print("Press 'q' to quit.")
            while True:
                ret, frame = cap.read()
                if not ret:
                    break
                rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
                results = pose.process(rgb)
                if results.pose_landmarks:
                    mp_drawing.draw_landmarks(frame, results.pose_landmarks, mp_pose.POSE_CONNECTIONS)
                cv2.imshow("MediaPipe Pose Estimation", frame)
                if cv2.waitKey(1) & 0xFF == ord('q'):
                    break
        cap.release()
        cv2.destroyAllWindows()
        return

    path = sys.argv[1] if len(sys.argv) > 1 else None
    if not path:
        print("Provide an image with a visible person, or use --webcam")
        print("Usage: python 03_pose_estimation_mediapipe.py photo.jpg")
        return

    img = cv2.imread(path)
    rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    with mp_pose.Pose(static_image_mode=True, min_detection_confidence=0.5) as pose:
        results = pose.process(rgb)

    if results.pose_landmarks:
        mp_drawing.draw_landmarks(img, results.pose_landmarks, mp_pose.POSE_CONNECTIONS)
        print(f"Detected {len(results.pose_landmarks.landmark)} body landmarks")
        cv2.imwrite("output_pose_estimation.png", img)
        print("Saved output_pose_estimation.png")
    else:
        print("No person detected in the image.")


if __name__ == "__main__":
    main()

```


---

# Module 09_3d_and_depth


## 09_3d_and_depth — Module Overview


> File: `09_3d_and_depth/README.md`

# 09 — 3D & Depth Vision

Everything so far worked in 2D pixel space. This module recovers 3D
structure — "how far away is this?" — from ordinary camera images.

| File | Concept |
|------|---------|
| `01_stereo_depth_estimation.py` | Classic stereo vision: two cameras + triangulation = a depth map |
| `02_monocular_depth_midas.py` | Deep-learning monocular depth: estimate depth from a SINGLE image using MiDaS |

## Stereo vs Monocular depth
- **Stereo** (two cameras, like human eyes): geometrically exact triangulation, but needs a calibrated camera pair (see Module 02's camera calibration) and a stereo rig.
- **Monocular** (one camera, deep learning): a neural network trained on huge datasets learns to infer relative depth cues (size, occlusion, perspective) from a single image — works with any regular camera/photo, but gives *relative*, not exact, depth by default.

## Requirements
```bash
pip install torch torchvision opencv-python
```




## `09_3d_and_depth/01_stereo_depth_estimation.py`


```python
"""
01 - Stereo Depth Estimation
================================
Concept: two cameras a known distance apart ("baseline") see the same scene
from slightly different angles. An object's horizontal pixel shift between
the left and right image ("disparity") is INVERSELY proportional to its
distance from the camera — close objects shift a lot, far objects barely
shift. This is exactly how human depth perception (binocular vision) works.

    depth = (focal_length * baseline) / disparity

OpenCV's StereoSGBM (Semi-Global Block Matching) computes a disparity map by
finding matching patches between the left/right images.

Run:
    python 01_stereo_depth_estimation.py
(Generates a synthetic stereo pair automatically — a near and far object at
different simulated disparities.)
"""
import cv2
import numpy as np


def make_stereo_pair():
    """Simulates a stereo pair: same scene, objects shifted based on 'depth'."""
    left = np.full((300, 400), 60, dtype=np.uint8)
    right = np.full((300, 400), 60, dtype=np.uint8)

    # Near object -> large disparity (shifts a lot between L/R)
    cv2.rectangle(left, (100, 100), (160, 160), 200, -1)
    cv2.rectangle(right, (85, 100), (145, 160), 200, -1)  # shifted 15px = near

    # Far object -> small disparity (barely shifts)
    cv2.circle(left, (300, 200), 30, 150, -1)
    cv2.circle(right, (295, 200), 30, 150, -1)  # shifted 5px = far

    return left, right


def main():
    left, right = make_stereo_pair()
    cv2.imwrite("output_stereo_left.png", left)
    cv2.imwrite("output_stereo_right.png", right)

    stereo = cv2.StereoSGBM_create(
        minDisparity=0,
        numDisparities=64,   # must be divisible by 16
        blockSize=7,
        P1=8 * 1 * 7 ** 2,
        P2=32 * 1 * 7 ** 2,
        disp12MaxDiff=1,
        uniquenessRatio=10,
        speckleWindowSize=100,
        speckleRange=32,
    )

    disparity = stereo.compute(left, right).astype(np.float32) / 16.0
    disparity_normalized = cv2.normalize(disparity, None, 0, 255, cv2.NORM_MINMAX).astype(np.uint8)
    disparity_color = cv2.applyColorMap(disparity_normalized, cv2.COLORMAP_JET)

    cv2.imwrite("output_disparity_map.png", disparity_color)
    print("Saved output_stereo_left.png, output_stereo_right.png, output_disparity_map.png")
    print("In the disparity map: brighter/warmer colors = closer objects (larger disparity)")
    print("\nWith a REAL calibrated stereo rig you'd convert disparity to actual metric depth via:")
    print("    depth = (focal_length_px * baseline_mm) / disparity")


if __name__ == "__main__":
    main()

```


## `09_3d_and_depth/02_monocular_depth_midas.py`


```python
"""
02 - Monocular Depth Estimation (MiDaS)
============================================
Concept: MiDaS (Mixed Dataset Training for Robust Monocular Depth) is a
neural network trained on many diverse datasets to predict a relative depth
map from a SINGLE ordinary photo — no stereo rig or calibration needed. It
learns the same depth cues humans use with one eye closed: relative object
size, occlusion (what's in front of what), texture gradients, and perspective.

Requirements:
    pip install torch torchvision opencv-python timm

Run:
    python 02_monocular_depth_midas.py [path/to/image.jpg]
"""
import sys
import cv2
import numpy as np
import torch


def placeholder():
    img = np.full((300, 400, 3), 90, dtype=np.uint8)
    cv2.rectangle(img, (250, 180), (380, 280), (40, 40, 40), -1)   # "near" object, lower/larger
    cv2.rectangle(img, (150, 100), (200, 140), (150, 150, 150), -1)  # "far" object, smaller/higher
    return img


def main():
    path = sys.argv[1] if len(sys.argv) > 1 else None
    img_bgr = cv2.imread(path) if path else placeholder()
    img_rgb = cv2.cvtColor(img_bgr, cv2.COLOR_BGR2RGB)

    print("Loading MiDaS (downloads pretrained weights on first run)...")
    model_type = "MiDaS_small"  # fastest variant; use "DPT_Large" for best quality
    midas = torch.hub.load("intel-isl/MiDaS", model_type)
    midas.eval()

    midas_transforms = torch.hub.load("intel-isl/MiDaS", "transforms")
    transform = midas_transforms.small_transform if "small" in model_type else midas_transforms.dpt_transform

    input_batch = transform(img_rgb)

    with torch.no_grad():
        prediction = midas(input_batch)
        prediction = torch.nn.functional.interpolate(
            prediction.unsqueeze(1), size=img_rgb.shape[:2], mode="bicubic", align_corners=False
        ).squeeze()

    depth_map = prediction.cpu().numpy()
    depth_normalized = cv2.normalize(depth_map, None, 0, 255, cv2.NORM_MINMAX).astype(np.uint8)
    depth_color = cv2.applyColorMap(depth_normalized, cv2.COLORMAP_INFERNO)

    cv2.imwrite("output_monocular_depth_map.png", depth_color)
    print("Saved output_monocular_depth_map.png")
    print("Brighter = closer to the camera (relative depth, not metric distance).")
    print("\nCompare this single-image result against the two-image stereo approach in the previous file!")


if __name__ == "__main__":
    main()

```


---

# Module 10_deployment


## 10_deployment — Module Overview


> File: `10_deployment/README.md`

# 10 — Deployment

A model that only runs in your Python script isn't useful to end users. This
module covers the three most common ways to ship a CV model: portable export
formats, a backend API, and an interactive demo app.

| File | Concept |
|------|---------|
| `01_onnx_export_inference.py` | Export a PyTorch model to ONNX (framework-independent) and run it with ONNX Runtime |
| `02_flask_api_deployment.py` | Wrap a model in a Flask REST API so any client (web, mobile) can send an image and get predictions |
| `03_streamlit_cv_app.py` | Build an interactive drag-and-drop web demo with Streamlit — no frontend code needed |

## Why ONNX?
Training frameworks (PyTorch, TensorFlow) are great for research but not always ideal for production (large dependencies, slower CPU inference). ONNX (Open Neural Network Exchange) is a universal format: export once from PyTorch, then run it with ONNX Runtime, TensorRT, mobile runtimes, or in the browser — often significantly faster on CPU too.

## Requirements
```bash
pip install onnx onnxruntime flask streamlit torch torchvision
```




## `10_deployment/01_onnx_export_inference.py`


```python
"""
01 - Export to ONNX & Run Inference
=======================================
Concept: convert a trained PyTorch model into the ONNX format — a static
computation graph that can be run by many different runtimes (ONNX Runtime,
TensorRT, mobile/edge runtimes) often WITHOUT needing PyTorch installed at
all, and frequently faster on CPU.

Run:
    python 01_onnx_export_inference.py
"""
import numpy as np
import torch
import torch.nn as nn


class TinyClassifier(nn.Module):
    """Stand-in for any trained model — swap in your real trained CNN here."""
    def __init__(self):
        super().__init__()
        self.net = nn.Sequential(
            nn.Conv2d(3, 8, 3, padding=1), nn.ReLU(), nn.AdaptiveAvgPool2d(1),
            nn.Flatten(), nn.Linear(8, 2)
        )

    def forward(self, x):
        return self.net(x)


def main():
    model = TinyClassifier()
    model.eval()

    dummy_input = torch.randn(1, 3, 64, 64)
    onnx_path = "model.onnx"

    torch.onnx.export(
        model, dummy_input, onnx_path,
        input_names=["input"], output_names=["output"],
        dynamic_axes={"input": {0: "batch_size"}, "output": {0: "batch_size"}},
        opset_version=13,
    )
    print(f"Exported model to {onnx_path}")

    # --- Run inference with ONNX Runtime (does NOT require PyTorch at inference time) ---
    try:
        import onnxruntime as ort
    except ImportError:
        print("Install onnxruntime to test inference:  pip install onnxruntime")
        return

    session = ort.InferenceSession(onnx_path)
    test_input = np.random.randn(1, 3, 64, 64).astype(np.float32)

    # Sanity check: PyTorch and ONNX Runtime should give (nearly) identical results
    with torch.no_grad():
        torch_output = model(torch.tensor(test_input)).numpy()
    onnx_output = session.run(None, {"input": test_input})[0]

    print(f"PyTorch output:      {torch_output}")
    print(f"ONNX Runtime output: {onnx_output}")
    print(f"Match within tolerance: {np.allclose(torch_output, onnx_output, atol=1e-4)}")


if __name__ == "__main__":
    main()

```


## `10_deployment/02_flask_api_deployment.py`


```python
"""
02 - Serving a CV Model with Flask
======================================
Concept: wrap a trained model behind a REST API so any client (a website,
mobile app, or another backend service) can POST an image and get back
predictions as JSON — without needing Python or your model code at all.

Run:
    python 02_flask_api_deployment.py
Then, in another terminal:
    curl -X POST -F "image=@your_photo.jpg" http://localhost:5000/predict
"""
from flask import Flask, request, jsonify
import numpy as np
import cv2

app = Flask(__name__)

# In a real app, load your trained model / YOLO model ONCE here at startup,
# not per-request (loading is slow — you only want to pay that cost once):
#
#   from ultralytics import YOLO
#   model = YOLO("yolov8n.pt")


@app.route("/health", methods=["GET"])
def health():
    return jsonify({"status": "ok"})


@app.route("/predict", methods=["POST"])
def predict():
    if "image" not in request.files:
        return jsonify({"error": "No image file provided. Use form field name 'image'."}), 400

    file = request.files["image"]
    file_bytes = np.frombuffer(file.read(), np.uint8)
    img = cv2.imdecode(file_bytes, cv2.IMREAD_COLOR)

    if img is None:
        return jsonify({"error": "Could not decode image"}), 400

    # --- Replace this block with your real model inference ---
    # results = model(img)
    # predictions = [{"class": model.names[int(b.cls)], "confidence": float(b.conf)}
    #                for b in results[0].boxes]
    predictions = [{"class": "placeholder_object", "confidence": 0.93}]
    # -----------------------------------------------------------

    return jsonify({
        "image_shape": img.shape,
        "predictions": predictions,
    })


if __name__ == "__main__":
    print("Starting Flask server on http://localhost:5000")
    print("Test it with:")
    print('  curl -X POST -F "image=@your_photo.jpg" http://localhost:5000/predict')
    app.run(host="0.0.0.0", port=5000, debug=True)

```


## `10_deployment/03_streamlit_cv_app.py`


```python
"""
03 - Interactive Streamlit CV App
======================================
Concept: Streamlit turns a plain Python script into an interactive web app
with almost no frontend code — perfect for quickly demoing a CV model to
non-technical stakeholders (upload an image, see predictions instantly).

Run:
    streamlit run 03_streamlit_cv_app.py
(Opens automatically in your browser, usually at http://localhost:8501)
"""
import numpy as np
import cv2

try:
    import streamlit as st
except ImportError:
    print("Install streamlit first:  pip install streamlit")
    print("Then run with:  streamlit run 03_streamlit_cv_app.py")
    raise SystemExit


st.set_page_config(page_title="CV Demo App", layout="centered")
st.title("🖼️ Computer Vision Demo")
st.write("Upload an image and pick a technique from this repo to apply.")

uploaded_file = st.file_uploader("Choose an image...", type=["jpg", "jpeg", "png"])

technique = st.selectbox(
    "Choose a technique",
    ["Canny Edge Detection", "Grayscale", "Gaussian Blur", "Object Detection (YOLOv8)"],
)

if uploaded_file is not None:
    file_bytes = np.frombuffer(uploaded_file.read(), np.uint8)
    img = cv2.imdecode(file_bytes, cv2.IMREAD_COLOR)
    st.image(cv2.cvtColor(img, cv2.COLOR_BGR2RGB), caption="Original", use_container_width=True)

    if technique == "Canny Edge Detection":
        gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
        result = cv2.Canny(gray, 100, 200)
        st.image(result, caption="Canny Edges", use_container_width=True)

    elif technique == "Grayscale":
        result = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
        st.image(result, caption="Grayscale", use_container_width=True)

    elif technique == "Gaussian Blur":
        ksize = st.slider("Blur strength (odd number)", 1, 25, 7, step=2)
        result = cv2.GaussianBlur(img, (ksize, ksize), 0)
        st.image(cv2.cvtColor(result, cv2.COLOR_BGR2RGB), caption="Blurred", use_container_width=True)

    elif technique == "Object Detection (YOLOv8)":
        try:
            from ultralytics import YOLO
            model = YOLO("yolov8n.pt")
            results = model(img, conf=0.4)
            annotated = results[0].plot()
            st.image(cv2.cvtColor(annotated, cv2.COLOR_BGR2RGB),
                      caption="YOLOv8 Detections", use_container_width=True)
            for box in results[0].boxes:
                st.write(f"- {model.names[int(box.cls[0])]}: {float(box.conf[0]):.2f}")
        except ImportError:
            st.error("Install ultralytics first:  pip install ultralytics")
else:
    st.info("👆 Upload an image to get started.")

```


---

# Projects


## Projects Overview


> File: `projects/README.md`

# Projects — Putting It All Together

Small but complete end-to-end applications combining techniques from
multiple modules. Study these once you've gone through modules 01-10 to see
how the pieces fit together in a real workflow.

| Project | Combines |
|---------|----------|
| [face_eye_realtime_detector/](face_eye_realtime_detector/) | Module 03 (Haar Cascades) + webcam video loop |
| [people_counting_yolo/](people_counting_yolo/) | Module 05 (YOLO detection) + Module 08 (DeepSORT tracking) + line-crossing counting logic |

Each project folder has its own README with setup and run instructions.




## Project: face_eye_realtime_detector


> File: `projects/face_eye_realtime_detector/README.md`

# Project: Real-Time Face & Eye Detector

A complete, runnable webcam application using classical Haar Cascade
detectors (Module 03) — no GPU or deep learning framework required, runs
fast on any laptop/edge device.

## What it does
- Opens your webcam
- Detects faces every frame
- Detects eyes within each detected face
- Draws boxes and shows live FPS

## Run
```bash
pip install opencv-python
python app.py
```
Press `q` to quit.

## Extend this project
- Swap Haar Cascades for `../../05_object_detection/06_yolo_realtime_webcam.py`'s YOLO approach for more robust detection in varied lighting/angles.
- Add a simple mask/no-mask classifier on top of each detected face crop (see `04_deep_learning_basics/02_transfer_learning_resnet.py` for the transfer-learning recipe).




### `projects/face_eye_realtime_detector/app.py`


```python
"""
Real-Time Face & Eye Detector
=================================
Combines: Module 03 (Haar Cascade classical detection) + a live video loop.

Run:
    python app.py
Press 'q' to quit.
"""
import time
import cv2


def main():
    face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")
    eye_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_eye.xml")

    cap = cv2.VideoCapture(0)
    if not cap.isOpened():
        print("Could not open webcam. If running headless, this project needs a camera.")
        return

    print("Press 'q' to quit.")
    prev_time = time.time()

    while True:
        ret, frame = cap.read()
        if not ret:
            break

        gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
        faces = face_cascade.detectMultiScale(gray, 1.1, 5, minSize=(60, 60))

        for (x, y, w, h) in faces:
            cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 2)
            roi_gray = gray[y:y + h, x:x + w]
            roi_color = frame[y:y + h, x:x + w]
            eyes = eye_cascade.detectMultiScale(roi_gray)
            for (ex, ey, ew, eh) in eyes:
                cv2.rectangle(roi_color, (ex, ey), (ex + ew, ey + eh), (255, 0, 0), 2)

        curr_time = time.time()
        fps = 1 / (curr_time - prev_time) if curr_time != prev_time else 0
        prev_time = curr_time
        cv2.putText(frame, f"FPS: {fps:.1f}  Faces: {len(faces)}", (10, 30),
                    cv2.FONT_HERSHEY_SIMPLEX, 0.7, (0, 255, 0), 2)

        cv2.imshow("Real-Time Face & Eye Detector", frame)
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    cap.release()
    cv2.destroyAllWindows()


if __name__ == "__main__":
    main()

```


## Project: people_counting_yolo


> File: `projects/people_counting_yolo/README.md`

# Project: People Counting with YOLO + Tracking

A real-world computer vision application: count how many people cross a
line (e.g. entering/exiting a store, room, or venue) using YOLO detection
(Module 05) + DeepSORT tracking (Module 08) so each person is only counted
ONCE, not once per frame.

## Why tracking is essential here
If you just counted "number of person detections per frame" you'd wildly
overcount (the same person detected in 100 frames = 100 counts). Tracking
gives each person a persistent ID, so we only increment the counter the
FIRST time that ID crosses the line.

## Run
```bash
pip install ultralytics deep-sort-realtime opencv-python
python app.py path/to/video.mp4
python app.py --webcam
```
Press `q` to quit. The count is displayed live and printed at the end.

## Extend this project
- Add IN vs OUT counting by checking crossing DIRECTION, not just crossing.
- Swap the counting line for a counting polygon/zone (e.g. "people inside this area").
- Log timestamped events to a CSV for analytics dashboards.




### `projects/people_counting_yolo/app.py`


```python
"""
People Counting with YOLO + DeepSORT
========================================
Combines: Module 05 (YOLOv8 person detection) + Module 08 (DeepSORT tracking)
+ simple line-crossing counting logic.

Run:
    python app.py path/to/video.mp4
    python app.py --webcam

Requirements:
    pip install ultralytics deep-sort-realtime opencv-python
"""
import sys
import cv2

LINE_Y = 300  # horizontal counting line's y-coordinate (in pixels) — tune to your video


def main():
    try:
        from ultralytics import YOLO
        from deep_sort_realtime.deepsort_tracker import DeepSort
    except ImportError:
        print("Install requirements first:  pip install ultralytics deep-sort-realtime")
        return

    source = 0 if "--webcam" in sys.argv else (sys.argv[1] if len(sys.argv) > 1 else None)
    if source is None:
        print("Usage: python app.py path/to/video.mp4   OR   python app.py --webcam")
        return

    model = YOLO("yolov8n.pt")
    tracker = DeepSort(max_age=30)

    cap = cv2.VideoCapture(source)
    if not cap.isOpened():
        print(f"Could not open video source: {source}")
        return

    counted_ids = set()
    track_prev_y = {}  # remembers each track's previous y-position to detect crossing

    print("Press 'q' to quit.")
    while True:
        ret, frame = cap.read()
        if not ret:
            break

        results = model(frame, conf=0.4, classes=[0], verbose=False)  # class 0 = person
        detections = []
        for box in results[0].boxes:
            x1, y1, x2, y2 = box.xyxy[0].tolist()
            conf = float(box.conf[0])
            detections.append(([x1, y1, x2 - x1, y2 - y1], conf, "person"))

        tracks = tracker.update_tracks(detections, frame=frame)

        cv2.line(frame, (0, LINE_Y), (frame.shape[1], LINE_Y), (0, 0, 255), 2)

        for track in tracks:
            if not track.is_confirmed():
                continue
            track_id = track.track_id
            x1, y1, x2, y2 = [int(v) for v in track.to_ltrb()]
            center_y = (y1 + y2) // 2

            cv2.rectangle(frame, (x1, y1), (x2, y2), (0, 255, 0), 2)
            cv2.putText(frame, f"ID {track_id}", (x1, y1 - 10),
                        cv2.FONT_HERSHEY_SIMPLEX, 0.5, (0, 255, 0), 2)

            prev_y = track_prev_y.get(track_id)
            if prev_y is not None and track_id not in counted_ids:
                crossed = (prev_y < LINE_Y <= center_y) or (prev_y > LINE_Y >= center_y)
                if crossed:
                    counted_ids.add(track_id)
            track_prev_y[track_id] = center_y

        cv2.putText(frame, f"Count: {len(counted_ids)}", (10, 40),
                    cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 0), 2)

        cv2.imshow("People Counting", frame)
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    cap.release()
    cv2.destroyAllWindows()
    print(f"\nFinal count: {len(counted_ids)} people crossed the line")


if __name__ == "__main__":
    main()

```


---


# Pushing This to GitHub


> File: `GITHUB_SETUP.md`

# Pushing This Repo to GitHub

This project was generated as a ready-to-use folder. To publish it as your
own GitHub repository:

```bash
cd cv-learning-repo

git init
git add .
git commit -m "Initial commit: Computer Vision from Zero to Advanced"

# Create a new EMPTY repo on github.com first (no README/license, so it
# doesn't conflict), then:
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

## Recommended repo settings once it's live
- Add topics/tags: `computer-vision`, `opencv`, `yolo`, `pytorch`, `deep-learning`, `image-segmentation`
- Enable GitHub Pages if you want the READMEs browsable as a mini-site
- Add a `.gitignore` for Python (see below) so downloaded model weights and generated outputs don't get committed

## Suggested `.gitignore`
```
__pycache__/
*.pyc
*.pt
*.onnx
*.pth
output_*.png
runs/
venv/
.env
```
(Model weight files like `yolov8n.pt` are large and auto-downloadable — don't commit them; let each user's script re-download on first run.)
