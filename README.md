Many American cities have communal bike sharing stations where you can rent bicycles by the hour or day. Washington, D.C. is one of these 
cities. The District collects detailed data on the number of bicycles people rent by the hour and day.Hadi Fanaee-T at the University of 
Porto compiled this data into a CSV file. The file contains 17380 rows, with each row representing the number of bike rentals for a single 
hour of a single day. You can download the data from the University of California, Irvine's website. 

Here are the descriptions for the relevant columns:
instant - A unique sequential ID number for each row
dteday - The date of the rentals
season - The season in which the rentals occurred
yr - The year the rentals occurred
mnth - The month the rentals occurred
hr - The hour the rentals occurred
holiday - Whether or not the day was a holiday
weekday - Whether or not the day was a weekday
workingday - Whether or not the day was a working day
weathersit - The weather (as a categorical variable)
temp - The temperature, on a 0-1 scale
atemp - The adjusted temperature
hum - The humidity, on a 0-1 scale
windspeed - The wind speed, on a 0-1 scale
casual - The number of casual riders (people who hadn't previously signed up with the bike sharing program)
registered - The number of registered riders (people who had already signed up)
cnt - The total number of bike rentals (casual + registered)

In this project, I try to predict the total number of bikes people rented in a given hour. I predict the cnt column using all of the 
other columns, except for casual and registered. To accomplish this, I create a few different machine learning models and evaluate 
their performance.


Now that you've done some exploration and manipulation, you're ready to apply linear regression to the data. Linear regression will probably work fairly well on this data, given that many of the columns are highly correlated with cnt.

As you learned in earlier missions, linear regression works best when predictors are linearly correlated to the target and also independent -- in other words, they don't change meaning when we combine them with each other. The good thing about linear regression is that it's fairly resistant to overfitting because it's straightforward. It also can be prone to underfitting the data, however, and not building a powerful enough model. This means that linear regression usually isn't the most accurate option.

You'll need to ignore the casual and registered columns because cnt is derived from them. If you're trying to predict the number of people who rent bikes in a given hour (cnt), it doesn't make sense that you'd already know casual or registered, because those numbers are added together to get cnt.
Now you're ready to apply the decision tree algorithm. You'll be able to compare its error with the error from linear regression, which will enable you to pick the right algorithm for this data set.

Decision trees tend to predict outcomes much more reliably than linear regression models. Because a decision tree is a fairly complex model, it also tends to overfit, particularly when we don't tweak parameters like maximum depth and minimum number of samples per leaf. Decision trees are also prone to instability -- small changes in the input data can result in a very different output model.
