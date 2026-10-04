# 1. Project Scope

## 1.1 Project goal

Smart Heritage is an iBeacon-based smart tourism system that connects physical heritage sites with digital content. The system automatically detects a visitor's proximity to historical artifacts using BLE/iBeacon technology and delivers relevant multimedia and multilingual information through a mobile application.

At the management side, a web administration platform manages heritage content, beacon infrastructure, visitor feedback, and analytics/reporting.

## 1.2 In-scope

### Visitor Mobile Application
- Visitor registration and login
- Visitor profile and preferred language
- Interactive heritage-site map
- Nearby-artifact detection through iBeacon/BLE
- Artifact information display
- Multimedia content: descriptions, images, videos, audio guides
- Continue viewing previously triggered artifact content after leaving beacon coverage
- Favorite artifacts
- Visit history
- Rating and feedback

### Web Administration Platform
- Administrator authentication
- Heritage site management
- Artifact management
- Multimedia and multilingual-content management
- iBeacon registration/configuration/assignment
- Beacon deployment-location management
- Feedback moderation
- Visitor analytics dashboard
- Statistical report export

### Backend
- Java 17 + Spring Boot REST API
- Authentication and authorization
- Heritage/content APIs
- Beacon and visitor-interaction APIs
- Feedback APIs
- Analytics/reporting APIs
- PostgreSQL persistence
- OpenAPI/Swagger documentation

### Infrastructure
- BLE/iBeacon devices at heritage sites
- Docker-based backend + PostgreSQL development/deployment setup

## 1.3 Out-of-scope / future extension

The following are not core requirements for the current implementation:
- Online ticket/payment processing
- E-commerce
- Social login
- AI-based tour recommendation
- AR experiences
- Smart-city platform integration

These can be considered future integrations after the core Smart Heritage platform is stable.

## 1.4 Main system actors

| Actor | Responsibility |
|---|---|
| Visitor | Uses the mobile application to explore heritage content and record interactions |
| Heritage Site Administrator | Manages heritage content, beacons, feedback, analytics and reports |
| iBeacon Device | Emits BLE beacon signals detected by visitor devices |

## 1.5 High-level product boundary

The system contains:
1. Visitor Mobile Application
2. Interactive Heritage Experience
3. Heritage Content Management
4. iBeacon Infrastructure Management
5. Visitor Analytics & Reporting
6. Digital Heritage Administration

The backend is the common integration layer between mobile/web clients and persistent data.
