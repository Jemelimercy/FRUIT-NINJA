# 🍎 AI Fruit-Ninja: Augmented Reality Edition 🍌

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=for-the-badge&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-007f00?style=for-the-badge&logo=google&logoColor=white)
![Pygame](https://img.shields.io/badge/pygame-373737?style=for-the-badge&logo=python&logoColor=green)

A high-performance Augmented Reality (AR) game where players slice fruits using real-time computer vision. This project leverages **MediaPipe's** hand-tracking landmarks to transform the user's index finger into a virtual blade.

## 🚀 Key Features
* **AR Immersion:** Overlays game assets (apples, bananas) directly onto the live webcam feed.
* **Red Skeleton Scanning:** Custom-styled Mediapipe hand landmarks to visualize tracking.
* **Infinite Gameplay:** Continuous scoring system with high-precision collision detection.
* **Juicy UI:** Semi-transparent HUD and particle-based fruit splatter effects.

## 📐 The Math: Precision Line-Segment Slicing
To prevent "ghost slices" (where a fast hand movement skips over a fruit between frames), I implemented a **Point-to-Line Segment distance algorithm**. 

Instead of checking if the finger is inside the fruit at a single moment, the game calculates the shortest distance from the fruit's center $P$ to the segment $\overline{AB}$ formed by the finger's position in the previous frame ($A$) and the current frame ($B$).

The distance $d$ is calculated using:
$$d = \frac{|(y_B - y_A)x_P - (x_B - x_A)y_P + x_B y_A - y_B x_A|}{\sqrt{(y_B - y_A)^2 + (x_B - x_A)^2}}$$

If $d < \text{fruit-radius}$, a slice is registered. This ensures 100% accuracy even during rapid swipes.



## 🛠️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/jemelimercy/FRUIT-NINJA.git](https://github.com/jemelimercy/FRUIT-NINJA.git)
   cd Fruit-Ninja
