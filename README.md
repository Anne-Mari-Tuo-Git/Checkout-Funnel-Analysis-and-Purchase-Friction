# Google Merchandise Store: Checkout Funnel Analysis

## 📌 Project Overview
This project analyzes the purchase journey and financial performance of the **Google Merchandise Store**. Using **Power BI**, I transformed raw e-commerce data into actionable business intelligence to identify where customers drop off and how to maximize revenue.

* **Data Source:** The analysis is based on the [Google Merchandise Sales Dataset] available on Kaggle (https://www.kaggle.com/datasets/mexwell/google-merchandise-sales-data).
* **Dataset Content:** It contains granular records of e-commerce activities, including **user events** (add-to-cart, checkout, purchase), **product catalogs** with pricing in USD, and **geographical/device data**.
* **Key Focus:** Analyzing the **12,545 "Add to Cart" events** to understand the **49% friction point** before checkout and calculating the total financial impact using custom **DAX measures**.


 ## 🛠️ Technologies Used

* Data Preparation:

* Analysis & Visualization:

* AI Assistance:

## 🏗️ Data Model & Relationships

The project follows a structured approach to ensure accurate calculations across the checkout funnel:

**Fact Table** (events1)**:** Contains core e-commerce events such as add_to_cart, begin_checkout, and purchase.

**Dimensions:**

items: Connected via item_id, providing product names and pricing in USD.

users: Connected via user_id to track unique purchaser behavior.

Relationships: Established a One-to-Many (*:1) relationship between the events and the item catalog, enabling granular revenue analysis.

