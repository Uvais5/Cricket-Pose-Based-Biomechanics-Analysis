# Cricket-Pose-Based-Biomechanics-Analysis

## Overview
This project implements a computer vision–based sports analytics pipeline to analyze cricket movement patterns from video input. Using pose estimation and biomechanical metrics, the system extracts meaningful insights about an athlete’s lower-body and upper-body mechanics.

The solution follows the requirements outlined in the assignment PDF and focuses on clarity, correctness, and interpretability rather than model complexity.

---

## Pipeline Summary

1. **Video Input**
   - Side-view cricket video

2. **Pose Estimation**
   - YOLOv8 Pose model used to extract 2D human keypoints per frame

3. **Keypoint Processing**
   - Frame-wise extraction of joint coordinates
   - Stored in a structured Pandas DataFrame

4. **Joint Angle Computation**
   - Knee joint angle (hip–knee–ankle)
   - Elbow joint angle (shoulder–elbow–wrist)

5. **Movement Metrics Extraction**
   - Scalar biomechanical metrics derived from joint angle time series

6. **Visualization & Output**
   - Joint angle plots
   - Metrics exported for further analysis

---

## Technologies Used

- **Python 3**
- **YOLOv8 (Ultralytics)** – Pose estimation
- **OpenCV** – Video processing
- **NumPy** – Vector math and angle computation
- **Pandas** – Data handling and metric aggregation
- **Matplotlib** – Visualization

---

## Movement Metrics

The following movement metrics are computed:

### 1. Knee Range of Motion (ROM)
- Measures the total angular movement of the knee joint
- Indicates lower-body engagement and flexibility

### 2. Knee Stability Variance
- Measures variability in knee joint angle over time
- Higher values may indicate rapid motion or instability

### 3. Elbow Range of Motion
- Measures arm extension and flexion
- Relevant for cricket batting and bowling mechanics

### Sample Output

| Metric | Value |
|------|------|
| Knee Range of Motion | ~67.9° |
| Knee Stability Variance | ~357.9 |
| Elbow Range of Motion | ~89.9° |

---

## Visual Outputs

- **Knee Joint Angle Over Time**
  - Line plot showing knee angle variation across frames
  - Useful for identifying motion phases and instability

---

## Results Interpretation

The knee joint exhibits a moderate range of motion, indicating effective lower-body involvement during the movement. The observed stability variance reflects either rapid dynamic motion or noise introduced by single-view pose estimation, which is expected in 2D analysis.

The elbow range of motion suggests significant arm extension, aligning with typical cricket batting or bowling mechanics.

---

## Limitations

- The analysis is based on **2D pose estimation**, which lacks depth information.
- Occlusions and fast motion can introduce noise in keypoint detection.
- The model is not fine-tuned on cricket-specific data.

---

## Future Improvements

- Apply temporal smoothing to reduce pose jitter
- Use multi-view or 3D pose estimation for improved accuracy
- Extend metrics to include hip–shoulder separation or stride length
- Fine-tune pose models on cricket-specific datasets

---

## Conclusion

This project demonstrates how pose estimation combined with simple biomechanical metrics can be used to analyze cricket movement patterns using only video input. The approach is lightweight, interpretable, and suitable for real-world sports analytics applications.

---

## Repository Structure


