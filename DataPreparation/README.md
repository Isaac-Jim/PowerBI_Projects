

# **Transport Records Data Cleaning Documentation**

## **1. Data Source**

The dataset used for this project is titled **Transport Records**.
It contains delivery company logs with detailed trip information, including:

* **Trip_ID:** Unique identifier for each delivery trip
* **Date:** Date the trip was completed
* **Driver_Name:** Name of the driver assigned to the trip
* **Vehicle_Type:** Type of vehicle used
* **Departure_Location:** Starting point of the trip
* **Destination:** End point of the trip
* **Distance_km:** Total distance covered (in kilometers)
* **Fuel_Used_Liters:** Amount of fuel consumed during the trip
* **Amount_Charged:** Cost charged for the trip
* **Payment_Status:** Indicates whether the payment was completed or pending

This dataset was provided as part of a logistics performance tracking and cost analysis assignment.

---

## **2. Data Cleaning Steps**

Data cleaning was carried out using **Power Query** and basic Excel transformations to ensure accuracy, consistency, and readiness for analysis.
The following steps were taken:

### **a. Text Cleaning**

* Trimmed all text fields (such as *Driver_Name*, *Departure_Location*, and *Destination*) to remove leading and trailing spaces.
* Capitalized text in relevant columns to maintain consistency and improve readability.

### **b. Handling Missing Values**

* Used **Fill Down** and **Fill Up** operations in Power Query to fill missing values in columns like *Payment_Status* or *Vehicle_Type* where repeated records applied.
* Replaced missing numeric values (e.g., *Distance_km*, *Fuel_Used_Liters*) with appropriate **statistical measures** such as the **mean** or **median** based on the data’s distribution.
* Verified that no critical records (e.g., *Trip_ID* or *Date*) were missing after transformations.

### **c. Data Type Corrections**

To enable accurate computation and analysis, the following data type conversions were made:

* **Trip_ID** → *Text*
* **Date** → *Date*
* **Distance_km** → *Decimal Number*
* **Fuel_Used_Liters** → *Decimal Number*
* **Amount_Charged** → *Currency / Decimal Number*
* **Payment_Status** → *Text*

### **d. Consistency and Validation**

* Checked for and removed duplicate records based on *Trip_ID*.
* Ensured all numeric values were positive and within reasonable ranges (e.g., no negative distances or fuel usage).
* Verified that *Payment_Status* contained only valid entries such as “Paid” or “Pending, Unpaid.”

---

## **3. Challenges Faced**

1. **Inconsistent Text Entries:**
   Some location and driver name fields had irregular capitalization and spacing, which required multiple cleaning steps to fix.

2. **Missing Numeric Values:**
   Several records lacked values for *Fuel_Used_Liters* or *Distance_km*, requiring statistical imputation while ensuring data integrity.

3. **Data Type Mismatches:**
   Columns such as *Amount_Charged* and *Distance_km* were initially read as text due to formatting errors in the raw file. These had to be corrected manually.

4. **Duplicate and Outlier Records:**
   A few duplicate *Trip_IDs* and extreme values in distance or fuel usage were identified and removed or adjusted after verification.

---

## **4. Final Outcome**

After cleaning:

* The dataset is free from duplicates and formatting inconsistencies.
* All columns have correct data types.
* Missing values have been appropriately handled.
* The dataset is ready for accurate analysis, visualization, and reporting.
