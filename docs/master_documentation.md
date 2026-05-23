# Master Documentation

## 🇩🇪 Projektziel

Der Schichtplaner wurde entwickelt, um ein flexibles, mehrbenutzerfähiges und mobiles Planungs- und Statistiksystem für Home Assistant bereitzustellen.

Das System kombiniert:

* Schichtplanung
* Familienkalender
* Statistiksysteme
* Mehrtagelogik
* Kalenderautomatisierung
* mobile Dashboardsteuerung
* historische Datenerhaltung

---

## 🇬🇧 Project Goal

The shift planner was developed to provide a flexible, multi-user and mobile planning and statistics system for Home Assistant.

The system combines:

* shift planning
* family calendars
* statistics systems
* multi-day logic
* calendar automation
* mobile dashboard control
* historical data preservation

---

# 🇩🇪 Systemarchitektur

Das Projekt wurde schrittweise in mehrere logische Ebenen aufgeteilt:

* Frontend Layer
* Routing Layer
* Calendar Layer
* Statistics Layer
* Synchronization Layer

Die Trennung der Ebenen verbesserte:

* Wartbarkeit
* Fehlersuche
* Performance
* Skalierbarkeit

---

# 🇬🇧 System Architecture

The project was gradually separated into multiple logical layers:

* Frontend Layer
* Routing Layer
* Calendar Layer
* Statistics Layer
* Synchronization Layer

The separation of layers improved:

* maintainability
* debugging
* performance
* scalability

---

# 🇩🇪 Wichtige Entwicklungsprobleme

Während der Entwicklung entstanden mehrere kritische Probleme:

* Geisterbuchungen
* Reload-Probleme
* Race Conditions
* Statistikinstabilität
* Kalender-Synchronisationsprobleme
* Hidden Dropdown States

Diese Probleme führten zur Entwicklung:

* dynamischer Routinglogik
* Zeitlogik statt Textlogik
* Reloadschutz
* künstlicher Delays
* persistenter Statistik-Helfer

---

# 🇬🇧 Important Development Problems

During development several critical problems occurred:

* ghost bookings
* reload problems
* race conditions
* statistics instability
* calendar synchronization issues
* hidden dropdown states

These problems resulted in the development of:

* dynamic routing logic
* time-based logic instead of text filtering
* reload protection
* artificial delays
* persistent statistics helpers

---

# 🇩🇪 Statistiksystem

Die ursprüngliche Statistik arbeitete textbasiert und erzeugte Probleme durch:

* Emojis
* unterschiedliche Schreibweisen
* Kalenderänderungen
* Umlaute

Später wurde das System auf Zeitlogik umgestellt.

Beispiel:

ALT:
selectattr('summary','search','Früh')

NEU:
selectattr('start','search','T06:00')

Dadurch wurde das Statistiksystem:

* stabiler
* reproduzierbarer
* performanter

---

# 🇬🇧 Statistics System

The original statistics system used text-based filtering and caused problems through:

* emojis
* naming differences
* calendar modifications
* umlauts

Later the system was migrated to time-based logic.

Example:

OLD:
selectattr('summary','search','Früh')

NEW:
selectattr('start','search','T06:00')

This made the statistics system:

* more stable
* more reproducible
* more performant

---

# 🇩🇪 Finaler Projektstatus

Der Schichtplaner entwickelte sich von einem einfachen privaten Kalenderprojekt zu einer vollständigen Home Assistant Planungsplattform.

Finale Hauptfunktionen:

* Mehrpersonenplanung
* mobile Dashboardsteuerung
* Familienkalender
* Statistiksystem
* Reloadschutz
* Doppelterminschutz
* Kalenderintegration
* Mehrtagelogik

---

# 🇬🇧 Final Project Status

The shift planner evolved from a simple private calendar project into a complete Home Assistant planning platform.

Final core features:

* multi-user planning
* mobile dashboard control
* family calendars
* statistics system
* reload protection
* duplicate protection
* calendar integration
* multi-day logic
