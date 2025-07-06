# Dynamic-Pricing-for-Urban-Parking-Lots
1. 🧾 Colab Notebook
A well-documented and modular Google Colab notebook is attached.

All code cells include clear comments explaining the logic, transformations, model assumptions, and visualization steps.

The notebook follows a chronological flow:

Data loading and preprocessing

Feature engineering

Real-time simulation with Pathway

Pricing model implementation

Bokeh-based interactive visualizations

Model comparison and analysis

2. 📊 Models Implemented
We developed and compared three distinct pricing models:

Model	Name	Basis	Formula Summary
1	Occupancy-Based	Parking capacity utilization	Price = Base + α × (Occupancy / Capacity)
2	Demand-Based	Real-time features + ML	Price = f(Occupancy, VehicleType, QueueLength, ...)
3	Competitor-Based	Competitive pricing strategy	Price = Avg(Model1, Model2) × Competitor Adjustment

3. 📈 Demand Function Explanation
Our demand estimation relies on a composite function using variables:

🔧 Variables considered:
Occupancy (real-time)

Vehicle Type (car, bike, truck, etc.)

Queue Length at entry

Nearby Traffic Condition (low/average/high)

Special Day indicator

📐 Demand Function (Model 2 - ML Based):
We treat demand as a non-linear function of the above variables and train a regression model (e.g., Random Forest or XGBoost) to learn the mapping:

Price
=
𝑓
(
Occupancy
,
QueueLength
,
VehicleType
,
TrafficCondition
,
IsSpecialDay
)
Price=f(Occupancy,QueueLength,VehicleType,TrafficCondition,IsSpecialDay)
This allows the price to adapt to complex demand patterns in real time.

4. 📎 Assumptions
Price Elasticity: As demand rises (e.g., more vehicles/traffic), users are likely to tolerate a modest price increase.

Vehicle-Type Influence: Larger or high-emission vehicles (like trucks) contribute more to congestion and are charged higher rates.

No Prior Reservation: All pricing is calculated for on-spot usage, assuming users decide in real time.

Uniform Pricing Zones: No zonal bias; all pricing depends only on dynamic parameters.

5. 📉 Pricing Dynamics
🟦 Model 1 (Occupancy-Based):
Price grows linearly with occupancy levels.

Simple, interpretable, but not demand-sensitive.

🟧 Model 2 (Demand-Based ML):
Price is influenced by multiple real-time demand drivers.

Captures complexity, better suited for urban deployment.

🟩 Model 3 (Competitor-Based):
Blends Model 1 and 2 with adjustments to simulate competitive behavior.

Useful in commercial areas where other parking providers exist.

📁 Files Submitted
Dynamic_Pricing_Colab.ipynb: Notebook with full implementation and plots.

dynamic_pricing_output.csv: Final dataset with predictions from all models.

dynamic_pricing_report.pdf: Report summarizing methodology, models, and insights.
