# C4 Model – Architekturübersicht

Dieses Dokument beschreibt die Architektur mit dem C4 Modell. Das C4 Modell besteht aus vier Ebenen:

1 Systemkontext
2 Container
3 Komponente
4 Code

---

# Level 1 – Kontext

System:

Digitale Bürgerplattform

Akteure:

- Bürger
- Sachbearbeiter
- Leitung
- IT Betrieb

Externe Systeme:

- Identity Provider
- Dokumentenarchiv
- E-Mail System

---

# Level 2 – Container

Die Plattform besteht aus mehreren Containern.

Container:

Web Application  
Benutzeroberfläche für Bürger und Sachbearbeiter.

API Gateway  
Zentrale Schnittstelle.

Application Services  
Microservices mit Business Logik.

Datenbanken  
Persistente Speicherung.

---

# Level 3 – Komponente

Innerhalb der Application Services existieren mehrere Komponenten.

Beispiele:

DigitalAntragsService

PrüfService

WorkflowService

DocuService

NotificationService

BIService

---

# Level 4 – Code

Code-Struktur der Anwendung:

src/

application/  
domain/  
infrastructure/  
presentation/

---

# Architekturprinzipien

Microservices Architektur

API-first Integration

Zero Trust Security

Secure by Design

Privacy by Design
