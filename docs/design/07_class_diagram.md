# 07. Class Diagram

## 1. Main Classes
- Role
- Language
- User
- HeritageSite
- Artifact
- Multimedia
- ArtifactTranslation
- BeaconDeploymentLocation
- iBeacon
- Favorite
- VisitorInteraction
- Feedback

## 2. Class Attributes
- Role: roleId, name
- Language: languageId, code, name
- User: userId, username, email, passwordHash
- HeritageSite: siteId, name, description, address, latitude, longitude
- Artifact: artifactId, name, description
- Multimedia: multimediaId, type, title, url
- ArtifactTranslation: translationId, title, description
- BeaconDeploymentLocation: locationId, name, description, latitude, longitude
- iBeacon: beaconId, uuid, major, minor, status
- Favorite: favoriteId, createdAt
- VisitorInteraction: interactionId, interactionType, interactedAt
- Feedback: feedbackId, rating, comment, status, createdAt

## 3. Class Relationships
- Role – User: One-to-Many
- Language – User: One-to-Many
- HeritageSite – Artifact: One-to-Many
- Artifact – Multimedia: One-to-Many
- Artifact – ArtifactTranslation: One-to-Many
- Language – ArtifactTranslation: One-to-Many
- HeritageSite – BeaconDeploymentLocation: One-to-Many
- BeaconDeploymentLocation – iBeacon: One-to-Many
- Artifact – iBeacon: Optional-to-Many
- User – Favorite: One-to-Many
- Artifact – Favorite: One-to-Many
- User – VisitorInteraction: One-to-Many
- Artifact – VisitorInteraction: One-to-Many
- iBeacon – VisitorInteraction: Optional-to-Many
- User – Feedback: One-to-Many
- Artifact – Feedback: One-to-Many

## 4. PlantUML Source
The UML class diagram source is represented in `07_class_diagram.puml`
