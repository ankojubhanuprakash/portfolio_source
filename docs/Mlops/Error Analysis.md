# Baselines
Ameisen (2018) names four levels of performance we can categorize a model into. Using these levels of performance we can determine what level we want our model to achieve based on our domain knowledge, our computational and human resources, and our business goals. Each level of performance will guide our selection of a baseline.

 
- **Trivially Attainable Performance**   
The Trivially Attainable Performance is the performance that can be obtained easily and you should expect your model to be better than this. For instance, in classification, guessing the most frequent class provides a quick solution.
- **Human Level Performance**   
We use machine learning methods mainly due to two reasons: automate tasks, or perform tasks where machines and algorithms are faster and better than humans (AlphaGo). For the former, a model achieving Human Level Performance means that the model is ready for deployment and for the latter it is only a lower bound on the expected performance.
- **Reasonable Automated Performance**   
Reasonable Automated Performance represents what can be obtained with a relatively simple method. This benchmark is critical in assessing whether a complex model is performing well and in addressing the accuracy and complexity trade-off.
- **Required Deployment Performance**   
Finally, Required Deployment Performance is the minimal performance that makes your model ready for production from a business standpoint.

Having constructed a baseline, the next step is to see what the baseline fails to capture. This will guide our choice of a more complex model. That being said, we should also not neglect the fact that improving upon baselines can make already successful cases fail, as improvements are not strictly additive. 
1. For example, for a classification task we can get an idea of what classes are hard to separate from each other by looking at the confusion matrix.
2. If we have a lasso regression problem, we can look at the non-zero coefficients to guide feature selection. Furthermore, if the model neglects some features that our domain knowledge tells us are important, then that sends a warning signal as our data may not be a good representation of the population or it could just be that the model is not suitable.



**Improving Baselines Strategically**   
These ideas were originally presented in Merity (2017).   

- Do not add unnecessary complexity   
A good rule of thumb is to start with a simple baseline, for example, logistic regression. The baseline should be stable in the sense that its results should be warranted up to some degree. Therefore, following Occam’s Razor principle is most valid for a baseline. If adding a lot of complexity means a tiny increase in performance, then keep that complexity out of the baseline.
- Find the limits of your baseline   
After we have constructed a simple and fast baseline we get it into shape. This can be done by: extensively tuning parameters, adopting regularization techniques, conducting data processing etc. We can afford many runs tuning the hyperparameters because the baseline is simple. Similarly, bugs and flawed assumptions become easier to find as the model is not complex enough to hide them from us.
- Gradually progress towards complex models   
While we progress towards more complex models, it is important to understand if the complexity we add is warranted. A strategy that people follow is to keep increasing the model’s parameters until it overfits on the dataset and then introduce regularization to prevent overfitting. Even though some work (Belkin 2019) has shown that further increasing the complexity of your model may lead to good generalization, this still leads to a lack of understanding of why increasing complexity works. Besides, simply adding complexity leads to too many moving parts, and it may be hard to isolate the improvements. A key idea when moving towards more complex models is to make sure we know what we are trading off. Add a component, one at a time, evaluate it, and then keep it or remove it. For example, we may have to weigh between component A which makes the model far slower but achieves gains, or component B that makes the model less general but faster.

#  Error Analysis

interepretml, fairlearn, error analysis

# Experiment Tracking 

## References
1. [Baselines](https://blog.ml.cmu.edu/2020/08/31/3-baselines/)
2. [Error Analysis](https://techcommunity.microsoft.com/t5/azure-ai-blog/responsible-machine-learning-with-error-analysis/ba-p/2141774)
3. [Experiment Tracking](https://neptune.ai/blog/ml-experiment-tracking)