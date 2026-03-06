# Deployment Architecture

Dieses Dokument beschreibt die technische Bereitstellung der Plattform.

---

# Infrastrukturmodell

Die Plattform wird in einer hybriden Infrastruktur betrieben.

Komponenten:

- Government Private Cloud
- On-Premises Infrastruktur
- Containerplattform

---

# Infrastrukturkomponenten

## Containerplattform

Technologie:

- Docker
- Kubernetes

Verantwortlich für:

- Skalierung der Microservices
- Service-Orchestrierung
- Load Balancing

---

## API Gateway

Zentrale Schnittstelle für alle Anwendungen.

Funktionen:

- Routing
- Authentifizierung
- Rate Limiting
- Monitoring

---

## Identity System

Zentrale Authentifizierung.

Funktionen:

- Single Sign-On
- Multi-Faktor-Authentifizierung
- Rollenverwaltung

---

## Datenbanken

Mehrere spezialisierte Datenbanken:

Transaktionsdaten  
PostgreSQL

Dokumentenarchiv  
Dokumentenspeicher

Reporting  
Data Warehouse

---

flowchart TB
    User["👤 Bürger / Client"]
    
    subgraph GPC["Government Private Cloud"]
        LB["Load Balancer"]
        APIGW["API Gateway"]
        
        subgraph K8S["Kubernetes Cluster"]
            DAS["DigitalAntragsService"]
            PS["PrüfService"]
            WS["WorkflowService"]
            NS["NotificationService"]
        end
        
        subgraph DBLayer["Datenbank Layer"]
            DAS_DB["DAS-DB"]
            PS_DB["PS-DB"]
            WS_DB["WS-DB"]
            NS_DB["NS-DB"]
        end
        
        LB --> APIGW
        APIGW --> DAS
        APIGW --> PS
        APIGW --> WS
        APIGW --> NS
        
        DAS --> DAS_DB
        PS --> PS_DB
        WS --> WS_DB
        NS --> NS_DB
        
        WS --> NS
    end
    
    User --> LB


---

# Sicherheitsaspekte

Zero Trust Prinzip:

- jeder Zugriff wird geprüft
- Netzwerksegmentierung
- MFA

Secure by Design:

- Sicherheitsprüfungen in CI/CD
- sichere Konfigurationen

Privacy by Design:

- Pseudonymisierung
- Datenminimierung
