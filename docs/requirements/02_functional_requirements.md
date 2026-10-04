# 2. Functional Requirements

## 2.1 Visitor Requirements

| ID | Requirement |
|---|---|
| FR-V01 | The system shall allow a Visitor to register and log in to the mobile application. |
| FR-V02 | The system shall allow a Visitor to update a personal profile and select a preferred language. |
| FR-V03 | The system shall allow a Visitor to view an interactive map of heritage sites. |
| FR-V04 | The system shall automatically detect nearby historical artifacts using iBeacon technology. |
| FR-V05 | The system shall deliver relevant artifact information when a nearby artifact is detected. |
| FR-V06 | The system shall provide multimedia information including historical descriptions, images, videos and audio guides. |
| FR-V07 | The system shall allow a Visitor to continue viewing artifact information after leaving beacon coverage. |
| FR-V08 | The system shall allow a Visitor to save favorite artifacts. |
| FR-V09 | The system shall allow a Visitor to review visit history. |
| FR-V10 | The system shall allow a Visitor to rate artifacts and submit feedback. |

## 2.2 Administrator Requirements

| ID | Requirement |
|---|---|
| FR-A01 | The system shall allow an Administrator to securely log in to the administration platform. |
| FR-A02 | The system shall allow an Administrator to create, edit and manage heritage sites and artifacts. |
| FR-A03 | The system shall allow an Administrator to upload and manage multimedia resources and multilingual descriptions. |
| FR-A04 | The system shall allow an Administrator to register, configure and assign iBeacon devices to artifacts or locations. |
| FR-A05 | The system shall allow an Administrator to manage beacon deployment locations on an interactive map. |
| FR-A06 | The system shall allow an Administrator to manage supported languages and content translations. |
| FR-A07 | The system shall allow an Administrator to moderate visitor feedback and reviews. |
| FR-A08 | The system shall provide dashboards for visitor statistics, artifact popularity, interaction frequency, language preferences and feedback. |
| FR-A09 | The system shall allow an Administrator to export statistical reports in PDF or Excel format. |

## 2.3 System / automated requirements

| ID | Requirement |
|---|---|
| FR-S01 | The system shall continuously process nearby iBeacon/BLE signals for visitor proximity detection. |
| FR-S02 | The system shall prevent duplicate notifications while a Visitor remains within the same beacon coverage area. |
| FR-S03 | The system shall trigger relevant artifact information when the Visitor enters the coverage area of a different beacon. |
| FR-S04 | The system shall synchronize visitor interactions, beacon information and digital content between clients and backend services. |
| FR-S05 | The system shall record visitor interactions, visited artifacts and user preferences for analytics. |
| FR-S06 | The system shall deliver multilingual content according to the Visitor's language preference. |
| FR-S07 | The system shall securely store operational data and user information. |

## 2.4 Functional dependency

Typical visitor flow:

`Login → Select language → Enter heritage site → Detect beacon → Resolve artifact → Load content → Record interaction → Favorite / Feedback`

Typical administrator flow:

`Admin login → Manage site/content/beacon → Monitor feedback → View dashboard → Export report`
