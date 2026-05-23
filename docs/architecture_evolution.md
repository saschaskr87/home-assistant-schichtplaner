# Architecture Evolution

## 🇩🇪 Ursprüngliche Architektur

Die erste Version des Schichtplaners bestand aus einer einfachen monolithischen Struktur.

Alle:

* Schichten
* Personen
* Familienereignisse

wurden über ein einziges Dropdown-Menü verarbeitet.

Dies führte zu:

* Fehlbuchungen
* unübersichtlicher Bedienung
* falschen Kalendereinträgen
* schlechter Skalierbarkeit

---

## 🇬🇧 Original Architecture

The first version of the shift planner used a simple monolithic structure.

All:

* shifts
* persons
* family events

were processed through a single dropdown menu.

This resulted in:

* incorrect bookings
* poor usability
* wrong calendar entries
* poor scalability

---

# 🇩🇪 Einführung der Routinglogik

Später wurde das System auf eine dynamische Routinglogik umgestellt.

Dadurch erhielt jede Person:

* eigene Dropdowns
* eigene Schichtlogik
* eigene Kalenderziele

Die Routinglogik entschied dynamisch:

* welcher Kalender beschrieben wird
* welche Schicht verarbeitet wird
* welche Statistik aktualisiert wird

---

# 🇬🇧 Introduction of Routing Logic

Later the system was migrated to dynamic routing logic.

Each person received:

* dedicated dropdowns
* individual shift logic
* separate calendar targets

The routing logic dynamically decided:

* which calendar is written to
* which shift is processed
* which statistics are updated

---

# 🇩🇪 Statistik-Evolution

Die ursprüngliche Statistik arbeitete mit textbasierten Filtern.

Probleme entstanden durch:

* Emojis
* unterschiedliche Schreibweisen
* Kalenderänderungen
* Umlaute

Das System wurde später auf Zeitlogik umgestellt.

Beispiel:

ALT:

```yaml
selectattr('summary','search','Früh')
```

NEU:

```yaml
selectattr('start','search','T06:00')
```

---

# 🇬🇧 Statistics Evolution

The original statistics system used text-based filtering.

Problems occurred because of:

* emojis
* naming differences
* calendar modifications
* umlauts

The system was later migrated to time-based logic.

Example:

OLD:

```yaml
selectattr('summary','search','Früh')
```

NEW:

```yaml
selectattr('start','search','T06:00')
```

---

# 🇩🇪 Reload- und Timingprobleme

Während der Entwicklung entstanden Probleme durch:

* Reloads
* Race Conditions
* verzögerte Kalenderupdates
* doppelte Trigger

Dies führte zur Einführung:

* künstlicher Delays
* Triggerprüfungen
* Synchronisationslogik
* persistenter Statistik-Helfer

---

# 🇬🇧 Reload and Timing Problems

During development problems occurred due to:

* reloads
* race conditions
* delayed calendar updates
* duplicate triggers

This resulted in:

* artificial delays
* trigger validation
* synchronization logic
* persistent statistics helpers

---

# 🇩🇪 Finale Architektur

Die finale Architektur besteht aus mehreren Schichten:

```text
Frontend Layer
        ↓
Input Helpers
        ↓
Routing Scripts
        ↓
Calendar Layer
        ↓
Statistics Engine
        ↓
Persistent State Helpers
```

---

# 🇬🇧 Final Architecture

The final architecture consists of multiple layers:

```text
Frontend Layer
        ↓
Input Helpers
        ↓
Routing Scripts
        ↓
Calendar Layer
        ↓
Statistics Engine
        ↓
Persistent State Helpers
```
