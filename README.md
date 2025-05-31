# Managerial Dashboard (Power BI)

This repository contains a Power BI report (“Managerial Dashboard”) developed as part of a university project in collaboration with Nokia. The dashboard visualizes and analyzes dummy alarm data, covering:

- **Location** of each alarm  
- **Company** associated with the alarm  
- **Income** impact metrics  
- **Problem solving duration**  
- **Classification** by urgency and difficulty  

> **Note:** All data in this report is synthetic (dummy) and for educational/demo purposes only.

---

## 📂 Repository Contents

- `managerial-dashboard.pbix`  
  - The main Power BI Desktop file.  
- `README.md`  
  - This documentation.

---

## ⚙️ Prerequisites

1. **Power BI Desktop**  
   - Download the **latest version** from Microsoft:  
     https://powerbi.microsoft.com/desktop/  
2. **MySQL Server** (or access to a MySQL instance)  
   - Data is stored in a MySQL database (e.g. via phpMyAdmin).  
3. **MySQL Connector for Power BI**  
   - Included with Power BI Desktop; just ensure you have network access and credentials.

---

## 🔗 Data Source & Setup

1. **Importing the CSV**  
   - A CSV file containing dummy alarm records has been imported into a MySQL database via phpMyAdmin.  
   - Table name: `alarms`  

2. **Configuring the Connection in Power BI**  
   1. Open `managerial-dashboard.pbix` in Power BI Desktop.  
   2. In the ribbon, select **Home → Transform data → Data source settings**.  
   3. Edit the MySQL connection:  
      - **Server**: `<your_mysql_server_address>`  
      - **Database**: `<your_database_name>`  
      - **Authentication**: Use your MySQL username & password.  
   4. Click **Refresh** to pull the `alarms` table into Power BI.

> **Tip:** If you need to swap to a different data source (e.g. real alarms data), simply update the table in your database or repoint the connection.

---

## 🚀 How to Use

1. Open **managerial-dashboard.pbix** in Power BI Desktop.  
2. Refresh the data (click **Refresh** in the Home tab).  
3. Navigate through the tabs/pages to explore:  
   - Overview KPIs (total alarms, avg. resolution time, etc.)  
   - Map view (geographical distribution by location)  
   - Company comparison (alarms by company & income impact)  
   - Urgency vs. Difficulty matrix  
4. Export visuals or publish to Power BI Service as needed.

---

## 🗂 Dashboard Structure

| Page / Tab              | Description                                                                              |
|-------------------------|------------------------------------------------------------------------------------------|
| **Overview**            | High-level KPIs: total alarms, avg. solve time, total income impact                      |
| **Geography**           | Interactive map showing alarms by location                                               |
| **Company Analysis**    | Bar/column charts comparing companies by #alarms and income impact                       |
| **Urgency & Difficulty**| Scatter/matrix chart classifying alarms by urgency (low→high) and difficulty (easy→hard) |

---

## ❓ Troubleshooting

- **Connection errors**  
  - Double-check your MySQL server address, database name, and credentials.  
  - Ensure your local firewall or network allows outgoing MySQL (TCP 3306) connections.  
- **Missing data**  
  - Confirm the `alarms` table exists and contains the expected columns:  
    ```sql
    id, location, company, income, solve_duration, urgency, difficulty
    ```

---

## 📝 Notes

- This project uses **dummy data** only; values are not representative of real-world alarms.  
- If you wish to extend or customize, consider adding:  
  - Real-time data ingestion (e.g. via APIs)  
  - Additional drill-through pages (e.g. alarm detail view)  
  - Role-based security settings in Power BI Service

---
