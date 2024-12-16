
New version:
# Payroll Management System Using Arduino

## Overview
This project presents an **Arduino-based payroll management system** that utilizes a finite state machine (FSM) to manage various functions such as adding accounts, handling payroll data, and displaying available SRAM and student IDs. The system features an RGB LCD shield for visual feedback and allows user interactions through serial commands and button inputs.

## Features
- **Payroll Account Management**:
  - Add, delete, and modify payroll accounts.
  - Manage job titles, grades, salaries, and pension statuses.
- **State Transitions**:
  - Switch between states like idle, main phase, and sub-states for account management.
- **Dynamic RGB Backlight**:
  - Indicate status with color-coded backlights.
- **Free RAM Display**:
  - Show the remaining SRAM using a library or manual calculation.
- **Student ID Display**:
  - Press and hold the select button for over 1 second to display the student ID and SRAM on a purple backlight.

## Finite State Machine (FSM)
The FSM manages different states:
1. **Idle State**: Awaits the serial command `BEGIN` to initiate.
2. **Main Phase**: Processes commands such as `ADD`, `GRD`, and `DEL`.
   - Sub-states include:
     - Listening for commands.
     - Navigating payroll accounts using up/down buttons.
     - Displaying the student ID.

## Data Structures
The project employs a `struct` to manage payroll records with the following fields:
- `id`: A unique 7-digit identifier.
- `grade`: An integer (1-9) indicating job importance.
- `title`: A string (3-17 characters) for the job title.
- `salary`: A floating-point number representing the salary.
- `pensionActive`: A boolean flag indicating whether the pension plan is active.

### Functions
- `handleAddCommand`: Adds new payroll accounts.
- `handlePensionActive`: Updates pension status.
- `handleJobGrade`: Adjusts job grades.
- `handleSalary`: Modifies or adds salary information.
- `handleJobDeletion`: Deletes accounts based on IDs.

## Hardware Requirements
- Arduino board.
