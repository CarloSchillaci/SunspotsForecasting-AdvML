# SunspotsForecasting-AdvML
Analysis and forecasting on a simple, small dataset provided by "jbrownlee". I will showcase the usage of neural network models to try forecasting on time series data

The notebook is divided into five distinct tasks to ensure clarity and methodical progress through the data preparation, model building, and comparison stages.

---

### **Task 1: Data Acquisition and Preprocessing**

* **Objective:** Load the raw monthly sunspot data and prepare it for time series modeling.
* **Data Source:** Monthly mean total sunspot number from the provided public dataset.
* **Key Action:**
    * Load the data from the specified URL.
    * **Scale the data** using the `MinMaxScaler` (0 to 1 range) to normalize the values for optimal neural network training.

### **Task 2: Time Series Organization and Splitting**

* **Objective:** Transform the raw series into a supervised learning format and divide the data into training and testing sets.
* **Prediction Goal:** **One-step-ahead prediction** (predicting the sunspot number for the next month).
* **Key Action:**
    * Create **time series sequences** of a chosen input length (lookback window).
    * Split the data: **80%** for Training + Validation and **20%** for Testing.

### **Task 3: Simple RNN and Dense Network (1-Step Ahead)**

* **Objective:** Establish a performance baseline for a one-step-ahead forecast using a basic Recurrent Neural Network (RNN) and a simple Dense network for comparison.
* **Models:**
    1.  **Simple RNN:** A standard RNN layer trained on the time series data.
    2.  **Simple Dense Network:** A basic multi-layer perceptron (MLP) to evaluate the benefit of the sequential processing ability of the RNN.
* **Evaluation:**
    * Train both models.
    * **Visualization:** Plot the **real time series** against the **predicted values**, clearly indicating the start of the test set predictions.

### **Task 4: Multi-Step Ahead Forecasting (Up to 6 Steps)**

* **Objective:** Extend the forecasting horizon to predict **six months ahead** using the two different multi-step forecasting approaches studied.
* **Prediction Goal:** **Six-step-ahead prediction**.
* **Approaches to be tested:**
    1.  **Iterative/Recursive Prediction:** Using the model's output as the input for the next time step.
    2.  **Multi-Output Prediction:** Modifying the model to output all six steps simultaneously.
* **Comparison:**
    * Determine **which multi-step approach works better** for this dataset.
    * Compare the performance of the best multi-step RNN approach against a Simple Dense network configured for the six-step task.

### **Task 5: Advanced Sequential Models (LSTM/GRU)**

* **Objective:** Implement and compare more advanced recurrent architectures (LSTM and/or GRU) for both the one-step and multi-step forecasting tasks.
* **Models:**
    * **Long Short-Term Memory (LSTM) Network**
    * **Gated Recurrent Unit (GRU) Network** 
* **Evaluation:**
    * Apply the new models to both the **1-step-ahead (Task 3)** and **multi-step-ahead (Task 4)** configurations.
    * Analyze how the **gating mechanisms** in LSTM/GRU improve performance over the Simple RNN, especially with longer time dependencies.
