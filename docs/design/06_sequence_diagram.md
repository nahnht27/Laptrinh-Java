## 6. Sequence Diagram

### 1. Main Participants
- **Visitor**: user of the Smart Heritage mobile application
- **Mobile App**: mobile application used to access heritage information
- **Backend API**: REST API that provides heritage data
- **HeritageSite**: heritage site data managed by the backend
- **Artifact**: historical artifact data
- **Multimedia**: multimedia resources associated with an artifact
- **iBeacon**: BLE device used to detect the visitor's proximity to an artifact or deployment location

### 2. Main Sequence Flows

#### 2.1 Heritage Site Information Flow
The Visitor requests heritage site information through the Mobile App.
1. Visitor opens the heritage map or requests heritage site information.
2. Mobile App sends a request to the Backend API.
3. Backend API retrieves the requested **HeritageSite** data.
4. Backend API returns the heritage site information.
5. Mobile App displays the information to the Visitor.

#### 2.2 Artifact Information Flow
The Artifact flow represents the main interaction after the Mobile App detects a nearby iBeacon.
1. iBeacon broadcasts a BLE signal from its deployment location.
2. Mobile App detects the iBeacon signal.
3. Mobile App sends the beacon information to the Backend API.
4. Backend API resolves the related deployment location and **Artifact**.
5. Backend API retrieves the corresponding **Artifact** data.
6. Backend API returns the artifact information.
7. Mobile App displays the artifact information to the Visitor.
8. The interaction may be recorded for visit history and analytics.

#### 2.3 Multimedia Information Flow
The Visitor requests multimedia content for an artifact.
1. Mobile App sends a request for multimedia resources of an **Artifact**.
2. Backend API retrieves the associated **Multimedia** resources.
3. Backend API returns the available multimedia information.
4. Mobile App displays the multimedia content to the Visitor.

### 3. Draft API
The following REST API endpoints are proposed for the Heritage Site, Artifact, and Multimedia data required in M2 Sprint 1.

#### 3.1 Heritage Site API
- GET /api/heritage-sites — Retrieve all heritage sites.
- GET /api/heritage-sites/{siteId} — Retrieve a specific heritage site by ID.

Example response:

{
  "siteId": 1,
  "name": "Heritage Site Name",
  "description": "Description of the heritage site",
  "address": "Heritage site address",
  "latitude": 10.762622,
  "longitude": 106.660172
}

#### 3.2 Artifact API
- GET /api/heritage-sites/{siteId}/artifacts — Retrieve artifacts belonging to a specific heritage site.
- GET /api/artifacts/{artifactId} — Retrieve a specific artifact by ID.

Example response:

{
  "artifactId": 1,
  "name": "Artifact Name",
  "description": "Description of the artifact"
}

#### 3.3 Multimedia API
- GET /api/artifacts/{artifactId}/multimedia — Retrieve multimedia resources associated with a specific artifact.

Example response:

{
  "multimediaId": 1,
  "type": "image",
  "title": "Artifact Image",
  "url": "https://example.com/media/artifact-1.jpg"
}

## 4. Sequence Diagram source 
- `08_sequence_heritage_site.puml` — Heritage Site information flow
- `08_sequence_artifact.puml` — iBeacon-based Artifact information flow
- `08_sequence_multimedia.puml` — Multimedia information flow