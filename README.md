# EC2-ML-Inference-Performance-Simulator
Overview
The EC2 ML Inference Performance Simulator is a Java-based tool designed to evaluate and compare the performance of machine learning inference tasks on AWS EC2 instances. This simulator specifically focuses on instances equipped with standard CPUs and those enhanced with AWS Inferentia chips, providing insights into the computational efficiency and cost-effectiveness of these configurations.

Features
Simulation of ML Inference: Simulate machine learning inference on different EC2 instance types.
Comparison Metrics: Compare performance between CPU-based instances and Inferentia-equipped instances.
Scalable Architecture: Utilizes Java HashMaps for efficient data management, allowing easy updates and scalability.
Data Structures and OOP Practices: Demonstrates the use of advanced data structures and object-oriented programming principles in a real-world application.

Architecture
InstanceType.java: Defines the properties of EC2 instances.
PerformanceMetrics.java: Manages and stores performance data.
SimulationEngine.java: Core logic for running simulations.
App.java: Main entry point that sets up and triggers simulations.
