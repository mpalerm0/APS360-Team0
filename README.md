# APS360-Team0
Documenting APS360 coursework and final Project


## Project Description - Weather Forecasting with RNN 

Link to Colaboratory notebook: [Here](https://colab.research.google.com/github/MEGmax/APS360-Team-0/blob/main/APS360_Team0_WeatherForcastingModel.ipynb)

This project aims to develop a model to accurately predict weather patterns based
on historical weather and climate data. A recurrent neural network (RNN) will
be leveraged to analyse the sequential and pattern based nature of the weather to
forecast real time weather

## Team 0 Members

```
Andrew Radke
andrew.radke@mail.utoronto.ca
```
```
Matthew Grech
matthew.grech@mail.utoronto.ca
```
```
Mitchell Palermo
mitchell.palermo@mail.utoronto.ca
```
```
Liza Abraham
l.abraham@mail.utoronto.ca
```
## 1. Introduction

Weather forecasting is an essential aspect of our daily lives, not only impacting our personal conve-
nience, but affecting entire industries such as agriculture, transportation, and energy systems. The
goal of this project is to develop a machine-learning model that can accurately predict the weather
based on historical weather and climate patterns of an area. Accurately forecasting the weather is
crucial to both the economy and the safety of people. Accurate weather predictions facilitate better
agricultural planning and crop management for farmers. In transportation, weather patterns are criti-
cal for optimizing cargo routes and the safety of plane passengers. Additionally, energy systems rely
on accurate weather prediction for effective power management and distribution, particularly for the
future of renewable energy sources that are heavily reliant on weather conditions. Deep learning
is a reasonable approach to this project as the weather has many pattern-based characteristics and
does not follow a rigid structure, making it difficult to compute with traditional methods. Neural
Networks excel at learning patterns and are able to learn from the historical weather events of an
area and apply that information to make an accurate prediction given real-time data.

## 2. Background

Since the advent of computer modelling weather forecasting systems have been in use to provide
weather event predictions. Historically, forecasting approaches may be broken into two groups, tra-
ditional numerical weather prediction (NWP) systems and artificial intelligence (AI) models. NWP
systems are comprised of hard-coded physics-based equations modelling physical processes with
dynamic multi-variable interactions [1]. These NWP systems would require extreme amounts of
computing power and time to process the results, taking an hour to process the same information
that current AI models take one second to process [2]. Modern AI solutions include, but are not
limited to, Recurrent Neural Networks, Long Short Term Memory (LSTM), and Gated Recurrent
Units (GRU) and Transformers [3]. RNNs are models which use backpropagation, a technique that
produces outputs as the sigmoid of not only current but also past inputs [3]. LSTM and GRU mod-
els are built upon a RNN framework, but implement additional variables that work by learning to
“forget” information that is not useful for future predictions [4]. Lastly, recent developments with
attentional transformer models enable the system to select the most important information across
prior time steps, not just consolidating all preceding values, or selectively dropping the least useful
pieces of information [5].


## 3. Project Illustrations



<div>

[![High Level Project Illustration](https://drive.google.com/uc?export=view&id=1XQ1VhwHU56X6fMi-EYm8ZKSQY8yYAnjB)](https://drive.google.com/uc?export=view&id=1XQ1VhwHU56X6fMi-EYm8ZKSQY8yYAnjB)
<div align="center"> <strong> Figure 1: High Level Project Illustration</strong> </div>

</div>


<div>
  
[![Recurrent Neural Network Illustration](https://drive.google.com/uc?export=view&id=1J69MN5JGuIstvZqxiqSiHXYq-Te3dSV3)](https://drive.google.com/uc?export=view&id=1J69MN5JGuIstvZqxiqSiHXYq-Te3dSV3)
<div align="center"> <strong>Figure 2: Recurrent Neural Network Illustration </strong></div>
</div>



## 4. Data Processing

The Government of Canada has amassed hourly weather data [6] for many specific regions in Canada
over the course of years. The team will collect the hourly weather data for Toronto over several years,
directly from their historical data portal, in a .CSV file format. When data is stored and the directory
is mounted to the Google Colabratory the team will clean and filter data for relevant metric and
non-null fields. To format the data into a usable state, the team will use the PySpark Library (Python 
API for Apache Spark) to query the data and generate a complete dataset that can be used to train
and validate our model. Formatting would not only include only pulling relevant fields, but it would
also require ensuring the fields are cast to the correct datatype (i.e. datetime, int, string) and any
spacing issues and special characters are dealt with. Developing a query/script to clean our data will
allow us to easily scale our dataset. We will be able to source more data from these sources, in their
standard template, and clean/format the data quickly and efficiently.

## 5. Architecture

The chosen model for this project is an RNN. An RNN will be used because it excels in areas such
as processing sequential data. Weather is inherently sequentially natured and thus the RNN will be
the best at interpreting this data and using it to make an accurate prediction. An RNN is good at
handling sequential data because it contains memory, time dependency and back propagation, which
will all be used to improve the prediction. In contrast, a CNN will not be used as they are best suited
for image interpretation and images will not be used for weather prediction.

## 6. Basline Model

The baseline model that will be used is a persistence model. The persistence model is a simple
model where you take the current state of the weather and predict the future state to be the exact
same as the current state. This model may seem overly simplistic as it does not use any machine
learning or complex algorithms, but it establishes a minimum performance for the model. If the
model performs better than this baseline then it can be determined that relevant information was
learned by the neural network, whereas if the model performs worse, then it can be determined that
the model did not learn any relevant information.

## 7. Ethical Consieration  

The four key ethical issues posed by the proposed forecasting model include biases, data handling,
model application, and overall transparency in the creation and operation of the model [7]. Biased
output can result from biased input, specifically when training on climate data from regions different
from those where the model is applied. This will be remedied by training and applying the model
strictly within the greater Toronto area. The next issue regards proper handling of data collection,
use, and storage. To avoid mishandling all training and inference data used will be collected from
publicly available databases provided by the Government of Canada. Additionally, model misuse
can possibly unlock potentials to use the information produced against groups and regions. Due to
the nature of this project, the model is not using state of the art technology, along with only be-
ing shared among Team 0 and APS360 staff, restricting its overall potential for use and therefore
misuse. Lastly, transparency regarding the creation and operation is a necessary element when re-
garding technology and the environment. This paper, along with all following course documentation
will provide reasonable detail to the models processes, and its narrow application and lightweight
construction make for a minimal impact on technological resources that could impact the weather.
This is in addition to the existing efforts done to reduce the ecological footprint of AI and technology,
the details of which extend beyond the scope of this paper.

## 8. Project Plan 

The team has developed a high-level Gantt chart tracking start and completion dates for all course
deliverables and for the project progression itself.


```
Figure 3: High-Level Tasks Gantt Chart
```
Each high-level role has been assigned a Task Owner, who is responsible for delegating the work
within the task to the appropriate members of the team. All assigned Task Owners will create a
detailed subtask tracker, in an Excel format, that will be continuously updated and monitored by
the Task Owner. All tasks are to be delegated equally amongst all members, and if any issues with
workload arise, the Task Owner is to be notified.

```
Figure 4: Sub-Task Tracker Example
```
The team has established protocols to encourage progress transparency and ensure continuous com-
munication:

1. All documentation and the Google Colaboratory Notebook will be located in a shared Google
Drive.
2. All task trackers will also be located in this drive.
3. There will be weekly online meetings.
4. All internal communication will be on an iMessage chat and through email.
5. All members must provide replies within 24 hours.
6. The team is to use GitHub to prevent overwriting each other’s code and for version control.

## 9. Risk Register

In this section, we will identify and analyse the major risks associated with the project. It is important
to consider any risks and assess the likelihood of each risk so that outlined actions are in place if
these risks were to materialise. One type of risk pertains to an unequal contribution among team
members which can arise in a variety of ways including but not limited to:

1. The potential dropout of a team member
2. Conflicting work/school/personal schedules
3. Medical, Family or Personal Emergencies
4. Unequal task distributions


To mitigate this risk, we will establish clear communication channels and a supportive environment
where redistribution of tasks take place if necessary. We will also maintain comprehensive docu-
mentation to minimise the impact of an individual’s departure.

Other than the risk of team and personal conflicts, there are also risks associated the the success of
the model itself that including:

1. Managing Large Amounts of Data
2. Addressing the Complex Interplay of Variables
3. Vanishing Gradients in RNN’s

Firstly, handling vast volumes of weather data can be challenging. Sorting through the data to iden-
tify relevant information is time-consuming and computationally intensive. Failure to address this
risk may result in excessive processing times, increased problem complexity, and potential inaccu-
racies in predictions. Robust data preprocessing techniques, such as filtering algorithms and feature
selection, can be done with PySpark and will enhance model performance by ensuring the model
will be trained on clean, relevant and accurate data.

Secondly, weather forecasting involves interconnected variables with intricate relationships. Ne-
glecting these complexities may lead to oversimplified models that fail to capture the full range of
weather dynamics.

Finally, recurrent neural networks used in weather forecast AI projects are susceptible to the problem
of vanishing gradients, where gradients become extremely small during back-propagation, hinder-
ing the model’s ability to capture long-term dependencies and accurately forecast complex weather
phenomena. This limits the RNN’s predictive capabilities, especially for events influenced by his-
torical weather patterns. To mitigate this, the model will employ methods like gradient clipping and
appropriate weight initialization that can stabilise and improve the training of RNNs, enabling better
forecasting performance for weather AI models.

By proactively brainstorming and addressing these risks, the model will obtain enhanced accuracy,
improved decision-making, and more efficient weather predictions contributing to the overall suc-
cess of the project.

## 10. Link to Google Colab

https://colab.research.google.com/drive/1IQ-zKpyy-Yk1flKSa-byiks4nEUF6r5r?usp=sharing

## References

[1] T. Shenwai, “A study on various deep learning-based weather forecasting models,” MarkTech-
Post, https://www.marktechpost.com/2023/03/01/a-study-on-various-deep-learning-based-weather-
forecasting-models/ (accessed Jun. 15, 2023).

[2] N. Kalchbrenner and L. Espeholt, “MetNet-2: Deep learning for 12-hour precipitation forecast-
ing,” Google AI Blog, https://ai.googleblog.com/2021/11/metnet-2-deep-learning-for-12-hour.html
(accessed Jun. 15, 2023).

[3] J. Shi, G. Narasimhan, and M. Jain, “Time Series Forecasting Using Various
DeepLearning Models,” International Journal of Computer and Systems Engineering,
vol. 16, pp. 224–232, Jun. 2022. Accessed: Jun. 15, 2023. [Online]. Available:
https://www.researchgate.net/publication/361265989TimeSeriesForecastingUsingVariousDee
pLearningModels

[4] IBM, “What are recurrent neural networks?,” IBM, https://www.ibm.com/topics/recurrent-
neural-networks (accessed Jun. 15, 2023).

[5] I. Godfried, “Attention for time series classification and forecasting,” Medium,
https://towardsdatascience.com/attention-for-time-series-classification-and-forecasting-
261723e0006d (accessed Jun. 15, 2023).

[6] E. and C. C. Canada, “Government of Canada / gouvernement du Canada,” Climate,
https://climate.weather.gc.ca/historicaldata/searchhistoricdatae.html(accessedJun. 16 ,2023).

[7] QL Space, “The Ethics of AI and Satellite Data in Weather Forecasting,”
QL Space, https://www.qlspace.com.au/the-ethics-of-ai-and-satellite-data-in-weather-
forecasting/: :text=These%20concerns%20include%20the%20potential,to%20weather%20data%
C%20and%20sustainability. (accessed Jun. 16, 2023).

