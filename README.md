# Robust Journey Planning

----
## Content

* [HOW-TO](#HOW-TO)
* [Problem Motivation](#Problem-Motivation)
* [Problem Description](#Problem-Description)
* [Contributors]

----
## HOW-TO

For a detailed demonstration of the project, please watch [this video](https://youtu.be/GWBFiA9lSIM).

The project consists of the following components:

1. **inference.py**: This script implements the search algorithm that generates the itineraries based on the provided inputs and constraints. It uses a combination of a graph traversal technique and a probabilistic method to optimize the generated routes.

2. **probabilities.py**: This script computes the edge probabilities for the underlying network. It takes into account historical data to estimate the likelihood of delays between different nodes in the graph. The computed probabilities are used by the inference.py script during the itinerary generation process.

3. **timetable_preprocessing.ipynb**: This Jupyter Notebook contains the script used to preprocess the timetable data and create the graph representation. It involves parsing and cleaning the input data, generating the necessary data structures, and preparing the graph for further analysis and inference by storing it.

4. **validation.ipynb**: This Jupyter Notebook provides a validation framework for evaluating the performance of the algorithm. The notebook can be used to assess the accuracy of the travel itinerary generator.

5. **viz.ipynb**: This Jupyter Notebook offers interacting with the algorithm and visualizing the generated travel itineraries. Users can input their preferences, constraints, and destinations, and the script will display the optimal routes along with relevant details if the routes exist. 

In order to interact with the visualization and test the search algorithm, the user has to enter the parameters under the penultimate cell of the viz.ipynb where they can choose between different busy random stops or type another stop of their choice. After having entered all the info the user presses both Search buttons and run the last cell to see the result of the algorithm with these parameters.

----
## Problem Motivation

Imagine you are a regular user of the public transport system, and you are checking the operator's schedule to meet your friends for a class reunion.
The choices are:

1. You could leave in 10mins, and arrive with enough time to spare for gossips before the reunion starts.

2. You could leave now on a different route and arrive just in time for the reunion.

Undoubtedly, if this is the only information available, most of us will opt for option 1.

If we now tell you that option 1 carries a fifty percent chance of missing a connection and be late for the reunion. Whereas, option 2 is almost guaranteed to take you there on time. Would you still consider option 1?

Probably not. However, most public transport applications will insist on the first option. This is because they are programmed to plan routes that offer the shortest travel times, without considering the risk factors.

----
## Problem Description

The goal of this project is to build a _robust_ public transport route planner to improve on that. It is based on the SBB dataset.

Given a desired arrival time, the route planner will compute the fastest route between departure and arrival stops within a provided confidence tolerance expressed as interquartiles.
For instance, "what route from _A_ to _B_ is the fastest at least _Q%_ of the time if I want to arrive at _B_ before instant _T_". Note that *confidence* is a measure of a route being feasible within the travel time computed by the algorithm.

The output of the algorithm is a list of routes between _A_ and _B_ and their confidence levels. The routes are be sorted from latest (fastest) to earliest (longest) departure time at _A_, they all arrive at _B_ before _T_ with a confidence level greater than or equal to _Q_. Tools are implemented to allow the visualization of the routes on a map with straight lines connecting all the stops traversed by the route.

----
## Contributors

Aude Maier
Antoine Maier
Lars Quaedvlieg
Somesh Mehra
Arvind Menon
Zoé Jeandupeux

This project was carried out as part of the EPFL course "Large scale data science for real world data".
