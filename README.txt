Fraud Detection using Unsupervised Learning
1. Introduction

This project aims to detect anomalous financial transactions using unsupervised learning techniques.

Since no labeled fraud data is available, the analysis focuses on:

Identifying anomalous transactions

Analyzing temporal patterns

Comparing model sensitivity and behavior

Evaluating behavioral segmentation

Four models were implemented:

Isolation Forest

Local Outlier Factor (LOF)

One-Class SVM (OCSVM)

KMeans Clustering

2. Isolation Forest Analysis
Overall Behavior

Isolation Forest detects anomalies by isolating observations through random partitioning.

Key observations:

Anomalies are strongly concentrated in specific months (notably August–September).

Anomalous transactions exhibit significantly higher transaction amounts.

Clear temporal patterns with relatively low noise.

Key Findings

A strong anomaly spike appears in September.

The model is highly sensitive to extreme transaction values.

Anomalies show temporal concentration rather than random dispersion.

Conclusion:
Isolation Forest provides the clearest and most stable anomaly signals among all tested models.

3. Local Outlier Factor (LOF)
Overall Behavior

LOF identifies anomalies based on local density deviations.

Observations:

Anomalies are more dispersed across months.

No sharp spike comparable to Isolation Forest.

Higher detection volume.

Key Findings

Sensitive to local density changes.

Effective at detecting small irregular clusters.

Temporal pattern appears noisier.

Conclusion:
LOF is suitable for detecting local irregularities but is less reliable as a standalone detector.

4. One-Class SVM (OCSVM)
Overall Behavior

OCSVM constructs a decision boundary around normal behavior.

Observations:

Anomalies are distributed across multiple months.

September spike exists but is less pronounced.

Higher variance compared to Isolation Forest.

Key Findings

Detects observations outside the main distribution boundary.

Sensitive to hyperparameters.

Potential risk of over-detection.

Conclusion:
OCSVM works well as a boundary-based validation layer but is less robust for extreme anomaly detection.

5. KMeans Clustering (Behavioral Segmentation)
Cluster Selection

Highest Silhouette score at K=2.

Elbow method suggests K=3.

K=3 selected for better behavioral interpretability.

Behavioral Segments Identified

Cluster 0 – Core Stable Population

Stable transaction amounts

Low volatility

Baseline customer behavior

Cluster 1 – Volatile Segment

Strong monthly fluctuations

Spike in July–August

Significant drop in September

Highest volatility

Cluster 2 – Moderate Activity Group

Moderate fluctuation

Mild spikes in March and September

Intermediate behavior profile

Key Insight

No cluster directly represents fraud.

Fraud signals do not fully align with cluster boundaries.

Conclusion:
KMeans supports behavioral understanding but is not a direct fraud detection tool.

6. Comparative Model Evaluation
Model	Strength	Limitation	Role
Isolation Forest	Strong at detecting extreme values	Less sensitive to local density	Primary detector
LOF	Sensitive to local irregularities	Noisy results	Secondary detector
OCSVM	Effective boundary detection	Over-sensitive to parameters	Complementary layer
KMeans	Behavioral segmentation	Not a direct anomaly detector	Support layer
7. Temporal Insights

Time-based analysis reveals:

Strong anomaly spikes in August–September.

Isolation Forest captures this pattern most clearly.

Volatile clusters align partially with anomaly spikes.

Stable cluster remains consistent over time.

Interpretation

Anomalies exhibit potential seasonal behavior.

Not all customer segments are equally affected.

Behavioral volatility correlates with anomaly concentration.

8. Strategic Approach

Key insights:

No single model is sufficient.

Isolation Forest is the most stable primary detector.

LOF and OCSVM reduce blind spots.

KMeans enables risk-based prioritization.

Recommended Real-World Framework

Use Isolation Forest as core detection model.

Apply ensemble logic (≥2 model agreement).

Prioritize review for high-volatility behavioral segments.

9. Conclusion

This study demonstrates that:

Isolation Forest is the most effective model for detecting extreme anomalies.

LOF and OCSVM provide complementary detection signals.

KMeans enhances behavioral understanding but does not replace anomaly detection.

The August–September spike is the most significant abnormal pattern observed.

Overall, combining anomaly detection with behavioral segmentation provides a practical and robust approach to unsupervised fraud detection.
