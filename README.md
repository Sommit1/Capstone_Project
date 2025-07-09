#  Dynamic Pricing System for Smart Parking
 ## Overview
This project implements a real-time dynamic pricing system for smart parking management using Pathway for streaming and Bokeh + Panel for real-time visualization.

The system adjusts parking prices dynamically based on factors like:

Parking occupancy

Queue length

Traffic conditions

Vehicle type

Special events

📈 Real-time data is simulated from historical records and visualized using live Bokeh-powered dashboards embedded with Panel.

## 🧰 Tech Stack

Layer	Tools / Libraries
Programming	Python 3
Streaming	Pathway
Visualization	Bokeh, Panel
Data Format	CSV
Platform	Google Colab

## Architecture Diagram

![Architecture Diagra](https://i.postimg.cc/hvTMYZkq/Screenshot-2025-07-09-214931.png)





## Architecture & Workflow
1. 📥 Data Ingestion
A CSV file containing historical parking data is streamed using Pathway.

pw.io.csv.read() or replay_csv() reads it as a real-time stream at fixed intervals.

2. 📊 Real-Time Price Computation
Two pricing models are applied on-the-fly:

✅ Model 1: Baseline Linear Model
Price = Base + α · (Occupancy / Capacity)

Simple linear price adjustment

Useful as a baseline reference

✅ Model 2: Demand-Based Pricing
Price = Base × (1 + λ × NormalizedDemand)

More realistic

Incorporates multiple features:

Occupancy rate

Queue length

Traffic level

Special day

Vehicle type

Both models run simultaneously on live data using Pathway's transformations.

3. 📈 Real-Time Visualization
Real-time outputs from both models are visualized using Bokeh interactive plots.

Pathway.plot() binds streaming data to a custom Bokeh chart.

Panel.serve() hosts the dashboard as a live visualization.

Plots include:

📉 Daily pricing trends

📊 Model 1 vs Model 2 comparisons

✅ Final Outcome
Fully interactive Colab-compatible system

Live pricing graphs

Smart price decisions per parking spot

Scalable for real-world parking management

