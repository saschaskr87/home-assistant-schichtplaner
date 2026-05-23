# Statistics System

## 🇩🇪 Ziel des Statistiksystems

Das Statistiksystem wurde entwickelt, um:

* Jahresstatistiken
* Schichtsummen
* Verlaufsauswertungen
* Familienereignisse

performant und persistent innerhalb von Home Assistant bereitzustellen.

---

## 🇬🇧 Goal of the Statistics System

The statistics system was developed to provide:

* yearly statistics
* shift summaries
* historical analysis
* family events

in a performant and persistent way within Home Assistant.

---

# 🇩🇪 Ursprüngliche Probleme

Die erste Statistikversion arbeitete direkt innerhalb von Lovelace-Karten.

Dies führte zu:

* Mikrorucklern
* langen Ladezeiten
* hoher CPU-Last
* instabilen Aktualisierungen

Besonders problematisch:

* vollständige Kalenderjahresabfragen
* häufige Dashboard-Reloads
* asynchrone Kalenderupdates

---

# 🇬🇧 Original Problems

The first statistics version operated directly inside Lovelace cards.

This caused:

* micro stutters
* long loading times
* high CPU usage
* unstable updates

Especially problematic:

* full calendar year parsing
* frequent dashboard reloads
* asynchronous calendar updates

---

# 🇩🇪 Lösungskonzept

Die Statistik wurde später ausgelagert in:

* dedizierte Scripts
* persistente Helper
* zeitbasierte Filterlogik

Die Ergebnisse werden dauerhaft gespeichert in:

```yaml
input_text.stats_person_a_fruehschicht
```

Dadurch muss die Statistik nicht permanent neu berechnet werden.

---

# 🇬🇧 Solution Concept

The statistics system was later moved into:

* dedicated scripts
* persistent helpers
* time-based filter logic

The results are permanently stored inside:

```yaml
input_text.stats_person_a_fruehschicht
```

This prevents constant recalculation of statistics.

---

# 🇩🇪 Zeitlogik statt Textlogik

Die ursprüngliche Statistik filterte nach Begriffen wie:

```yaml
Frühschicht
```

Dies verursachte Probleme durch:

* Emojis
* Tippfehler
* unterschiedliche Schreibweisen

Die finale Lösung verwendet Zeitfenster:

```yaml
selectattr('start','search','T06:00')
```

---

# 🇬🇧 Time Logic instead of Text Logic

The original statistics system filtered using terms like:

```yaml
Frühschicht
```

This caused problems through:

* emojis
* typos
* naming differences

The final solution uses time windows:

```yaml
selectattr('start','search','T06:00')
```

---

# 🇩🇪 Finale Statistikarchitektur

```text
Google Calendar
        ↓
calendar.get_events
        ↓
Statistics Script
        ↓
input_text Speicherzellen
        ↓
Dashboard Anzeige
```

---

# 🇬🇧 Final Statistics Architecture

```text
Google Calendar
        ↓
calendar.get_events
        ↓
Statistics Script
        ↓
input_text storage helpers
        ↓
Dashboard display
```
