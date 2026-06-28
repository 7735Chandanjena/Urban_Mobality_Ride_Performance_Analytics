<<<<<<< HEAD
# 🚗 OLA Data Analyst Project

## 📌 Project Overview
This project analyzes OLA ride data using **SQL** and **Power BI** to extract meaningful business insights about ride volumes, revenue, cancellations, and customer/driver ratings.

---

## 🛠️ Tools Used
- **MySQL** — Data querying and analysis
- **Power BI** — Interactive dashboards and visualizations
- **Excel/CSV** — Raw data source

---

## 📂 Repository Structure
```
Urban_Mobality_Ride_Performance_Analytics/
│
├── 📸 01_overview_dashboard.png
├── 📸 02_Vehicletype_Analysis_dashboard.png
├── 📸 03_Revenue_analysis.png
├── 📸 04_Revenue_analysis_Dashboard.png
├── 📸 05_Ratings_givenby_custome&drivers.png
├── 📊 ola project.pbix
└── 📖 README.md
```

---

## 🗄️ Dataset Columns
| Column | Description |
|--------|-------------|
| Date, Time | Ride date and time |
| Booking_ID | Unique booking identifier |
| Booking_Status | Success / Cancelled |
| Customer_ID | Unique customer identifier |
| Vehicle_Type | Type of vehicle booked |
| Pickup_Location | Ride start location |
| Drop_Location | Ride end location |
| Booking_Value | Fare amount |
| Payment_Method | Cash / UPI / Credit Card |
| Ride_Distance | Distance covered |
| Driver_Ratings | Rating given to driver |
| Customer_Rating | Rating given by customer |

---

## 🗄️ SQL Questions & Answers

### 1. Retrieve all successful bookings:
```sql
Create View Successful_Bookings As
SELECT * FROM bookings
WHERE Booking_Status = 'Success';
```

### 2. Find the average ride distance for each vehicle type:
```sql
Create View ride_distance_for_each_vehicle As
SELECT Vehicle_Type, AVG(Ride_Distance) as avg_distance
FROM bookings
GROUP BY Vehicle_Type;
```

### 3. Get the total number of cancelled rides by customers:
```sql
Create View cancelled_rides_by_customers As
SELECT COUNT(*) FROM bookings
WHERE Booking_Status = 'cancelled by Customer';
```

### 4. List the top 5 customers who booked the highest number of rides:
```sql
Create View Top_5_Customers As
SELECT Customer_ID, COUNT(Booking_ID) as total_rides
FROM bookings
GROUP BY Customer_ID
ORDER BY total_rides DESC LIMIT 5;
```

### 5. Get the number of rides cancelled by drivers due to personal and car-related issues:
```sql
Create View Rides_cancelled_by_Drivers_P_C_Issues As
SELECT COUNT(*) FROM bookings
WHERE cancelled_Rides_by_Driver = 'Personal & Car related issue';
```

### 6. Find the maximum and minimum driver ratings for Prime Sedan bookings:
```sql
Create View Max_Min_Driver_Rating As
SELECT MAX(Driver_Ratings) as max_rating,
MIN(Driver_Ratings) as min_rating
FROM bookings WHERE Vehicle_Type = 'Prime Sedan';
```

### 7. Retrieve all rides where payment was made using UPI:
```sql
Create View UPI_Payment As
SELECT * FROM bookings
WHERE Payment_Method = 'UPI';
```

### 8. Find the average customer rating per vehicle type:
```sql
Create View AVG_Cust_Rating As
SELECT Vehicle_Type, AVG(Customer_Rating) as avg_customer_rating
FROM bookings
GROUP BY Vehicle_Type;
```

### 9. Calculate the total booking value of rides completed successfully:
```sql
Create View total_successful_ride_value As
SELECT SUM(Booking_Value) as total_successful_ride_value
FROM bookings
WHERE Booking_Status = 'Success';
```

### 10. List all incomplete rides along with the reason:
```sql
Create View Incomplete_Rides_Reason As
SELECT Booking_ID, Incomplete_Rides_Reason
FROM bookings
WHERE Incomplete_Rides = 'Yes';
```

---

## 📊 Power BI Dashboards

### 1. Overall
- **Ride Volume Over Time** — Time-series chart showing rides per day/week
- **Booking Status Breakdown** — Pie chart showing Success vs Cancelled rides

### 2. Vehicle Type
- **Top 5 Vehicle Types by Ride Distance** — Bar chart ranking vehicle types by distance

### 3. Revenue
- **Revenue by Payment Method** — Stacked bar chart (Cash, UPI, Credit Card)
- **Top 5 Customers by Total Booking Value** — Leaderboard of top spenders
- **Ride Distance Distribution Per Day** — Histogram of daily ride distances

### 4. Cancellation
- **Cancelled Rides Reasons (Customer)** — Bar chart of customer cancellation reasons
- **Cancelled Rides Reasons (Driver)** — Bar chart of driver cancellation reasons

### 5. Ratings
- **Driver Ratings Distribution** — Box plot of driver ratings by vehicle type
- **Customer vs Driver Ratings** — Scatter plot comparing both ratings

---

## 🔍 Key Insights
- UPI is one of the most used payment methods
- Prime Sedan has notable driver rating patterns
- Top 5 customers contribute significantly to total booking value
- Cancellation reasons vary between customers and drivers

---

## 👨‍💻 Author
**Chandan Jena**
GitHub: [7735Chandanjena](https://github.com/7735Chandanjena)
=======
# Urban_Mobality_Ride_Performance_Analytics
Developed a dashboard to analyze ride bookings, focusing on success and cancellation rates. Identified trends across time and locations, including peak cancellation periods and driver vs customer cancellations. Visualized key KPIs to support data-driven decisions,  optimize operations, and enhance customer experience.
>>>>>>> 8ea4a865269e7ece8d7027cc38270b0b072ddbd3
