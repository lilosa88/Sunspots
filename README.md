# Case study Sunspots

# Objective

- This project belongs to [kaggle's competitions](https://www.kaggle.com/robervalt/sunspots) and I carried out as a part of a specialization called [DeepLearning.AI TensorFlow Developer Specialization](https://www.coursera.org/account/accomplishments/specialization/certificate/L6R6AFWVXHZT) which is given by DeepLearning.AI. This specialization is conformed by 4 courses: 
1. Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning 
2. Convolutional Neural Networks in TensorFlow 
3. Natural Language Processing in TensorFlow 
4. Sequences, Time Series and Prediction

Specifically this project is part of the second course in this specialization. 

- Sunspots are temporary phenomena on the Sun's photosphere that appear as spots darker than the surrounding areas. They are regions of reduced surface temperature caused by concentrations of magnetic field flux that inhibit convection. Sunspots usually appear in pairs of opposite magnetic polarity. Their number varies according to the approximately 11-year solar cycle. We have a dataset that contains the monthly mean total sunspot number, from 1749/01/01 to 2017/08/31. The idea is to create a Deep Learning model that is capable of predicting the total sunspot number in the future. 

# Code and Resources Used

- **Phyton Version:** 3.0
- **Packages:** pandas, numpy, sklearn, seaborn, matplotlib

# Data description

- Date: Date in which the total sunspot number was taken, in the format year-month-day
- Monthly Mean Total Sunspot Number

# Data exploration

-Loking at how the monthly mean total sunspot number changes with the time we observe a bit of seaonality. However it is not very regular with some peaks much higher than others. We also have a bit of noise but there is not general trend.

 <p align="center">
   <img src="https://github.com/lilosa88/Sunspots/blob/main/Images/Captura%20de%20Pantalla%202021-04-28%20a%20la(s)%2021.37.52.png" width="560" height="320">
  </p>

# Feature engineering

-  We split our series into a training and validation datatests. We select split_time= 3000.
-  We set all the constants for our neural network model. Window_size = 20, batch_size = 32 and shuffle_buffer_size = 1000.

# Neural Netwrok model

- We use Convolutional layer with the activation function as a "relu"
- We use two Long Short Term Memory layers
- We use three Dense layers with the activation function as a "relu"
- We use callback in order to tweak the learning rate using a lr scheduler, we found that lr=1e-5 was the best
- The loss function used was Huber
- The metric was mae
- epochs=100

 <p align="center">
   <img src="https://github.com/lilosa88/Sunspots/blob/main/Images/Captura%20de%20Pantalla%202021-04-28%20a%20la(s)%2021.37.52.png" width="560" height="320">
  </p>
  
   <p align="center">
   <img src="https://github.com/lilosa88/Sunspots/blob/main/Images/Captura%20de%20Pantalla%202021-04-28%20a%20la(s)%2021.37.52.png" width="560" height="320">
  </p>



