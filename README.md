# Non-Maximum Suppression (NMS) Algorithms Comparison

## Benchmark Results

### 1. Synthetic Data Performance (Processing Time)

| Algorithm       | Time (s)  | Complexity |
|-----------------|----------|------------|
| Classic NMS     | 28.281   | O(n log n) |
| Soft NMS        | 30.051   | O(n log n) |
| Adaptive NMS    | 56.041   | O(n²)      |
| Hashing NMS     | 0.415    | O(n)       |
| Inverted NMS    | 28.640   | O(n log n) |

**Key Finding:** Hashing-based NMS demonstrated superior speed (linear time complexity), while Adaptive NMS was the slowest due to its quadratic complexity.

---

### 2. Real-World Dataset Performance

#### CrowdHuman Dataset:

| Algorithm       | Precision | Recall  | F1-Score |
|-----------------|-----------|---------|----------|
| Adaptive NMS    | 0.881     | 0.459   | 0.565    |
| Classic NMS     | 0.885     | 0.459   | 0.566    |
| Hashing NMS     | 0.608     | 0.479   | 0.476    |
| Inverted NMS    | 0.888     | 0.455   | 0.564    |
| Soft NMS        | 0.875     | 0.460   | 0.565    |

#### Blood Cell Dataset:

| Algorithm       | Precision | Recall  | F1-Score |
|-----------------|-----------|---------|----------|
| Adaptive NMS    | 0.685     | 0.963   | 0.787    |
| Classic NMS     | 0.687     | 0.963   | 0.788    |
| Hashing NMS     | 0.574     | 0.964   | 0.708    |
| Inverted NMS    | 0.687     | 0.962   | 0.789    |
| Soft NMS        | 0.686     | 0.962   | 0.788    |

**Key Finding:** Inverted NMS consistently achieved high performance across both datasets.

---

### 3. Precision-Recall Analysis

![PR Curves for CrowdHuman](images/crowdhuman_pr_curve.png)
*Fig. 1: Precision-Recall curves on CrowdHuman dataset*

![PR Curves for Blood Cells](images/bloodcell_pr_curve.png)
*Fig. 2: Precision-Recall curves on Blood Cell dataset*

---

## Key Conclusions

1. **For Processing Speed**  
   **Hashing-based NMS** is optimal with linear time complexity

2. **Adaptive Algorithms**  
   Soft NMS and Adaptive NMS show potential but require careful hyperparameter tuning:

3. **Balanced Recommendation**  
   While Classic NMS remains a reliable baseline, Inverted NMS offers better consistency:

## References

1. Redmon, J., & Farhadi, A. (2018). YOLOv3. *https://arxiv.org/abs/1804.02767*  
2. Bodla, N., et al. (2017). Soft-NMS. *https://arxiv.org/abs/1704.04503*  
3. Wang, J., et al. (2020). Hashing-NMS. *https://arxiv.org/abs/2005.11426*  
4. Liu, L., & Zhou, L. (2023). Inverted-NMS. *https://arxiv.org/abs/2305.10593*  