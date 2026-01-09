# Data-Drift-detection
Repository that contains the data drift detection (univariate) on different types of drift.

Drift refers to changes in data distribution over time. This type of changes affect the way a model developed performs, affecting their metrics and relevance to solve a particular problem or give accurate insights. The data over time can be changed in several ways: seasonly, changes in client or customer preferences, external events like changes in technology, culture, politics, economy, and several other factors. It is important to distinguish the different type of drift. Typically there can be defined four of them: gradual, incremental, sudden and reocurring drift. 

<p align = "center"> <img width="427" height="278" alt="image" src="https://github.com/user-attachments/assets/78f1a0ac-99b8-4461-9e5a-9fb38ccd94ba" /> </p>

Different approaches can be adopted to detect drift. One of them is the definition of an error rate, which is measured over a deployed model. If an increment or a decrement in that error is detected and is statistically significant, an alarm is produced to point that drift. Another approach includes the direct comparison between data distribution. If the similarity is measured below certain threshold, the alert is produced.


