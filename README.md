# IT-Code-Fair-Data-Science-Challenge

I would like to ackowledge that this project has been done with my team members: Hai Vu, Cong Do Le (Peter) and Quang Thang. 
And thanks to CDU IT Code Fair team and the sponsors to give us opportunity to participate in solving real life issue. 

**Project Background:**
Australia’s Information Technology (IT) landscape has been marred by several high-profile IT project failures. Billions of dollars were wasted on projects that never delivered on their promises. The Robodebt scheme, the Queensland Health payroll system, and Victoria’s Myki Smart Card are just a few examples.
Are there patterns behind these failures? Can these failures be anticipated? And what does the data tell us? 

**Project Mission:**
To begin, our team should collect data on high-profile IT project failures from Australia and worldwide. These may include both governmental and non-governmental projects. 
By applying machine learning techniques to this data, we will identify patterns and factors that may have contributed to these failures and determine the extent to which failed projects could have been predicted.

**Project Progress**

1. We first went through research papers and articles that related to this project to identify two significant questions before we processed with further steps. Firstly, which project is identified as failure and which project is identified as successful? This question raised as because, at school, we learned that 3 main contrains that effect a project's success/failure are project scope, project time and project cost. But in reality, what driven to the failure/successful project are not just those 3 factors, they can be technical literacy, user envolvement, project management expertise, etc. (based on the research papers we have read - please see the References folder to access to the research papers). For example, in reality, a project has done with more than the planned time or went over the budget still idetified as success because at the end, the project still met its scope and satisfied the end users. Along with the first question, the second question is that which features/factors we can use to predict whether an IT project fail or success?.

2. We came up with several features that we believed it will effect to the failure/successful of an IT project: Duration, Budget, Restart, Cost Overrun, Time Overrun, Content deficiency, User involvement, Executive Management, Statement of Requirements, Planning, Expectations, Requirements & Specifications, Changing Requirements & Specifications, Technical Competence, Resources Availability, IT Management, Technical Literacy, User satisfaction. (Please refer to Data Analysis folder/Data_dictionary file to view full description of each factor)

3. In data collecting process, data has been collected based on the features have been ideitified earlier. Which mean, an IT project could only be collected as long as we found all the informations realted to the identified factors above. It would be quite difficult to collect those informations as government/non-goverment projects are mostly not published and if we are collecting from Australia, we have to change our IP address to other countries in order to view their IT project reports. The techniques we used to collect/scrape data are: Beautiful Soup library in Python, Microsoft Power Automate, Web Scraper Extension (Google Chrome) for Structured date such as tables, whole pragraphs, etc. However, most of the informations will come in form of text around a paragraph. So to automate the collecting data process, we used tools/techniques for structured date which are mentioned before to scrape pragraphs, from scraped paragraph we used Regular Expression library in Python to extract the information we want to collect in that paragraph. However, we propsed this technique on some of the paragraph in this project only as it would not be time effective strategy as each report contains not many IT projects on it, so to use this technique for all reports we need to change the text pattern regularly. But in future, it will be helpful technique if we want to collect data from a report/article that contains a lot of information on it. (Please refer to Data Analysis folder/Regular Expression python file and Example report file to see how I deal with scraping untructured data)

4. Get to know our dataset: 166 (83 sucessful/failed projects, 86 high-profile projects) IT projects from 20 countries with 50 sub-categories. 82.5% of data are government projects. 95% projects duration within 5 years. 

5. To classify project success or failure, we used  classification algorithm from 4 different models to analyze the project-related data and assign projects to one of the two classes: success or failure based on the predefined features. 
Firstly, we decided to use Naïve Bays classifier as our baseline model because its classification algorithm is simple, can provide quick results.
Beside Naïve Bays model, we also applied other popular advanced classification models on the same dataset which includes Extreme Gradient Boosting, Support Vector Machine and Random Forrest. They are well known for their specific strength, XGBoost strength is in predictive accuracy by combining the strengths of multiple decision trees, SVM is powerful in handling high-dimensional data and complex decision boundaries, while Random Forest is better in capturing complex patterns and handling noisy data.
The performance of the 3 advanced classification models then will be compare to the performance of the baseline model to pick the optimal classification model for our dataset.

6. To compare the 4 classification models, firstly, we loaded and cleaned the data, then extracted the features that we want to evaluate from the dataset. After that we splitted the dataset to training set which includes 80% of the data and the testing set which includes 20% of the data. Finally, we trained each model and evaluate their performance with the metrics below: 
Accuracy: the percentage of all projects (both successful and failed) that the model correctly classified
Precision: Precision in project prediction measures the percentage of the projects that are labeled as "successful" were truly successful.
Recall: the percentage of actual fail projects that the model correctly identified. It's like ensuring that you don't miss any of the real failure project.
F1 score is a balance between precision and recall. It measures the overall accuracy performance of a model.

**Result**:
- Based on the score from the metrics we used, Random Forest model came up with the highest accuracy score (96.43%).
- Based on Feature Weighting and Backward selection techniques, we found that there are 5 significant factors that effect the success/failure of a project: User Involvement, Changing requirement and specification, user satisfaction, planning and technical compentence. 


