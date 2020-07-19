# Introduction to Machine Learning

- [Introduction to Machine Learning](#introduction-to-machine-learning)
  - [What is Machine Learning?](#what-is-machine-learning)
  - [How Traditional Programming is different from Machine Learning?](#how-traditional-programming-is-different-from-machine-learning)
  - [Applications of Machine Learning](#applications-of-machine-learning)
  - [The historical context of machine learning](#the-historical-context-of-machine-learning)
  - [The Data Science Process](#the-data-science-process)
    - [The OSEMN Framework](#the-osemn-framework)
  - [Common Types of Data](#common-types-of-data)

***

## What is Machine Learning?

Definition 1: **Machine learning is the science of getting computers to act without being explicitly programmed. - Andrew Ng**

Definition 2: Machine learning is a data science technique used to extract patterns from data, allowing computers to identify related data, and forecast future outcomes, behaviors, and trends.

Definition 3: A subcategory of artificial intelligence that involves learning from data without being explicitly programmed.

***

## How Traditional Programming is different from Machine Learning?

In traditional programming we use data and rules as input to process and get the output/result while in Machine Learning we pass on the data and the output/result to the machine to figure out the rules by itself (train the model) that can be used later on to feed input and get the desired output.

![Traditional programming v/s Machine Learning](https://user-images.githubusercontent.com/7588716/87047646-6653e800-c218-11ea-9009-c6c1cc89f35a.png)

***

## Applications of Machine Learning

The applications of machine learning are extremely broad! And the opportunities cut across industry verticals. Whether the industry is healthcare, finance, manufacturing, retail, government, or education, there is enormous potential to apply machine learning to solve problems in more efficient and impactful ways.

<img alt="ML Application" src="https://user-images.githubusercontent.com/7588716/87048715-b41d2000-c219-11ea-9b25-8c34d5e53846.png" width="650">

Few examples of applied Machine Learning:

- **Automate the recognition of disease**: Trained physicians can only review and evaluate a limited volume of patients or patient images (X-rays, sonograms, etc.). Machine learning can be used to spot the disease, hence reducing physician burnout. For example, [Google has trained a deep learning model to detect breast cancer](https://www.mercurynews.com/2017/03/03/google-computers-trained-to-detect-cancer/) and [Stanford researchers have used deep learning models to diagnose skin cancer](https://news.stanford.edu/2017/01/25/artificial-intelligence-used-identify-skin-cancer/).

- **Recommend next best actions for individual care plans**: With the mass digitization of patient data via systems that use [EMRs (Electronic Medical Records) and EHRs (Electronic Health Records)](https://en.wikipedia.org/wiki/Electronic_health_record), machine learning can be used to help build effective individual care plans. For example, [IBM Watson Oncology](https://www.ibm.com/products/clinical-decision-support-oncology) can help clinicians explore potential treatment options. More examples of how machine learning impacts healthcare can be found [here](https://www.forbes.com/sites/nicolemartin1/2019/08/30/how-healthcare-is-using-big-data-and-ai-to-cure-disease/#64671f7e45cf).

- **Enable personalized, real-time banking experiences with chatbots**: You've likely encountered this when you call a customer service number. Machine learning can be used to intercept and handle common, straightforward issues through chat and messaging services, so customers can quickly and independently resolve simple issues that would otherwise have required human intervention. With the chatbot, a customer can simply type in a question and the bot engages to surface the answer. Refer to [this article](https://www.drift.com/learn/chatbot/ai-chatbots/) to find more information about chatbot powered machine learning.

- **Identify the next best action for the customer**: Real-time insights that incorporate machine learning tools—such as [sentiment analysis](https://www.concur.com/newsroom/article/machine-learning-with-heart-how-sentiment-analysis-can-help-your)—can help organizations assess the likelihood of a deal closing or the level of a customer’s loyalty. [Personally-tailored recommendations](https://medium.com/@madasamy/introduction-to-recommendation-systems-and-how-to-design-recommendation-system-that-resembling-the-9ac167e30e95) powered by machine learning can engage and delight customers with information and offers that are relevant to them.

- **Capture, prioritize, and route service requests to the correct employee, and improve response times**:
A busy government organization gets innumerable service requests on an annual basis. Machine learning tools can help to capture incoming service requests, to route them to the correct employee in real-time, to refine prioritization, and improve response times. Can check out [this article](https://monkeylearn.com/blog/ticket-routing/) if you're curious to learn more about ticket routing

***

## The historical context of machine learning

- *Artificial Intelligence* : A broad term that refers to computers thinking more like humans.
- *Machine Learning* : A subcategory of artificial intelligence that involves learning from data without being explicitly programmed.
- *Deep Learning* : A subcategory of machine learning that uses a layered neural-network architecture originally inspired by the human brain.

<img alt="ML Application" src="https://user-images.githubusercontent.com/7588716/87622868-a992e700-c741-11ea-9e3e-3c5c98ed0423.png" width="650">

Further Reading: [What’s the Difference Between Artificial Intelligence, Machine Learning and Deep Learning? by Michael Copeland at NVIDIA](https://blogs.nvidia.com/blog/2016/07/29/whats-difference-artificial-intelligence-machine-learning-deep-learning-ai/)

***

## The Data Science Process

<img alt="Data Science Process" src="https://user-images.githubusercontent.com/7588716/87878538-79c63680-ca02-11ea-9e91-513a632bcde6.png" width="650">

1. *Data Collection* : This involves collection the data from various sources and handling the amount of data.
2. *Data Preparation* : In this step, the relevant features affecting the end result are marked and kept for further research and the rest are either standardized or removed, based on the requirement. Data wrangling is a part of this process.
3. *Model Training* : This step usually involves selecting an algorithm based on data and usecase. Then dividing the data into Training , Testing, and Validation(Optional) sets for further process.
4. *Model Evaluation* : At this stage, we run the model on the validation set of the input data to assert its accuracy, precision and so on.
5. *Model Deployment* : This is usually the last step - the best model is used based on different parameters such as accuracy, precision and recall and is deployed on some web service, API etc.
6. *Re-training* : When we get new data, we might need to re-train the model to get the model adjusted with the new data or in between training and deployment, we re-train the model several times to get the best parameters for the final model.

### The OSEMN Framework

<img alt="Data Science Process" src="https://user-images.githubusercontent.com/7588716/87878582-b5610080-ca02-11ea-9d2e-7e49a88f06e8.png" width="650">

Further Reading: [5 Steps of a data science project](https://towardsdatascience.com/5-steps-of-a-data-science-project-lifecycle-26c50372b492)

***

## Common Types of Data

In Data Science, we deal with different types of data. Here are the few types of data that we deal with:

- *Numerical* - **It's All Numerical in the End**. This involves integer or float data.

- *Time-Series* - Evenly spaced data in different points of time or simply data that contains datetime values in it. It is a series of numerical data which can be arranged in an order.e.g - Population data over the years, stock market data.

- *Categorical* - This type of data if of mainly some specific categories in which the entire dataset is divided into - generally has low cardinality but this type of data requires a very high efficiency while handling it.e.g gender.

- *Text* - This type of data comprises words, sentences, articles etc and it is a challenge to get these converted into a machine understandable form. We use NLP to handle text data.

- *Image* - Image frames from video stream or simply the entire video stream - again the same problem of converting these into numerical form to make some sense out of it.

**All data in machine learning eventually ends up being numerical, regardless of whether it is numerical in its original form, so it can be processed by machine learning algorithms.**
***
