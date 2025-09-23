# Airlines Flight Data ✈️

This folder contains the dataset used for exploratory data analysis (EDA) of airline flights.  
The dataset provides detailed information about airlines, routes, schedules, and ticket pricing.  
It is suitable for analysis, visualization, and predictive modeling.

---

## 📂 Dataset Features

The cleaned dataset includes the following features:

1. **Airline**  
   The airline company name.  
   *Type:* Categorical (6 unique airlines)

2. **Flight**  
   Flight code of the plane.  
   *Type:* Categorical

3. **Source City**  
   City from which the flight departs.  
   *Type:* Categorical (6 unique cities)

4. **Departure Time**  
   Time period of departure, grouped into bins.  
   *Type:* Categorical (6 unique labels)

5. **Stops**  
   Number of stops between source and destination.  
   *Type:* Categorical (3 values)

6. **Arrival Time**  
   Time period of arrival, grouped into bins.  
   *Type:* Categorical (6 unique labels)

7. **Destination City**  
   City where the flight lands.  
   *Type:* Categorical (6 unique cities)

8. **Class**  
   Seat class (Business or Economy).  
   *Type:* Categorical (2 values)

9. **Duration**  
   Total travel time between cities (in hours).  
   *Type:* Continuous

10. **Days Left**  
    Days remaining until the trip (trip date − booking date).  
    *Type:* Derived numerical feature

11. **Price**  
    Ticket price of the flight.  
    *Type:* Target variable (continuous)

---

## 🚀 Usage

- Exploratory Data Analysis (EDA)  
- Data visualization of airlines, routes, and pricing    

---

## 📌 Notes
- Dataset has been cleaned and preprocessed.  
- Suitable for machine learning tasks such as regression and classification.  
