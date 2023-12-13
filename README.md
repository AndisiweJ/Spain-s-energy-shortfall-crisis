# Spain's-energy-shortfall-crisis

### Advanced-Regression
### Introduction 
Predicting energy shortfalls in Spain and its significance in facilitating sustainable infrastructure planning. Our goal is to streamline processes, from database design to setting up analytic dashboards, and ensure confident collaboration with our team of biometrics experts.

Our approach involved exploring and visualising the dataset, cleaning it, building multiple models, and assessing their accuracy to ultimately choose the best model for making predictions.

#### Problem Statement
As people from an electricity scarce continent, I’m sure we all appreciate the value of properly planned electricity systems. The Government of Spain has tasked our company with building a model that predicts shortfalls between energy generated by fossil fuels and energy generated from renewable sources. The government of Spain is contemplating an expansion of its renewable energy resource infrastructure investments. To aid this initiative, they sought insights into the trends and patterns of the country's renewable and fossil fuel energy generation.

The important context is that renewable energy generation is both highly variable and takes a long time to bring online (it can’t be switched on and off as quickly as fossil fuel stations), so you need to know in advance when and how much to bring online. Otherwise, you risk power outages if you undercompensate or you could spend unnecessary money and precious resources if you overcompensate.

An accurate and reliable model that can predict Spain’s electricity needs is therefore of the utmost importance.

### EDA and Feature Engineering

Before we delve into the bulk of the model, let’s first clarify something. Load shortfall is defined as the residual load, i.e power generation through fossil fuel minus renewable production. A negative result shows that the renewable energy sources have a higher electricity supply than the fossil fuels, while a positive value show us that the fossil fuels generate more energy than the renewable resources

To create an accurate and reliable model, we gathered various factors that impact electricity demand and supply. These factors included time, weather conditions, wind speed and direction, rainfall, atmospheric pressure, cloud coverage, and snowfall in each city of Spain. By considering these variables, we aimed to capture the complex dynamics of Spain's electricity system.

Firstly, we thoroughly explored and visualised the dataset. This step allowed us to understand the relationships between the different variables and identify any patterns or trends. By visualising the data, we gained valuable insights into how weather conditions and other factors influence electricity demand and supply in Spain.

Interesting features in the data were that: No single variable was by itself closely linked to load shortfall, the correlation of individual variables with the response variable was low Several variables were highly correlated to each other such as the maximum temperatures in the different cities. This could pose multicollinearity issues. There were quite a few outliers in the data. Weekends had the lowest power consumption Summer had a higher load shortfall

Next, we cleaned the dataset to ensure its quality and consistency. This involved handling missing values, removing outliers, and addressing any inconsistencies in the data. By cleaning the dataset, we prepared a reliable foundation for training and evaluating our machine learning models.

Feature engineering played a crucial role in our project. We dropped unnecessary columns, such as "Unnamed," and redundant features like temperature maximum and minimum for each city. Additionally, we removed weather ID columns for Madrid, Barcelona, Seville, and Bilbao, as they didn't contribute to our predictions.

We also created new features by splitting the "time" feature into month, day of the week, year, and hour components. These additional features provided valuable insights into seasonal variations, the rate of change in energy sources over the years, and specific hours when load shortfalls occur.

In order for machine learning models to interpret these features on the same scale, we need to perform feature scaling. In this project, Standard Scaling was adopted because of it's robustness to outliers

### Model Evaluation:

We then proceeded to build 12 different regression models including linear regression, random forest, decision tree, gradient boosting, LASSO, ridge regression, a Support Vector Machine, a neural network, K Nearest Neighbour, Bayesian Ridge, Kernel ridge regression, and LARS lasso.

Linear regression is a model that is based on a straight line graph, sweet and simple Decision tree is hierarchical model that uses a tree-like model of decisions and their outcomes Random forest is a model made up of multiple decision trees Gradient boosting takes the many smaller models and combines them to get a stronger model Lasso shrinks data depending on coefficients and selects only relevant variables LARS lasso is a lasso model designed for data with many dimensions (ie variables) Ridge regression is like lasso but it does not select variables Bayesian Ridge regression is similar to ridge regression but obtains probabilities instead of point values Kernel ridge regression combines ridge regression with the kernel trick (an ability which means they operate with high numbers of variables but never calculate the coordinates of those variables) A Support Vector Machine is a supervised learning model, meaning it is a type of machine learning that relies on labelled input and output training data A neural network is a model that acts like a brain with multiple connected “neurons” that make predictions K nearest neighbour uses the the nearest available data points to make predictions

Each model was trained on the dataset to predict the 3-hourly load shortfall. To ensure the accuracy of our models, we conducted thorough assessments. We used various evaluation metrics such as mean squared error, mean absolute error, and R-squared to compare the predicted values against the actual load shortfall data. These assessments allowed us to validate the model's accuracy and reliability, providing confidence in its predictive capabilities.

We then created ensembles, which are combinations of the aforementioned models that bring out their strengths by decreasing the error and increasing accuracy.

We made 4 ensembles. 3 of them took the average values of the selected models predictions. The 4th weighted all the models according to the performance in our previous assessments.

Based on the evaluations, where lower rmse is best, lower mae is best, and higher r-squared is best, We confidently chose an ensemble as our best performer. We chose its component models (the kernel ridge and the random forest) for their ability to capture complex relationships and handle non-linearities in the data which made it a robust choice for making accurate predictions of electricity shortfall in Spain. They were the two top performing models.

### Business Value/Conclusion

Accurate electricity demand and supply predictions empower Spain's policymakers, utility companies, and grid operators to make informed decisions. This model facilitates energy policy formulation, efficient resource planning, demand response initiatives, and real-time energy balancing. Stakeholders can optimise energy distribution, minimise costs, enhance grid stability, and foster a more sustainable and resilient energy system.

The successful deployment of this machine learning model in Spain will yield improved electricity demand and supply forecasting, optimal resource allocation, enhanced grid stability, and environmental benefits. Accurate predictions enable proactive decision-making,significant cost savings, and improved energy efficiency. Real-time integration ensures dynamic monitoring and timely actions for grid stability. Furthermore, this model contributes to reducing greenhouse gas emissions and promotes sustainable energy practices.

It already outperforms most competitors and with a little bit of tweaking could be taken to new levels of accuracy. Part of what makes our company different is that everyone here is passionate about what they do and very willing to go the extra mile. It will be pleasant, productive, and profitable to work with us as this is more than “just a job” to us. When you choose to collaborate with our company, Spain can make informed decisions, optimise resource allocation, and mitigate the challenges posed by the electricity shortfall and climate crisis.

Thank you for your attention, and we look forward to leveraging the power of machine learning to address Spain's electricity shortfall with accuracy and efficiency.
