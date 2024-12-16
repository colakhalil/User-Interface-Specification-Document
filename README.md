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

| **Field Name**      | **Type**           | **Required** | **Notes**                    |
|----------------------|--------------------|--------------|------------------------------|
| **Username**         | Textbox            | Yes          | Input username for the user. |
| **Display Name**     | Textbox            | No           | Optional display name.       |
| **Phone**            | Textbox            | No           | Optional phone number.       |
| **Email**            | Textbox            | Yes          | User's email address.        |
| **User Roles**       | Dropdown           | Yes          | Options: Guest, Admin, SuperAdmin. |
| **Enabled**          | Checkbox (toggle)  | Yes          | Checked = Active, Unchecked = Disabled. |


#### **Behavior:**
- **User Roles Dropdown:** Enables one to select predefined roles (Guest, Admin, SuperAdmin).
- **Proof:**
- **Username** and **Email** are obligatory fields.
- Email field must be in a valid email format.
- **Action Taken:**
- Clicking **"Save User"** saves the user in the table.

---

## 3. Page Behavior

### 3.1 Standard View
- By default, all enabled users are displayed in the user table.
The "Hide Disabled User" checkbox is cleared.

Adding a Second User 3.2
1. Populate the user form fields.
2. Click Save User.
- **On Accomplishment:**
- The new user is in the table now.
- **On failure:**
- A pop-up error message is thrown (e.g., "Username or Email cannot be empty").

### 3.3 User Filtering - Check the **"Hide Disabled User"** checkbox to hide rows where "Enabled" is set to `false`.

### 3.4 Data Preservation - Click **Save User** to save the user information. - Provide visual feedback on success or failure.
