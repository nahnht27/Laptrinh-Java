# 3. Non-Functional Requirements

| ID | Category | Requirement |
|---|---|---|
| NFR-P01 | Performance | Mobile application shall detect nearby iBeacon devices and display corresponding heritage information within 2 seconds under normal operating conditions. |
| NFR-P02 | Performance | At least 95% of web/API requests shall complete within 2 seconds under normal operating conditions. |
| NFR-P03 | Performance | Standard dashboard reports shall be generated within 5 seconds. |
| NFR-U01 | Usability | The platform shall provide an intuitive interface suitable for domestic and international visitors with minimal learning effort. |
| NFR-U02 | Usability | Major visitor tasks such as viewing artifact information, navigation and changing language should require no more than 3–5 interactions. |
| NFR-U03 | Usability | The web platform shall support responsive layouts and the mobile application shall support different screen sizes. |
| NFR-S01 | Security | Communications among mobile/web clients and backend services shall use HTTPS/TLS 1.2 or above. |
| NFR-S02 | Security | Authentication and authorization shall follow Role-Based Access Control (RBAC). |
| NFR-S03 | Security | Personal and operational data shall be protected against unauthorized access. |
| NFR-SC01 | Scalability | The system shall support at least 500 concurrent users without significant performance degradation. |
| NFR-SC02 | Scalability | The system shall support multiple heritage sites, thousands of artifacts and hundreds of deployed iBeacon devices. |
| NFR-SC03 | Scalability | The backend architecture shall permit future horizontal scaling. |
| NFR-AV01 | Availability | The platform shall maintain at least 99% availability during normal operating periods. |
| NFR-AV02 | Availability | When beacon communication fails, visitors shall still be able to manually access previously loaded artifact information. |
| NFR-R01 | Reliability | Beacon detection shall be accurate enough to avoid duplicate notifications within the same beacon coverage area. |
| NFR-R02 | Reliability | Visitor interaction data, heritage content and statistical data shall be synchronized reliably. |
| NFR-R03 | Reliability | The system shall gracefully recover from temporary network interruptions. |
| NFR-M01 | Maintainability | The architecture shall use clear modular separation between Mobile Application, Backend API, Beacon-related functionality and Web Administration Platform. |
| NFR-M02 | Maintainability | REST APIs shall be documented using OpenAPI/Swagger. |
| NFR-M03 | Maintainability | The architecture shall leave clear extension points for future AI recommendation, AR and smart-city integrations. |
