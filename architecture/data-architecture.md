# Data Architecture – Digitale Bürger-Services

Dieses Dokument beschreibt die Datenarchitektur der Plattform für digitale Bürgerleistungen einer Landesbehörde.

Ziel ist eine konsistente, sichere und nachvollziehbare Datenhaltung unter Berücksichtigung von:

- DSGVO
- BSI-Grundschutz
- Privacy by Design
- Data Governance

---

# Ziele der Datenarchitektur

Die Datenarchitektur verfolgt folgende Ziele:

- Zentrale Verwaltung von Stammdaten
- Vermeidung redundanter Datenspeicherung
- Sichere Speicherung sensibler Daten
- Nachvollziehbarkeit durch Audit-Logs
- Datenbereitstellung für Reporting und Analyse
- Einhaltung von Datenschutzanforderungen

---

# Daten-Domänen

Die Plattform verwendet mehrere logisch getrennte Datendomänen.

## 1. Bürgerstammdaten

Beschreibung:

Zentrale Stammdaten der Bürger, die Anträge stellen.

Beispiele:

- Name
- Adresse
- Kontaktinformationen
- Identifikationsnummern

Systeme:

- DigitalAntragsService
- IdentityGov

Sicherheitsmaßnahmen:

- Verschlüsselung
- Zugriff über Rollenmodell
- Minimierung der Datenspeicherung

---

## 2. Verfahrensdaten

Beschreibung:

Daten zu Verwaltungsverfahren und Anträgen.

Beispiele:

- Antragstyp
- Bearbeitungsstatus
- Entscheidung
- Zeitstempel

Systeme:

- PrüfService
- WorkflowService
- BIService

Sicherheitsmaßnahmen:

- Zugriffskontrolle
- Protokollierung aller Änderungen
- Integritätsprüfungen

---

## 3. Dokumentendaten

Beschreibung:

Alle Dokumente, die zu einem Antrag gehören.

Beispiele:

- Antragsdokumente
- Bescheide
- Anhänge

Systeme:

- DocuService

Sicherheitsmaßnahmen:

- Verschlüsselung (at rest)
- Zugriff über Workflow-Rollen
- Versionierung

---

## 4. Audit- und Protokolldaten

Beschreibung:

System- und Sicherheitsprotokolle.

Beispiele:

- Login-Versuche
- Änderungen an Datensätzen
- Zugriffe auf Dokumente

Systeme:

- IdentityGov
- Monitoring Plattform
- SIEM System

Ziel:

- Nachvollziehbarkeit
- Sicherheitsanalyse
- Compliance

---

## 5. Reporting- und Analyse-Daten

Beschreibung:

Aggregierte Daten für Management und Controlling.

Beispiele:

- Anzahl bearbeiteter Anträge
- Bearbeitungszeiten
- Prozesskennzahlen

Systeme:

- BIService
- Data Warehouse

Datenschutzmaßnahmen:

- Pseudonymisierung
- Aggregation
- Zugriff nur für berechtigte Rollen

---

# Datenfluss

Typischer Datenfluss innerhalb der Plattform:

1 Bürger stellt Antrag im DigitalAntragsService

2 Antrag wird im Verfahrensdatensystem gespeichert

3 Dokumente werden im DocuService archiviert

4 WorkflowService steuert Bearbeitungsprozesse

5 Audit-Logs werden zentral gespeichert

6 BIService aggregiert Daten für Reporting

---

# Data Governance

Die Data Governance stellt sicher, dass Daten korrekt verwaltet werden.

Wichtige Aspekte:

- klare Datenverantwortlichkeiten
- Datenklassifizierung
- definierte Zugriffsrechte
- Datenqualitätskontrollen
- regelmäßige Audits

---

# Datenschutzmaßnahmen

Die Plattform berücksichtigt folgende Datenschutzprinzipien:

Privacy by Design

Privacy by Default

Datensparsamkeit

Pseudonymisierung

Verschlüsselung sensibler Daten

Zugriff nur nach Rollen und Berechtigungen

---

# Technische Umsetzung

Datenbanktechnologien:

- PostgreSQL (Transaktionsdaten)
- Dokumentenspeicher (DocuService)
- Data Warehouse für BI

Sicherheitsmaßnahmen:

- Verschlüsselung der Datenbanken
- sichere Backups
- Zugriff über IdentityGov
- Audit-Logging

---

# Vorteile der Datenarchitektur

- konsistente Datenhaltung
- verbesserte Datenqualität
- sichere Speicherung sensibler Informationen
- bessere Entscheidungsgrundlagen für Leitung
- vollständige Nachvollziehbarkeit von Vorgängen
