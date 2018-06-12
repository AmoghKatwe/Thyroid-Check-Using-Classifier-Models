# Thyroid-Check-Using-Classifier-Models
Built classifier models on the Euthyroid Dataset to predict the result of patient using ROC as a performance measure


## 1.	Introduction
The Data Set chosen is a Euthyroid Check Sick Syndrome. The Data Set has 21 attributes including the Result. The aim of the Data is to check if the patient has Thyroid problem or not. The Class attribute ‘Result’ has 2 possibilities i.e., Positive and Negative. The result of the patient can be predicted by considering some or all the attributes taken together. 
The accuracy of the result is got by considering attributes which were got after running Attribute Selection Algorithms on the Data Set.


### Source
The source of the Data Set is http://www.hakank.org/weka/


### Dataset Description 
1)	Age: Age of Patient
2)	Sex: Patient Gender
3)	On Thyroxine: Check whether patient is on thyroxine or not. (TRUE|FALSE)
4)	Query on Thyroxine: Check the Query on Thyroxine. (TRUE|FALSE)
5)	On Anti-thyroid medication: Checks if patient is on anti-thyroid medication or not
6)	Thyroid Surgery: Show whether the patient has had a thyroid surgery or not (TRUE|FALSE)
7)	Query Hypothyroid: This shows if the Thyroid gland is underactive or not.
8)	Query Hyperthyroid: This shows if the Thyroid gland is overactive or not.
9)	Pregnant: Checks whether patient is pregnant or not (TRUE|FALSE)
10)	Sick: Checks if the patient is Sick or not (TRUE|FALSE)
11)	Tumour: Checks if the patient has a Tumour or not (TRUE|FALSE)
12)	 Lithium: Checks the use of Lithium in the body (TRUE|FALSE)
13)	Goitre: Checks if there is swelling in the thyroid glands (TRUE|FALSE)
14)	TSH Measured: This is Thyroid Stimulation hormone Test. This checks if the test is done or not (YES|NO) 
15)	TSH Real: This shows the amount of TSH present in the blood
16)	T3 measured: This shows Value the value of Total Triiodothyronine which is used to check the thyroid function.
17)	TT4 Measured: Checks Total hormone concentration.
18)	T4U Measured: This is the Thyroxine Utilization Range
19)	FTI Measured: These are Thyroid Function Test blood test value which are used to check function of Thyroid.
20)	FTI Real: This is value the FTI check
21)	Result: The result shows that the person is suffering from Sick Euthyroid or Not(Negative)


## 2.	Model Building Procedure
After loading the Data Set into Weka, the next step was to choose Attributes which would help in deciding which attribute will give the best accuracy. For the Attribution Selection Algorithms, it would display the attributes that I can choose. We choose a search method for a few attributes, which would help in selecting the attributes for classification. 
For the execution of the attribute selection algorithm, I choose Full Training Set for the attribute selection mode.
After getting the attributes, I would choose the first 6 attributes among the list of ranked attributes along with the Class attribute.

The next step would be deleting the rest of the attributes and running Classifier Algorithms on them. For the classification, I choose the 10-Fold Cross-Validation as the test option for all the algorithms.


## 3. 	Attribute Selection Algorithms Chosen

### a.	CfsSubsetEval [Best First method]
This algorithm evaluates a subset of attributes by considering the individual predictive ability of each feature along with the degree of redundancy between them. The subsets that are highly correlated with the class while having low intercorrelation are preferred. Best First is the search method used for the algorithm.


### b.	GainRatioAttributeEval
This algorithm evaluates the worth of an attribute by measuring the gain ratio with respect to the class. A Ranker is used for the search method.

GainR(Class,Attribute)=(H(Class)-H(Class ┤|  Attribute))/(H(Attribute))

### c.	InfoGainAttributeEval
This algorithm evaluates an attribute by measuring the information gain with respect to the class.
Information Gain is calculated as shown:

Information Gain(Class,Attribute)=H(Class)-H(Class ┤|  Attribute)

### d.	OneRAttributeEval
Evaluates an attribute using OneR Classifier.



## 4.	Classifier Models & Results
For the Classification, I ran 10 classifier models to check which classifier has the highest ratio. The following shows the result the 4 best classifier models chosen that has the best accuracy, for every algorithm.


## 5.	Conclusion
Among all the classifications, Random Forest Classifier has the highest accuracy and the largest ROC area with 4 of the Attribute selection algorithms.
J48 has the highest accuracy with CfsSubsetEval as the attribute selection algorithm, with accuracy of 94.22% and ROC area of 0.916.

Random Forest classifier has the highest accuracy with 4 attribute selection algorithms. They are,
•	It has an accuracy of 97.49% and ROC area of 0.977 with GainRatioAttributeEval as the attribute selection algorithm.
•	It has an accuracy of 97.23% and ROC area of 0.976 with InfoGainAttributeEval as the attribute selection algorithm.
•	It has an accuracy of 96.13% and ROC area of 0.965 with OneRAttributeEval as the attribute selection algorithm.
•	It has an accuracy of 94.27% and ROC area of 0.948 with attributes chosen by myself.

From all the attribute selection algorithms, we find that GainRatioAttributeEval has the highest accuracy of 97.49% and ROC area of 0.977 with Random Forest being the classifier.

Also, the sensitivity (TP Rate) is highest for attribute selection algorithm of GainRatioAttributeEval with Random Forest being the classifier.

Hence here we can say that, GainRatioAttributeEval with Random Forest being the classifier gives the best result with TP rate = 0.977 and Accuracy = 97.49%.

