# 5. Use Case Diagram

## 5.1 Actors

- **Visitor** — primary mobile-app user
- **Heritage Site Administrator** — primary web-admin user
- **iBeacon Device** — external BLE signal source

Note: "System" from the original requirements is treated as **automated behavior inside the Smart Heritage system boundary**, not as an external UML actor.

## 5.2 Main use cases

### Visitor
- Register / Login
- Manage Profile & Language
- View Heritage Map
- Detect Nearby Artifact
- View Artifact Information
- View Multimedia Content
- Continue Viewing Artifact
- Manage Favorites
- View Visit History
- Rate Artifact / Submit Feedback

### Administrator
- Admin Login
- Manage Heritage Sites & Artifacts
- Manage Multimedia
- Manage Languages / Translations
- Manage iBeacon Devices
- Manage Beacon Deployment Location
- Moderate Feedback
- View Analytics Dashboard
- Export Reports

### Automated system behavior
- Process Beacon Signal
- Prevent Duplicate Notification
- Trigger New Artifact Notification
- Record Visitor Interaction
- Synchronize Data
- Deliver Language-specific Content
- Securely Store Data

## 5.3 Relationships

Important `include` relationships:

- `Detect Nearby Artifact` includes `Process Beacon Signal`
- `Detect Nearby Artifact` includes `Prevent Duplicate Notification`
- `View Artifact Information` includes `Deliver Language-specific Content`
- `View Artifact Information` includes `Record Visitor Interaction`
- `Admin Dashboard` includes `View Analytics Data`
- `Export Reports` includes `Generate Statistical Report`

## 5.4 PlantUML source

See `05_use_case_diagram.puml`.
