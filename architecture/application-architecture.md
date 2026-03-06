# Application Architecture

## Purpose

Dieses Dokument beschreibt die interne Architektur der Anwendung und die Struktur der wichtigsten Module.

## Architecture Style

Die Anwendung folgt einer **modularen, serviceorientierten Architektur** mit klar getrennten Verantwortlichkeiten.

Hauptprinzipien:

* Separation of Concerns
* Modularität
* Testbarkeit
* Skalierbarkeit

## Layers

### 1. Presentation Layer

Verantwortlich für Benutzerinteraktion.

Beispiele:

* Web UI
* Mobile UI
* REST / GraphQL Endpoints

Aufgaben:

* Eingaben validieren
* Requests an Application Layer weiterleiten
* Responses formatieren

---

### 2. Application Layer

Koordiniert die Business-Logik der Anwendung.

Aufgaben:

* Use-Cases orchestrieren
* Geschäftsregeln ausführen
* Domain Services aufrufen

Typische Komponenten:

* Controllers
* Application Services
* DTOs

---

### 3. Domain Layer

Kern der Business-Logik.

Beispiele:

* Entities
* Value Objects
* Domain Services
* Business Rules

Ziele:

* Framework-unabhängig
* klare Modellierung der Fachlogik

---

### 4. Infrastructure Layer

Technische Implementierungen für externe Systeme.

Beispiele:

* Datenbankzugriff
* externe APIs
* Messaging / Queues
* File Storage

Typische Komponenten:

* Repository Implementierungen
* API Clients
* Adapter

---

## Example Module Structure

```
src/
 ├─ application/
 │   ├─ services/
 │   ├─ use-cases/
 │   └─ dto/
 │
 ├─ domain/
 │   ├─ entities/
 │   ├─ value-objects/
 │   └─ services/
 │
 ├─ infrastructure/
 │   ├─ database/
 │   ├─ repositories/
 │   └─ external/
 │
 └─ presentation/
     ├─ controllers/
     └─ routes/
```

---

## Dependency Rule

Die Abhängigkeiten dürfen **nur nach innen zeigen**:

```
Presentation → Application → Domain
Infrastructure → Domain
```

Die Domain-Schicht darf **keine Abhängigkeiten zu äußeren Schichten** besitzen.

---

## Benefits

* klare Struktur
* bessere Wartbarkeit
* einfache Tests
* gute Skalierbarkeit
