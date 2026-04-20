# Custom ALV Sales Order Report in SAP ABAP

**Capstone Project** 

BY :

**Name : Abhisekh Tewary ,
Roll No.: 2306005 ,
Branch: Information Technology ,
Batch: 2027 ,
Specialization: SAP ABAP Development**

---

## Project Overview

Standard SAP reports like VA05 provide limited flexibility and do not fully support custom business requirements. In real-world scenarios, users need a consolidated and interactive report that combines multiple datasets and provides meaningful insights.

This project develops a **Custom ALV (ABAP List Viewer) Report** that integrates sales order, item, and customer data into a single ALV Grid. It provides filtering, aggregation, and visual status indicators to improve decision-making and monitoring.

---

## Objectives

* Build a reusable ALV-based reporting solution
* Combine data from multiple SAP tables using optimized queries
* Provide dynamic filtering options
* Implement business logic for order status visualization
* Enable aggregation and structured display of data

---

## Key Features

### 1. Selection Screen

The report allows users to filter data using:

* `S_DATE` — Sales order creation date (mandatory)
* `P_VKORG` — Sales organization (default: 1000)

---

### 2. Data Integration

Data is retrieved using INNER JOIN across:

* VBAK — Sales Order Header
* VBAP — Sales Order Item
* KNA1 — Customer Master

---

### 3. Order Status Logic

Order status is determined using creation date comparison with system date:

* Red (`C610`) — Orders older than 30 days
* Yellow (`C510`) — Orders between 15–30 days
* Green (`C310`) — Recent or processed orders

---

### 4. ALV Grid Functionalities

* Dynamic field catalog generation
* Subtotals for:

  * Net Value (`NETWR`)
  * Quantity (`KWMENG`)
* Zebra pattern for better readability
* Automatic column width optimization
* Row-wise color highlighting
* Structured tabular output

---

## Technical Details

| Component       | Details                      |
| --------------- | ---------------------------- |
| SAP System      | ECC 6.0 / S/4HANA            |
| Language        | ABAP (7.50+)                 |
| Tool            | SE38                         |
| ALV Class       | CL_GUI_ALV_GRID              |
| Container       | CL_GUI_CUSTOM_CONTAINER      |
| Function Module | REUSE_ALV_FIELDCATALOG_MERGE |

---

## Program Structure

The program follows a modular approach using FORM routines:

1. **GET_DATA** — Fetches data using INNER JOIN
2. **APPLY_LOGIC** — Applies color coding logic
3. **BUILD_FCAT** — Generates field catalog dynamically
4. **DISPLAY_ALV** — Displays output in ALV Grid

---

## Highlights

* Modular coding improves readability and maintainability
* Dynamic field handling avoids hardcoding
* Real-time business logic using system date
* Built-in aggregation using ALV properties
* Clean and structured ALV display

---

## Future Enhancements

* Add more filters (Customer, Document Type)
* Integrate delivery status using LIPS table
* Implement email functionality for reports
* Convert to CDS View for better performance
* Extend to SAP Fiori application

---

## Output Screens

* Selection Screen
* ALV Report Output
* Color-coded Status View
* Subtotals Display

---

## Conclusion

This project demonstrates how a standard SAP report can be enhanced using ABAP and ALV to provide better usability, flexibility, and business insights. The solution is scalable and can be extended further using modern SAP technologies.

---

Submitted as part of SAP ABAP Capstone Project — April 2026
