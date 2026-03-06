# System Context – Digitale Bürger-Services Plattform

Dieses Dokument beschreibt den Kontext der Plattform innerhalb der Landesbehörde und deren Interaktion mit externen und internen Akteuren.

Das Ziel des System Context Diagrams ist es, die wichtigsten Benutzer und externen Systeme darzustellen.

---

# Akteure

## Bürger

Bürger nutzen die Plattform, um:

- Anträge zu stellen
- Dokumente hochzuladen
- Status von Verfahren einzusehen
- Bescheide abzurufen

---

## Sachbearbeiter

Sachbearbeiter nutzen das System zur:

- Prüfung von Anträgen
- Bearbeitung von Vorgängen
- Kommunikation mit Bürgern
- Dokumentation von Entscheidungen

---

## Abteilungsleitung

Die Leitung nutzt die Plattform für:

- Monitoring
- Reporting
- Prozessübersicht
- Entscheidungsunterstützung

---

## IT-Betrieb

Der IT-Betrieb ist verantwortlich für:

- Betrieb der Infrastruktur
- Monitoring
- Incident Management
- Sicherheitsüberwachung

---

# Externe Systeme

## Identity Provider

Authentifizierung der Benutzer.

Beispiele:

- Behörden-SSO
- Bürgerkonto

---

## Dokumentenarchiv

Langzeitarchivierung von Dokumenten.

---

## E-Mail / Benachrichtigungssystem

Versand von Statusmeldungen und Bescheiden.

---

# System Context Diagram
    Bürger
       |
       v
       +----------------------------+
| Digitale Bürgerplattform |
+----------------------------+
| | |
v v v
Sachbearbeiter DMS Identity Provider
|
v
Abteilungsleitung

---

# Ziele

Der Systemkontext zeigt:

- wer das System nutzt
- welche externen Systeme integriert sind
- welche Organisationseinheiten beteiligt sind
