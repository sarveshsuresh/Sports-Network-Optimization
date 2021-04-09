# Sports-Network-Optimization
Final semester project on sports viewership

Objective:
The objective of this survey and its analysis was to put myself in the shoes of a Sports Broadcasting Network to decide on the events to cover over a period of one year, subject to the budget as well as tournament-related constraints in order to maximize the Revenue. The code and its working has been detailed in the following notebook:

1.Approach
The following are the steps to be followed to complete the project and satisfy the above objective.
	Design the Survey and collect the relevant data.
	Clean the data obtained from step 1
	Make a clear list of the events available to be covered and the cost and constraints associated with each such event.
	Define the metric to measure the popularity of a sport/event
	Calculate the metric decided upon in step 4 for each sport/event
	Maximize the overall sum of the metric subject to the constraints.

	Sample Survey 
The sample survey was designed using Google Forms. The number of responses received were 173. The link to the Google Form: https://docs.google.com/forms/d/e/1FAIpQLSfXVTtYdrL2ALoQq0s3Izd7sVozmNH9R_ngdDyVvhe9fuT71w/viewform

The responses needed a lot of cleaning as there were a variety of errors made by the respondents while filling the form. The csv file containing the uncleansed data has been attached.

	Cleaning of Survey data
The data obtained from 1.1 had to be cleaned to remove heterogeneity in data formats for each variable. The process has been clearly detailed in the notebook

	List of events and their associated costs
The list of sports events available to be covered and their associated Costs has been clearly mentioned in the Excel Sheet attached. The following are the constraints:
	The expenditure should not exceed 60 Million units.
	At least one event from each sport must be covered.
	For Cricket, all formats of a tour (T20, Test, ODI) need to be covered.
      The goal is to maximise the revenue metric which is yet to be defined.
	Definition of Revenue metric
The revenue metric we will use shall be called the Probabilistic Index (PI)
 〖PI〗_k=p_k×10×m_k

Where pk is the probability of a randomly selected person watching every game in the given tournament k. mk is the number of matches in tournament k.

The values of pk have been obtained in the notebook and the method used is also mentioned.
Now as defined in 1.3, we try to maximize Σ〖(PI〗_k×A_k) where Ak is an indicator function which shows if the event k is to be covered or not. The constraints are mentioned in 1.3

	Calculation of Probabilistic Index.
The following is the algorithm for calculating the PI for each event k:
	For a given sport, iterate through each event.
	For a given event, iterate through each row.
	For each row create a vector containing the events of the given sport which is watched.
	Create a vector containing the quantitative equivalents in terms of number of matches (using domain knowledge) for each level of watching.
	Fill up a new column in each row for each event with the number of matches expected to be watched.
	Take the mean of the column k and divide by mk
	This is the procedure to obtain pk values for each k
The pk values have been calculated in the notebook. The values have been mentioned in the Optimization Excel Sheet too.
	Final Optimization Process
The final step in this project involves deciding on the Ak values such that the constraints in 1.3 are met and the objective function in 1.4 is maximized. This reduces to a Linear Programming Problem (LPP) which has been solved using the Solver utility in MS Excel. The Optimized results are given the Optimization Excel Sheet.


Conclusion:
On solving the final LPP we obtain the list of events that need to be covered.
IPL, India vs England, Australian Open, Premier League, Bundesliga, Laliga, Serie A.
However here are some points that are to be noted:
	The sample size of 173 is not enough as per industry standards.
	The age distribution of the sample is expectedly positively skewed with the peak at 21.
	The cost of coverage for each event, the tournament constraints and budgetary restriction was taken arbitrarily as these are details that would be given by the Network to the Analyst.
	The revenue is considered to be significantly higher than the costs. That is why maximize the revenue and not the profit.
	In the industry, the calculation of the revenue metric will be more complex because said Revenue is obtained through various sources like advertisements, Dish Network fee, etc.


