# 🚗 Dynamic Pricing for Urban Parking Lots  
*Summer Analytics 2025 – Capstone Project*

## 📚 Project Overview

This project implements a real-time dynamic pricing engine for 14 urban parking lots using historical occupancy data, queue lengths, traffic congestion, and vehicle types. Developed as part of the **Consulting & Analytics Club × Pathway** challenge, it includes three progressive pricing models built with **Pandas**, **NumPy**, and **Bokeh**.

---

## 📦 Dataset

The dataset (`dataset.csv`) contains:
- `ID`: Unique Parking Lot ID  
- `SystemCodeNumber`: Code identifier  
- `Capacity`, `Occupancy`, `QueueLength`: Real-time parking state  
- `VehicleType`: Type of incoming vehicle (car/bike/truck)  
- `TrafficConditionNearby`: Traffic congestion level  
- `IsSpecialDay`: 1 if holiday/event, else 0  
- `Latitude`, `Longitude`: Geo-location  
- `LastUpdatedDate`, `LastUpdatedTime`: Timestamps

---

## 🔍 Models Implemented

### 1️⃣ Linear Pricing Model
A baseline where price increases linearly with occupancy:

### 2️⃣ Demand-Based Pricing Model
Demand score computed using multiple features:
Price is clipped between $5 and $20.

### 3️⃣ Competitive Pricing Model
Adds competitor-aware logic based on geographic proximity using Haversine formula:
- If nearby lots are cheaper and current lot is full → price drops or reroute.
- If nearby lots are expensive → price may increase (up to $20).

---

## 📊 Visualization

Implemented using **Bokeh** for real-time pricing trends:
- Shows `Linear`, `Demand`, and `Competitive` prices.
- Live plots per parking lot with timestamps.

---

## ⚙️ Technologies

- Python 3  
- Pandas, NumPy  
- Bokeh (for visualization)  
- Pathway (for real-time simulation – not fully implemented here)

---

## 📁 Files

| File | Description |
|------|-------------|
| `Dynamic_Pricing_Notebook.ipynb` | Main notebook with all 3 models |
| `dataset.csv` | Dataset with parking records |
| `README.md` | Project documentation |

---

## 🚀 Future Scope

- Complete real-time ingestion using Pathway’s streaming engine.
- Suggest rerouting vehicles to alternate lots in real time.
- Deploy model via REST API or stream dashboard.

---

## 📌 Assumptions

- Vehicle weight: car = 1, bike = 0.5, truck = 1.5  
- Pricing is bounded between $5 and $20  
- Nearby lots are within 0.5 km radius  

---

## 📞 Contact

This repository is part of Summer Analytics 2025 by C&A Club, IITG.

