# ADR-001 – Einführung eines API Gateways

## Status
Accepted

## Kontext

Die bestehende IT-Landschaft der Behörde nutzt Punkt-zu-Punkt-Schnittstellen zwischen Systemen.

Probleme:

- hohe Kopplung
- schwer wartbare Integrationen
- Sicherheitsrisiken
- fehlende zentrale Steuerung

Für die Zielarchitektur wird eine API-basierte Integrationsstrategie benötigt.

---

## Entscheidung

Es wird ein zentrales API Gateway eingeführt.

Das Gateway übernimmt:

- Routing von API-Anfragen
- Authentifizierung
- Autorisierung
- Rate Limiting
- Monitoring
- Logging

---

## Konsequenzen

Vorteile:

- zentrale Steuerung von Schnittstellen
- bessere Sicherheit
- einfachere Integration neuer Systeme
- Monitoring und Logging

Nachteile:

- zusätzliche Infrastrukturkomponente
- initialer Implementierungsaufwand

---

## Betroffene Systeme

- DigitalAntragsService
- PrüfService
- WorkflowService
- DocuService
- BIService
