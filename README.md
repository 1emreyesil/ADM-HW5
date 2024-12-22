# Homework 5 - USA Airport Flight Analysis

![image](https://github.com/user-attachments/assets/c6a15fd6-fa91-4eba-a5d7-8d3f7a648c9d)


## Overview

This project focuses on analyzing a dataset of the USA airport flight network. The dataset includes information about airports, flight routes, and passenger traffic. The goal is to explore the structure of the flight network, identify key airports (hubs), evaluate flight routes, and analyze the connectivity of the network.

### Key Tasks

1. **Flight Network Analysis**: Analyze the basic features of the flight network such as its size, density, and degree distribution. We will also visualize and identify the busiest airports (hubs) and assess if the network is sparse or dense.
2. **Nodes' Contribution**: Explore different centrality measures, including how important each airport is in the network. These measures help identify key airports that are essential for connectivity.
3. **Best Routes**: Find the best flight route between two cities for a specific day, with the goal of minimizing the total distance traveled.
4. **Airline Network Partitioning**: Identify how to separate the network into two distinct groups of airports, without any connections between them.
5. **Finding and Extracting Communities**: Identify communities of interconnected airports and explore how cities are related within the flight network.

## Approach

### 1. Flight Network Analysis (Q1)

In this task, the goal is to understand the basic properties of the flight network:

- **Graph Features**: Count the number of airports (nodes) and flights (edges). Calculate the density of the network, which helps us understand how interconnected the airports are.
- **Degree Distribution**: Calculate the in-degree (how many flights arrive at an airport) and out-degree (how many flights leave an airport) for each airport. Visualize this with histograms to understand the distribution.
- **Identifying Hubs**: Airports with high degrees (i.e., lots of flights) are called hubs. We will identify these hubs by comparing the degree of each airport to the 90th percentile.
- **Graph Sparsity/Density**: Based on the density, we will determine whether the network is sparse (few connections) or dense (many connections).

The function `summarize_graph_features` will generate a report that includes:

- The number of nodes and edges in the graph.
- The graph's density.
- Degree distribution plots for in-degree and out-degree.
- A table of identified hubs.

### 2. Nodes' Contribution (Q2)

Certain airports play a more critical role in maintaining the flow of traffic. To identify these airports, we will use **centrality measures**:

- **Betweenness Centrality**: How often an airport is on the shortest path between two other airports.
- **Closeness Centrality**: How easily an airport can be reached from all other airports.
- **Degree Centrality**: The number of direct flights an airport has.
- **PageRank**: This measures the "importance" of an airport based on how many incoming flights it has.

We will calculate these centrality measures for each airport and compare them. The function `compare_centralities` will:

- Compute and compare centrality values for all airports.
- Plot the distributions of these centrality measures.
- Identify the top 5 airports for each centrality measure.

### 3. Finding Best Routes (Q3)

For this task, we are interested in finding the best (i.e., shortest) route between two cities for a specific day. The best route is defined as the one that minimizes the total distance flown.

If there are multiple airports in each city, we will compute the best route for each possible combination of airports. If no route is available, the function will return "No route found."

The result will be displayed in a table with three columns:

- `Origin_city_airport`: The airport in the origin city.
- `Destination_city_airport`: The airport in the destination city.
- `Best_route`: The list of airports visited in order during the optimal route.

### 4. Airline Network Partitioning (Q4)

In this task, we will partition the flight network into two disconnected subgraphs. The goal is to identify the minimum number of flights that need to be removed in order to disconnect the network into two separate parts.

After partitioning, we will visualize the original flight network and the resulting two subgraphs.

### 5. Finding and Extracting Communities (Q5)

Communities in a network are groups of airports that are highly interconnected. For this task, we focus on identifying communities at the city level.

We will use graph analysis to detect these communities and visualize the results. We will also check whether two specific cities belong to the same community.

