# 9. Admin User Flow

## 9.1 Overview

The Admin User Flow describes the main navigation and functional flow of the
Heritage Site Administrator within the Smart Heritage system.

The administrator must successfully log in before accessing the administration
functions.

## 9.2 Admin User Flow

The main administration functions are:

1. Admin Login
2. Manage Heritage Sites & Artifacts
3. Manage Multimedia
4. Manage Languages / Translations
5. Manage iBeacon Devices
6. Manage Beacon Deployment Location
7. Moderate Feedback
8. View Analytics Dashboard
9. Export Reports

The administrator can select an available function from the Admin Menu and
continue managing the system until choosing to log out.

## 9.3 Main Flow

### 9.3.1 Admin Login

- The administrator performs Admin Login.
- The system validates the login credentials.
- If the login fails, the system displays a login error and allows the
  administrator to try again.
- If the login is successful, the administrator is directed to the Dashboard.

### 9.3.2 Manage Heritage Sites & Artifacts

The administrator can manage heritage sites and historical artifacts.

### 9.3.3 Manage Multimedia

The administrator can manage multimedia resources associated with heritage
content.

Supported multimedia resources include:

- Images
- Videos
- Audio guides
- Multilingual descriptions

### 9.3.4 Manage Languages / Translations

The administrator can manage supported languages and digital content
translations.

### 9.3.5 Manage iBeacon Devices

The administrator can manage iBeacon devices, including their configuration
and assignment to specific artifacts or locations.

### 9.3.6 Manage Beacon Deployment Location

The administrator can manage the deployment locations of beacon devices on an
interactive map.

### 9.3.7 Moderate Feedback

The administrator can view and moderate visitor feedback and reviews.

### 9.3.8 View Analytics Dashboard

The administrator can view the Analytics Dashboard to access visitor and
artifact-related analytics data.

The dashboard includes:

- Visitor statistics
- Artifact popularity
- Interaction frequency
- Language preferences
- User feedback

### 9.3.9 Export Reports

The administrator can export statistical reports for management activities and
tourism promotion.

Supported report formats include:

- PDF
- Excel

### 9.3.10 Logout

The administrator can log out from the administration platform.

After logout, the administrator is returned to the login page.

## 9.4 Flow Summary

```text
Admin Login
    |
    +-- Login Failed --> Display Login Error --> Admin Login
    |
    +-- Login Successful
            |
        Dashboard
            |
        Admin Menu
            |
            +-- Manage Heritage Sites & Artifacts
            |
            +-- Manage Multimedia
            |
            +-- Manage Languages / Translations
            |
            +-- Manage iBeacon Devices
            |
            +-- Manage Beacon Deployment Location
            |
            +-- Moderate Feedback
            |
            +-- View Analytics Dashboard
            |
            +-- Export Reports
            |
            +-- Logout
                    |
                Login Page