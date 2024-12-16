# User Interface Specification Document  
## User Management Screen  

This document covers the UI specifications of the User Management Screen as per the attached design file. It includes all UI components, functional elements, and behavioral aspects of the page. 

---

## 1. Requirements
The user management interface shall meet the following requirements:

- Allow admins to create, update and manage users.
- Give a table of current users with information like **ID**, **Username**, **Email**, and **Enabled status**.
- Allow filtering, sorting, and interaction with user data within the table.
- Allow inputting of new users' details with a form. Add methods for user account activation or deletion.

---

## 2. UI Components  

### 2.1 User Table  
The user table displays a list of users with the following columns:  

| **Column Name**  | **Description**                  | **Actions**                    |
|------------------|----------------------------------|--------------------------------|
| **ID**           | Unique numeric identifier.       | Static, not editable.          |
| **Username**     | Displayed name of the user.      | Editable when creating/updating.|
| **Email**        | User's email address.            | Editable when creating/updating.|
| **Enabled**      | User status (true/false).        | Toggle between active/inactive.|

#### **Behavior:**
- **Sorting:** All columns are sortable (ascending/descending).
- **Filtering:** Add Username and Email search/filter functionality.
- **Hide Disabled Users:**
A checkbox to hide rows where "Enabled" is `false`.

---

### 2.2 User Form The form to the right is used to **add a new user**. The fields include:

| **Field Name**      | **Type**           |  **Notes**                    |
|----------------------|--------------------|------------------------------|
| **Username**         | Textbox            | Input username for the user. |
| **Display Name**     | Textbox            | Optional display name.       |
| **Phone**            | Textbox            | Optional phone number.       |
| **Email**            | Textbox            | User's email address.        |
| **User Roles**       | Dropdown           | Options: Guest, Admin, SuperAdmin. |
| **Enabled**          | Checkbox (toggle)  | Checked = Active, Unchecked = Disabled. |


#### **Behavior:**
- **User Roles Dropdown:** Enables one to select predefined roles (Guest, Admin, SuperAdmin).
- Email field must be in a valid email format.
- **Action Taken:**
- Clicking **"Save User"** saves the user in the table.

---

## 3. Page Behavior 

### 3.1 Default View 

* The user table, by default, displays all **enabled users**.
* By default, the **"Hide Disabled User"** checkbox is **unchecked**.
* The user can interact with the table as follows:
 
* **Sorting:** By default, the data in the table is sorted in ascending/descending order by column header clicking.

---
 
### 3.2 Adding a New User 
1. Fill in the **User Form** fields with the necessary information:  
   - **Username** 
   - **Display Name** 
   - **Phone**
   - **Email** 
   - **User Roles** (to choose from Guest, Admin, SuperAdmin)  
   - **Enabled** check box to set the status of the user  

2. Click **"Save User"** to submit the form.  

   - **On Success:**  
     - A confirmation message is displayed: * "User added successfully.
- The new user dynamically appears in the table.  

   - **On Failure:**  
     - A pop-up error message appears with the problem:  
       - *"Username or Email cannot be empty."*
       - *"Please enter a valid email address."*

---

### 3.3 User Filtering 
- To hide disabled users from the table: 
   - Check the **"Hide Disabled User"** checkbox. 
   - Rows where **Enabled** is set to `false` will be hidden. 

- To show all users again: 
   - Uncheck the **"Hide Disabled User"** checkbox. 

---

### 3.4 Data Preservation
- Click **"Save User"** to validate and persist user information.  
- **Visual Feedback:**  
  - On success, show confirmation.  
  - On failure, show clear error messages to the user.
