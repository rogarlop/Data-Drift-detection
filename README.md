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

### **Wassterstein Distance**

Also named as "Earth Mover's Distance" (EMD) as it is interpreted as the energy cost needed to transform a probability distribution into another. This distance is the sum of all the absolute differences along the distributions instead of using only the maximum difference.

### **Mann-Whitney-Wilcoxon test**

Another non parametric proof. It determines if two sample distributions come from the same population. It is a popular alternative to t-student test. It assumes that the compared samples are from the same population. In case this is true, when all observation are joined, it is expected to observe a random intercalation between them. The opposite causes the observations to move or group by one side or another compared to the first distribution. Its assumptions are that the data need to be ordinal or at least sortable and to be independant. Null hypothesis is when both distributions come from the same population. The next equations show the way the proof is executed (n1 and n2 refer to sample size, R1 and R2 correspond to the sum of the ranges of the observations of each sample, Z is the probability to acquire at least the same value than the observed and with this last value, the statistical tables are consulted to the desired significancy level to obtain the p value). A good tool that can also be obtained during this proof is the "effect". That is the normalized Z statistic depending on the total number of observations. An effect higher than 0.5 typically is considered high, medium in the range 0.3-0.5 and low less than 0.1-0.2.
