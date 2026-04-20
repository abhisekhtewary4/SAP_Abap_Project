# Custom ALV Sales Order Report in SAP ABAP

**Capstone Project**
**Name:** Abhisekh Tewary
**Roll No.:** 2306005
**Branch:** Information Technology
**Batch:** 2027
**Specialization:** SAP ABAP Development

---

## Project Overview

Standard SAP transactions such as VA05 provide limited reporting capabilities and lack flexibility for custom business needs. In real-world scenarios, organizations require an integrated and interactive report that combines multiple datasets and supports quick decision-making.

This project develops a **Custom ALV (ABAP List Viewer) Report** that consolidates sales order data from multiple SAP tables and presents it in a structured ALV Grid. The report enables efficient monitoring and analysis through filtering, aggregation, and visual indicators.

---

## Problem Statement

Standard SAP reports do not provide:

* Flexible filtering options
* Combined view of header, item, and customer data
* Visual representation of order status
* Easy aggregation for analysis

This creates difficulty in quick and effective business decision-making.

---

## Objectives

* Develop a reusable ALV-based reporting solution
* Retrieve and integrate data from multiple SAP tables
* Implement business logic for order status tracking
* Provide dynamic filtering and structured output
* Enable aggregation and improved visualization

---

## Key Features

### 1. Selection Screen

The report includes a simple and user-friendly selection screen:

* `S_DATE` — Sales order creation date (mandatory)
* `P_VKORG` — Sales organization (default: 1000)

---

### 2. Data Retrieval & Integration

Data is fetched using optimized INNER JOIN across:

* VBAK — Sales Order Header
* VBAP — Sales Order Item
* KNA1 — Customer Master

---

### 3. Order Status Logic

Order status is calculated based on the difference between system date and creation date:

* Red (`C610`) — Orders older than 30 days
* Yellow (`C510`) — Orders between 15–30 days
* Green (`C310`) — Recent or on-track orders

---

### 4. ALV Grid Functionalities

* Dynamic field catalog generation
* Subtotals for:

  * Net Value (`NETWR`)
  * Quantity (`KWMENG`)
* Zebra pattern for readability
* Automatic column width optimization
* Row-level color highlighting
* Structured tabular output

---

## Technical Environment

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

1. GET_DATA — Fetches data using INNER JOIN
2. APPLY_LOGIC — Applies color coding logic
3. BUILD_FCAT — Generates field catalog dynamically
4. DISPLAY_ALV — Displays output in ALV Grid

---

## Key Highlights

* Modular and maintainable coding structure
* Dynamic field handling without hardcoding
* Real-time business logic using system date
* Efficient data processing using internal tables
* Enhanced visualization using color-coded rows
* Built-in aggregation for better analysis

---

## Future Enhancements

* Add filters for Customer and Document Type
* Integrate delivery tracking using LIPS table
* Implement email functionality
* Convert to CDS Views for better performance
* Extend to SAP Fiori application

---

## Output Screens

* Selection Screen
* ALV Report Output
* Color-coded Status View
* Subtotals Display

---

## Conclusion

This project demonstrates how standard SAP reporting can be enhanced using ABAP and ALV to deliver a flexible, interactive, and user-friendly solution. It improves data visibility and supports better business decision-making.

---

**Submitted as part of SAP ABAP Capstone Project — April 2026**

