# Architecture Diagram

## Overview

Dieses Dokument beschreibt das grundlegende Architekturdiagramm der Anwendung.
Es zeigt die wichtigsten Komponenten und deren Beziehungen.

## High-Level Architecture

```mermaid
flowchart TD

    User[User / Client]

    subgraph Frontend
        WebApp[Web Application]
        MobileApp[Mobile App]
    end

    subgraph API Layer
        APIGateway[API Gateway]
    end

    subgraph Backend Services
        AuthService[Authentication Service]
        AppService[Application Service]
        DataService[Data Service]
    end

    subgraph Data Layer
        DB[(Primary Database)]
        Cache[(Cache / Redis)]
        Storage[(Object Storage)]
    end

    User --> WebApp
    User --> MobileApp

    WebApp --> APIGateway
    MobileApp --> APIGateway

    APIGateway --> AuthService
    APIGateway --> AppService

    AppService --> DataService

    DataService --> DB
    DataService --> Cache
    DataService --> Storage
```

## Component Description

### Client Layer

* **Web Application** – Browserbasierter Zugriff auf das System
* **Mobile App** – Optionaler mobiler Zugang

### API Layer

* **API Gateway**

  * zentraler Einstiegspunkt
  * Routing zu Backend-Services
  * Rate Limiting / Logging

### Backend Services

* **Authentication Service**
  Verwaltung von Login, Tokens und Benutzerrechten

* **Application Service**
  Enthält die zentrale Business-Logik

* **Data Service**
  Abstraktionsschicht für Datenzugriffe

### Data Layer

* **Primary Database** – Persistente Daten
* **Cache** – Performance-Optimierung
* **Object Storage** – Dateien, Uploads, Assets

## Goals

* klare Trennung der Schichten
* skalierbare Services
* einfache Erweiterbarkeit
