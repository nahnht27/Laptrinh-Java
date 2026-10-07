# Java Backend — Admin API Design

## 1. Overview

The Admin Web uses the Java 17 Spring Boot REST API as the backend service.

This document defines the main REST APIs required for the Heritage Site Administrator in Sprint 1.

The APIs cover:
- Heritage Site Management
- Artifact Management
- Multimedia Management
- iBeacon Management
- Beacon Deployment Location Management
- Translation Management
- Feedback Moderation
- Analytics Dashboard
- Statistical Report Export

> Note: These APIs are API requirements/design for Sprint 1. They are not implemented yet.

---

## 2. Admin API

### 2.1 Authentication

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/login` | Authenticate an Administrator |

### 2.2 Heritage Site Management

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/heritage-sites` | Retrieve and search heritage sites |
| `GET` | `/api/admin/heritage-sites/{siteId}` | Retrieve a heritage site by ID |
| `POST` | `/api/admin/heritage-sites` | Create a heritage site |
| `PUT` | `/api/admin/heritage-sites/{siteId}` | Update a heritage site |
| `DELETE` | `/api/admin/heritage-sites/{siteId}` | Delete a heritage site |

### 2.3 Artifact Management

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/artifacts` | Retrieve and search artifacts |
| `GET` | `/api/admin/artifacts/{artifactId}` | Retrieve an artifact by ID |
| `POST` | `/api/admin/artifacts` | Create an artifact |
| `PUT` | `/api/admin/artifacts/{artifactId}` | Update an artifact |
| `DELETE` | `/api/admin/artifacts/{artifactId}` | Delete an artifact |

### 2.4 Multimedia Management

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/multimedia` | Retrieve multimedia resources |
| `GET` | `/api/admin/multimedia/{multimediaId}` | Retrieve multimedia details |
| `POST` | `/api/admin/multimedia` | Upload and create multimedia resource |
| `PUT` | `/api/admin/multimedia/{multimediaId}` | Update multimedia resource |
| `DELETE` | `/api/admin/multimedia/{multimediaId}` | Delete multimedia resource |

### 2.5 iBeacon Management

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/beacons` | Retrieve and search iBeacon devices |
| `GET` | `/api/admin/beacons/{beaconId}` | Retrieve beacon details |
| `POST` | `/api/admin/beacons` | Register an iBeacon device |
| `PUT` | `/api/admin/beacons/{beaconId}` | Update / configure an iBeacon |
| `DELETE` | `/api/admin/beacons/{beaconId}` | Delete an iBeacon |

#### Beacon Assignment

| Method | Endpoint | Description |
|---|---|---|
| `PUT` | `/api/admin/beacons/{beaconId}/assignment` | Assign a beacon to an artifact or location |

### 2.6 Beacon Deployment Location

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/beacons/{beaconId}/location` | Retrieve beacon deployment location |
| `PUT` | `/api/admin/beacons/{beaconId}/location` | Update beacon deployment location |

The deployment location is intended to support management through the interactive map.

### 2.7 Translation Management

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/translations` | Retrieve translations |
| `GET` | `/api/admin/translations/{translationId}` | Retrieve translation details |
| `POST` | `/api/admin/translations` | Create a translation |
| `PUT` | `/api/admin/translations/{translationId}` | Update a translation |
| `DELETE` | `/api/admin/translations/{translationId}` | Delete a translation |

### 2.8 Feedback Management

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/feedback` | Retrieve visitor feedback and reviews |
| `GET` | `/api/admin/feedback/{feedbackId}` | Retrieve feedback details |
| `PUT` | `/api/admin/feedback/{feedbackId}/moderate` | Moderate visitor feedback |

Feedback creation is performed by the Visitor side, while the Administrator is responsible for moderation.

### 2.9 Analytics Dashboard

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/analytics` | Retrieve analytics data for the dashboard |

The analytics API may provide:
- Visitor statistics
- Artifact popularity
- Interaction frequency
- Language preferences
- Feedback statistics

### 2.10 Statistical Reports

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/admin/reports/export` | Export statistical reports |

Supported report formats:
- PDF
- Excel

---

## 3. CRUD Operations

| Entity / Module | Create | Read | Update | Delete | Special Operation |
|---|:---:|:---:|:---:|:---:|---|
| Heritage Site | ✓ | ✓ | ✓ | ✓ | Search |
| Artifact | ✓ | ✓ | ✓ | ✓ | Search |
| Multimedia | ✓ | ✓ | ✓ | ✓ | Upload |
| iBeacon | ✓ | ✓ | ✓ | ✓ | Configure / Assign |
| Beacon Deployment Location | — | ✓ | ✓ | — | Interactive Map |
| Translation | ✓ | ✓ | ✓ | ✓ | Language |
| Feedback | — | ✓ | ✓ | — | Moderate |
| Analytics | — | ✓ | — | — | Dashboard |
| Reports | — | — | — | — | Export |

### CRUD Notes

- **Heritage Site** and **Artifact** require full CRUD operations.
- **Multimedia** requires create/upload, read, update and delete operations.
- **iBeacon** requires registration, configuration, assignment and management.
- **Beacon Deployment Location** is managed as part of beacon deployment rather than as a standalone CRUD entity.
- **Translation** requires CRUD operations for multilingual content.
- **Feedback** is created by Visitors and managed/moderated by the Administrator.
- **Analytics** is a read-only reporting operation.
- **Reports** use an export operation rather than standard CRUD.

---

## 4. Role and Permission

### 4.1 Role

The system defines the following administrative role for the Admin Web:

| Role | Description |
|---|---|
| `ADMIN` | Heritage Site Administrator |

The Administrator is responsible for managing heritage content, beacon infrastructure, feedback, analytics and reports.

### 4.2 Admin Permissions

| Permission | ADMIN |
|---|:---:|
| Admin Login | ✓ |
| Manage Heritage Sites | ✓ |
| Manage Artifacts | ✓ |
| Manage Multimedia | ✓ |
| Manage iBeacons | ✓ |
| Configure iBeacons | ✓ |
| Assign iBeacons | ✓ |
| Manage Beacon Deployment Location | ✓ |
| Manage Translations | ✓ |
| Moderate Feedback | ✓ |
| View Analytics Dashboard | ✓ |
| Export Statistical Reports | ✓ |

---

## 5. Authorization

Admin APIs require:

1. Authentication
2. `ADMIN` role authorization

```text
Admin
  |
  v
Login
  |
  v
Authentication
  |
  v
Check ADMIN Role
  |
  +-------------------+
  |                   |
  v                   v
Authorized         Unauthorized
  |                   |
  v                   v
Admin APIs        403 Forbidden