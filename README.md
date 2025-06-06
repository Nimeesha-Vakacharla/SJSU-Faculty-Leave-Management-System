# SJSU-Faculty-Leave-Management-System
## Overview
This project implements an advanced Leave Management System for the faculty of the **Data Analytics Department at San Jose State University (SJSU)**, leveraging the **Model Context Protocol (MCP) Server** for a robust, automated, and user-friendly solution.

Key highlights:
- Faculty can check leave balances and apply for leaves.
- Integrated with **Claude Desktop** for natural language queries.
- Demonstrates skills in **server configuration**, **API development**, **in-memory DB management**, and **NLP integration**.

---

## Problem Statement

The SJSU Data Analytics Department required a system to:

- Check leave balances.
- Apply for leaves with:
  - No duplicate dates.
  - Sufficient leave balance.
  - No applications on holidays.
- Enable natural language interactions.
- Ensure scalability and reliability.

---

## Features Implemented

###  Check Leave Balance
- Faculty query leave balance via natural language.
- Returns current leave balance and history.

###  Apply for Leave
- Prevents duplicate applications.
- Verifies leave balance.
- Validates against holidays.
- Updates balance/history on success.

###  List All Employees
- Lists all faculty members for administrative use.

###  Retrieve Holiday Calendar
- Returns SJSU holiday list.

###  Natural Language Query Processing
- Integrated with **Claude Desktop**.
- Sample queries:
  - "How many leave days does Taehee Jeong have?"
  - "Apply for a leave on June 15, 2025, for Shih-Yu Chang."
  - "Can Guannan Liu apply on December 25, 2025?"

---

## Technical Implementation

### Technologies Used
- **MCP Server (FastMCP)**
- **Python**
- **JSON**
- **Claude Desktop**
- **Regular Expressions**
- **Datetime**

---

## Key Components

### `employee_leave.py`
- `EmployeeLeaveSystem` class:
  - Loads and manages faculty data + holidays.
  - Methods:
    - `check_leave_balance`
    - `apply_for_leave`
    - `get_all_employees`
    - `get_holiday_calendar`

### `leave_service.py`
- MCP API endpoints:
  - `check_leave_balance`
  - `apply_for_leave`
  - `get_all_employees`
  - `get_holiday_calendar`
- Uses stdio transport for Claude Desktop.

### `Mock_Data.json`
- Stores:
  - Faculty data: name, leave balance, history.
  - SJSU holiday calendar.

---

## How It Was Achieved

###  In-Memory Database Setup
- Data loaded from `Mock_Data.json`.
- Fallback to defaults if JSON fails.

### ⚙️ MCP Server Configuration
- MCP tools created using FastMCP decorators.
- Integrated with Claude Desktop.

###  Validation Logic
- Valid date format (`YYYY-MM-DD`).
- No duplicate entries.
- Sufficient leave balance.
- No holidays.

###  Claude Desktop Integration
- Natural language → API call → response.
- Fully conversational system.

---

## Example Workflow

###  Check Leave Balance
**Query:** "How many leave days does  Andrew Bond have?"  
**Response:**  
> "Andrew Bond currently has a leave balance of 8 days. His leave history includes December 12, 2024, January 2, 2025, January 15, 2025, and June 15, 2025."

###  Apply for Leave
**Query:** "Apply for a leave for Ming-Hwa Wang on June 16, 2025."  
**Response:**  
> "Leave successfully applied for June 16, 2025. Updated balance: 3 days."

###  Holiday Constraint
**Query:** "Apply for a leave for Sangjin Lee on December 25, 2025."  
**Response:**  
> "Cannot apply for leave on December 25, 2025, as it is a holiday."

---

## Achievements

-  Automated leave tracking.
-  Seamless MCP + Claude Desktop integration.
-  Robust validation (duplicates, holidays, balance).
-  Natural language interface.
-  Error-tolerant in-memory database.

---

## MCP Usage Skills Demonstrated

- MCP Server configuration with FastMCP.
- Designed MCP tool endpoints.
- Natural language → API routing with Claude Desktop.
- JSON-based dynamic data handling.
- Exception and validation handling.
- Modular and scalable architecture.



