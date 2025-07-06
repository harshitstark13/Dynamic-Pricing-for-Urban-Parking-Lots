# 🚗 Dynamic Pricing for Urban Parking Lots

An intelligent, real-time pricing engine for urban parking spaces using real-time traffic, vehicle, and demand data. This project leverages simulation, machine learning, and competitive pricing logic to dynamically update parking prices with fairness and efficiency.

---

## 📚 Table of Contents

- [📓 Colab Notebook](#-colab-notebook)
- [📊 Models Implemented](#-models-implemented)
- [📈 Demand Function](#-demand-function)
- [📎 Assumptions](#-assumptions)
- [📉 Pricing Dynamics](#-pricing-dynamics)
- [📦 Dataset](#-dataset)
- [🛠️ Tech Stack](#️-tech-stack)
- [📌 Setup & Execution](#-setup--execution)
- [🔍 Visualizations](#-visualizations)
- [📜 License](#-license)

---

## 🧾 Colab Notebook

A modular and well-documented [Google Colab notebook](link-to-your-notebook) is included.

> ✅ All code cells include clear comments explaining the logic, model assumptions, and visualization steps.

### Structure:
1. Data loading & preprocessing  
2. Feature engineering  
3. Real-time simulation (Pathway)  
4. Pricing model implementation  
5. Bokeh-based interactive visualizations  
6. Model comparison and evaluation  

---

## 📊 Models Implemented

| Model | Name             | Basis                        | Formula Summary                                       |
|-------|------------------|------------------------------|-------------------------------------------------------|
| 1     | **Occupancy-Based**  | Parking capacity utilization | `Price = Base + α × (Occupancy / Capacity)`           |
| 2     | **Demand-Based**     | Real-time features + ML      | `Price = f(Occupancy, VehicleType, QueueLength, ...)` |
| 3     | **Competitor-Based** | Competitive pricing strategy | `Price = Avg(Model1, Model2) × Competitor Adjustment` |

---

## 📈 Demand Function

We treat price as a **non-linear function** of key real-time features:

### 🔧 Variables Considered:
- `Occupancy`
- `VehicleType` (car, bike, truck, etc.)
- `QueueLength`
- `TrafficConditionNearby` (low / average / high)
- `IsSpecialDay`

### 📐 Model 2 (Demand-Based ML Pricing)
```math
Price = f(Occupancy, QueueLength, VehicleType, TrafficCondition, IsSpecialDay)
