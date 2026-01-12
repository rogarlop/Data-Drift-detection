# Data-Drift-detection
Repository that contains the data drift detection of different types of drift.

Drift refers to changes in data distribution over time. This type of changes affect the way a model developed performs, affecting their metrics and relevance to solve a particular problem or give accurate insights. The data over time can be changed in several ways: seasonly, changes in client or customer preferences, external events like changes in technology, culture, politics, economy, and several other factors. It is important to distinguish the different type of drift. Typically there can be defined four of them: gradual, incremental, sudden and reocurring drift. 

<p align = "center"> 
<img width="427" height="278" alt="image" src="https://github.com/user-attachments/assets/78f1a0ac-99b8-4461-9e5a-9fb38ccd94ba" />
</p>

Different approaches can be adopted to detect drift. One of them is the definition of an error rate, which is measured over a deployed model. If an increment or a decrement in that error is detected and is statistically significant, an alarm is produced to point that drift. Another approach includes the direct comparison between data distribution. If the similarity is measured below certain threshold, the alert is produced. Multiple hypothesis testing mixes the two previous techniques (or others) to detecto drift.

In this particular case, the drift was measured using the data distribution technique. This technique use a statistical proof to quantify the similarity between the previous existing samples, and the new samples. The conceptual changes are the aim on drift detection. In particular, we implemented the Kolmogorov-Smirnov (K-S test) and the Mann-Whitney-Wilcoxon tests along with the Wassterstein distance and the Population Stability Index (PSI) to detect it.

### **K-S test**

Non parametric test used for proof if exists a statistically significant difference between two sample distributions (frequencies observed). This is a valuable test because it does not assumes or needs a certain shape of the distribution to be compared. Another term to refer to the likeness of the distribution is "goodness of fit". This proof is build from the cummulative distribution functions (CDF) of the two samples and the largest difference between the two CDFs is determined as the value D. Then, this value D is the one used to determine the critical value for different significance level to accept or deny the null hypothesis. 

<p align = "center"> 
<img width="427" height="278" alt="image" src="https://github.com/user-attachments/assets/c64ee7ab-1cb2-46ed-8d3f-f9bf0310e910" />
</p>
