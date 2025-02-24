# N1102 Machine Learning
This repository is for the machine learning course, which is part of the Computer Science postgraduate program at CIn/UFPE. It contains projects focused on evaluating and comparing machine learning classifiers using various methods.

## First Question

Consider the **"SPECTF Heart"** data from the UCI website ([SPECTF Heart Dataset](http://archive.ics.uci.edu/dataset/96/spectf+heart)). 
Concatenate the **SPECTF.test** and **SPECTF.train** datasets to form the **SPECTF dataset** with 267 individuals (rows) described by 45 variables (columns), with the first column being the class variable. 

**Parameters:**
- **T = 100**
- **∈ = 10⁻⁶**
- **m = 1.1**

### Steps:

1. **Run the KFCM-K and KFCM-K-W.1 algorithms** 50 times each to get a fuzzy partition with:
   - **c ∈ {2, 3, 4, 5}**
   - For each **c**, select the **best result** according to the objective function.
   
2. **Get the corresponding crisp partition** from the best fuzzy partition for each **c**.

3. **For each c and crisp partition**, calculate the **silhouette coefficient (Sil)**.
   - Plot **Sil vs. c** for **c ∈ {2, 3, 4, 5}**.
   - Choose the **optimal number of clusters (c*)**:
     
     \[ c^* = \arg\max_{c} Sil(c) \]

4. **For each algorithm and best fuzzy partition with c***:
   - Calculate the **Modified Partition Coefficient** and comment on the results.

5. **For each algorithm and crisp partition corresponding to the best fuzzy partition with c***:
   - Calculate the **Corrected Rand Index** and comment on the results.

6. **For each algorithm and best result according to the objective function with c***:
   - Show the **prototypes** of each group (**g₁, ..., g_c**).
   - Show the **vector of width parameters** of each group (**s₁, ..., s_c**).
   - Display the **confusion matrix** of the **crisp partition vs. the a priori partition**.
   - Plot the **objective function vs. the iterations**.

### Reference:
- **Gaussian Kernel Fuzzy C-Means with Width Parameter Computation and Regularization** ([DOI: 10.1016/j.patcog.2023.109749](https://doi.org/10.1016/j.patcog.2023.109749))

---

## Second Question

Consider once again the **SPECTF dataset** with **two a priori classes**.

### Steps:

1. **Use "30 10-folds" stratified cross-validation** to evaluate and compare the following 5 classifiers:
   - **(i) Bayesian Gaussian**
   - **(ii) k-neighbor-based Bayesian**
   - **(iii) Bayesian based on the Parzen window**
   - **(iv) Logistic regression**
   - **(v) Majority vote rule** from the first 4 classifiers.

2. **When necessary, perform hyperparameter tuning:**
   - Use **5-fold cross-validation** on the remaining 9 folds.
   - Retrain the model using the remaining 9 folds with the **optimal hyperparameters**.
   - Use **stratified sampling**.

3. **Estimate and compute the confidence interval** for each classifier evaluation metric:
   - **Error rate**
   - **Accuracy**
   - **Coverage**
   - **F-measure**

4. **Compare the classifiers using statistical tests:**
   - Use the **Friedman test** (non-parametric test).
   - Apply the **Nemenyi post-hoc test** for each metric.

5. **For each evaluation metric**, plot the **learning curve for the Gaussian Bayesian classifier**:
   - Use **stratified sampling**.
   - Split **70% for training** and **30% for testing**.
   - Train the algorithm using training sets ranging from **5% to 100%** of the original training set, with a **5% step size**.
   - Comment on the results.

### Observation:

- **For the k-NN algorithm**, consider the following distance metrics:
  - **Euclidean distance**
  - **City-Block distance**
  - **Chebyshev distance**
  
- Use **cross-validation techniques** to determine the best values for **k** and the **distance metric**.

For each assessment metric, plot the learning curve for the Gaussian Bayesian classifier. Using stratified sampling, use 70% of the data for training and 30% for testing. Train the algorithm with sets training from 5% to 100% of the original training set, with step of 5% (using stratified sampling). Comment.

Team: 
Beatriz Andrade de Miranda (bam2@cin.ufpe.br),
Camila Siqueira Lins (csl2@cin.ufpe.br),
Luisa Cavalcante (lncc@cin.ufpe.br) and
Nicolly Lira Albuquerque (nla@cin.ufpe.br)
Observation

For the k-NN algorithm, consider the Euclidean, City-Block and Chebishev distances to define the neighbourhood. Use cross-validation techniques to fixate the parameters k and the distance.
