# EC2 ML Inference Performance Simulator

## Overview
The EC2 ML Inference Performance Simulator (E-MIPS) is a Java-based tool designed to simulate the performance of different AWS EC2 instance types, particularly focusing on the impact of AWS Inferentia chips on machine learning inference tasks. This simulator helps users evaluate the potential benefits of Inferentia-equipped instances compared to standard CPU-based instances in terms of computational power and performance efficiency.

## Features
- Simulate and compare the performance of various EC2 instances.
- Evaluate the impact of AWS Inferentia chips on machine learning inference.
- Easy to extend with more instance types and performance metrics.

## Architecture
The E-MIPS project is structured into several Java classes each responsible for a distinct part of the simulation process:

### InstanceType
This class represents different types of EC2 instances. Each instance is characterized by its name, whether it is equipped with an AWS Inferentia chip, and a simplified compute power metric.

### PerformanceMetrics
Manages and stores the performance data for each instance type. It allows for adding new performance metrics and retrieving stored metrics for display.

### SimulationEngine
The core class that orchestrates the setup and execution of performance simulations. It initializes the instances, simulates their performance based on predefined logic, and collects results.

### App
Contains the `main` method, which serves as the entry point for the simulator. It sets up the simulation with predefined instance types, triggers the simulation process, and displays the results.
