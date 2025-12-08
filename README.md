
# **UK Job Change Analysis – Tableau Visualisation Project**

This repository contains a Tableau visualisation project based on the **EMSI Job Change UK Dataset**.

## **Aim**
The goal of this analysis is to explore job growth and decline across UK industries and cities by creating interactive visualisations and a combined dashboard.

---

## **Dataset**

**EMSI JobChange UK Dataset:**
The dataset includes two worksheets:

* **1 digit** – high-level industry categories and city data
* **2 digit** – more granular industry sub-categories and percentage change values

These worksheets were linked in Tableau using the shared **Country** field.

---

## **Visualisations Created**

### **1. Bar Chart – Percentage Job Change by Sub-Category**

This visualisation shows percentage job change for each 2-digit industry category.

<img width="1715" height="903" alt="1. Bar Chart – Percentage Job Change by Sub-Category" src="https://github.com/user-attachments/assets/73f136fb-e00e-4ea5-87f2-c5c21a9e4e2e" />


**Key steps:**

* Loaded dataset via *Connect to a File → Microsoft Excel*.
* Added both sheets (“1 digit” and “2 digit”) to the canvas and defined their relationship using **Country**.
* Created a new worksheet and renamed it **“% Change by Sub-Category”**.
* Dragged **Industry (2 digit)** to Rows and **% Change (2 digit)** to Columns to generate a bar chart.
* Added colour encoding using **Industry (2 digit)** on the Colour card.
* Sorted industries by **% Change (2 digit)** in ascending order.
* Removed null values using Tableau’s built-in filter option.

**Outcome:**
A clear visual ranking of industries experiencing highest and lowest percentage job change.

---

### **2. UK Map – Percentage Change Across Cities**

This visualisation highlights job change geographically across major UK cities.

<img width="1645" height="847" alt="UK Map – Percentage Change Across Cities" src="https://github.com/user-attachments/assets/ea5d99ee-a3ed-4820-9965-50cb5e8f72fc" />


**Key steps:**

* Created a new worksheet titled **“Map of % Change”**.
* Dragged **City** (from “1 digit” sheet) into the canvas to generate map points.
* Dragged **% Change (1 digit)** to the Colour card to encode magnitude of change.
* Resolved unknown locations using *Edit Locations* and setting the country to **United Kingdom**; manually corrected unmatched cities.
* Switched to **Satellite Map** for better contrast and visibility.

**Outcome:**
An interactive geographic view showing which UK cities experienced the greatest job increases or decreases.

---

## **Calculated Fields**

To compare higher-level (1-digit) and detailed (2-digit) job changes, a calculated field was created:

```
[change] - [change (2 digit)]
```

This field represents the difference between the two sheets and was used in the bar chart to analyse variations across levels of industry aggregation.

---

## **Dashboard – UK Job Change Overview**

A combined dashboard titled **“% Job Change in UK”** was created to present an integrated view.

<img width="990" height="1001" alt="Dashboard – UK Job Change Overview" src="https://github.com/user-attachments/assets/e6dd2c1f-1100-4bfd-86bf-8c0b05bdf867" />


**Dashboard components:**

* **% Change by Sub-Category** bar chart
* **Map of % Change** geospatial chart

**Enhancements:**

* Dashboard title added and customised.
* Legends were made floating for a cleaner layout.
* Applied a filter to show **Top 10 cities** by % change:

  * *City → Filter → Top → By Field → Top 10 by SUM(% change)*.

**Outcome:**
A comprehensive, interactive dashboard summarizing both industry-level and city-level job change insights.

---

## **Tools & Technologies**

* **Tableau Desktop** for data visualisation
* **EMSI JobChange UK Dataset** (Excel)
* **Calculated fields, filters, map layers, sorting, and dashboard design** features in Tableau

---

## **Repository Structure**

```
/data                # EMSI Job Change dataset
/tableau             # Tableau project file (.twbx)
README.md            # Project documentation
```

---

## **Summary**

This project demonstrates:

* Data modelling across multiple sheets
* Bar chart analysis by industry sub-category
* Geospatial mapping of job change across UK cities
* Use of filters, calculated fields, and dashboard layout best practices

The resulting dashboard provides meaningful insights into how different sectors and regions across the UK have changed over time.
