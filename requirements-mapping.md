# Requirements Mapping – Digitale Bürger-Services Landesbehörde

Dieses Dokument zeigt, **wo im Repository funktionale und nicht-funktionale Anforderungen beschrieben, umgesetzt oder dokumentiert sind**.  
Es dient als **Nachweis für Architektur-, Lösungs- und Governance-Kompetenz**.

---

## 1️⃣ Funktionale Anforderungen

| Funktionale Anforderung | Umsetzung / Service | Repository-Datei |
|-------------------------|------------------|-----------------|
| Digitale Antragserfassung | DigitalAntragsService | `application-architecture.md`, `ist-prozesse.md`, `soll-prozesse.md` |
| Plausibilitätsprüfung & interne Freigabe | PrüfService, WorkflowService | `application-architecture.md`, `ist-prozesse.md`, `soll-prozesse.md` |
| Dokumentenarchivierung | DocuService | `application-architecture.md`, `data-architecture.md` |
| Reporting & KPI-Auswertung | BIService | `application-architecture.md`, `data-architecture.md` |
| Benachrichtigung von Bürgern | NotificationService | `application-architecture.md`, `ist-prozesse.md` |
| Rollen & Berechtigungen zentral steuern | IdentityGov | `application-architecture.md`, `architecture-governance.md` |

---

## 2️⃣ Nicht-funktionale Anforderungen

| Nicht-funktionale Anforderung | Umsetzung / Konzept | Repository-Datei |
|-------------------------------|-------------------|-----------------|
| Sicherheit / Schutz sensibler Daten | Zero Trust Architektur, Secure by Design | `architecture-decisions/ADR-002-zero-trust.md`, `architecture-governance.md` |
| Datenschutz / DSGVO | Privacy by Design, Pseudonymisierung | `architecture-principles.md`, `architecture-governance.md` |
| Skalierbarkeit | Microservices, Containerisierung, API-Gateway | `application-architecture.md`, `architecture-decisions/ADR-001-api-gateway.md` |
| Verfügbarkeit / Monitoring | Zentralisiertes Logging & SIEM | `roadmap/transformation-roadmap.md`, `architecture-decisions/*.md` |
| Performance / schnelle Verarbeitung | Event-Streaming, Optimierte Services | `application-architecture.md` |
| Nachvollziehbarkeit / Auditability | Audit-Logs, Architecture Decision Records | `architecture-decisions/*.md`, `architecture-governance.md` |
| Compliance / BSI-Konformität | Architekturprinzipien, Architektur-Reviews | `architecture-principles.md`, `governance/architecture-governance.md` |

---

## 3️⃣ Architektur & Lösungsdokumentation

| Artefakt | Zweck | Repository-Datei |
|----------|-------|-----------------|
| Architekturdiagramm | Visualisierung von Layern, Services & Schnittstellen | `architecture-diagram.md` |
| Application Architecture | Detaillierte Beschreibung der Anwendungen | `application-architecture.md` |
| Data Architecture | Datenmodelle, Speicherorte, Zugriff | `data-architecture.md` |
| Security Architecture | Zero Trust, Secure by Design, Privacy by Design | `security-architecture.md` *(optional)* |
| Architecture Decisions (ADRs) | Dokumentation von Entscheidungen, Alternativen, Konsequenzen | `architecture-decisions/*.md` |
| Governance & Principles | Regeln, Verantwortlichkeiten, Architekturprinzipien | `governance/*.md` |
| Transformation Roadmap | Umsetzungsschritte & Zeitplan | `roadmap/transformation-roadmap.md` |
| Prozessmodelle | IST- und SOLL-Prozesse | `process-models/ist-prozesse.md`, `process-models/soll-prozesse.md` |

---

## 4️⃣ Fazit

Dieses Mapping zeigt:

- **Funktionale Anforderungen** → Services + Prozesse + Applikationen  
- **Nicht-funktionale Anforderungen** → Security, Datenschutz, Skalierbarkeit, Performance  
- **Dokumentation & Governance** → Nachvollziehbarkeit, Architekturentscheidungen, Roadmap  
