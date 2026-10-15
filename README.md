# 🏠 Home Maintenance für Home Assistant / Home Maintenance for Home Assistant

**🌐 Sprache / Language:** [🇩🇪 Deutsch](#deutsch) · [🇬🇧 English](#english)

---

## Deutsch

Halte dein Zuhause in Schuss: Verfolge wiederkehrende Wartungsaufgaben direkt in Home Assistant!

Diese Custom Integration erinnert dich an regelmäßige Aufgaben wie den Wechsel von Luftfiltern, das Reinigen der Dachrinne oder das Testen der Rauchmelder – und zeigt dir, wann sie fällig sind.

### ✨ Funktionen

- 📋 Wiederkehrende Aufgaben anlegen (z. B. „Filter alle 90 Tage wechseln“)
- 🔔 Für jede Aufgabe wird eine Entität erstellt – nutzbar für Automationen und Dashboards
- ✅ Aufgaben als erledigt markieren; das nächste Fälligkeitsdatum wird automatisch berechnet
- 🏷️ Optional: Aufgabe per NFC-Tag als erledigt markieren
- 📊 Übersichtliches Panel direkt in der Home-Assistant-Seitenleiste

### ⚠️ Wichtiger Hinweis

Diese Integration schließt eine einfache, aber wichtige Lücke in Home Assistant: wiederkehrende Aufgaben ohne mehrere Helfer und Automationen. Sie ist bewusst minimal gehalten und konzentriert sich ausschließlich auf die Aufgabenverfolgung.

Dashboards, Automationen und Benachrichtigungen bringt Home Assistant bereits mit – die Integration ergänzt diese Funktionen, statt sie zu ersetzen.

### 🛠️ Installation

[![Öffne dein Home Assistant und füge das Repository im Home Assistant Community Store hinzu.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Noack1978&repository=home_maintenance&category=integration)

1. Installation über **HACS**: Repository über den Button oben hinzufügen, nach „Home Maintenance“ suchen und auf **Herunterladen** klicken.
2. Home Assistant neu starten.
3. **Einstellungen → Geräte & Dienste → Integration hinzufügen** und „Home Maintenance“ auswählen.
4. Das Panel findest du anschließend in der Seitenleiste.

Optionen (Panel nur für Administratoren, Name in der Seitenleiste) lassen sich jederzeit über die Integration anpassen.

### 📖 Benutzung

1. Öffne **Home Maintenance** in der Seitenleiste.
2. Unter „Neue Aufgabe erstellen“ eintragen:
   - Titel (z. B. „Trocknerabluft reinigen“)
   - Intervall (Anzahl) und Einheit (Tage, Wochen, Monate)
   - Zuletzt durchgeführt (optional, Standard: heute)
   - NFC-Tag (optional, markiert die Aufgabe beim Scannen als erledigt)
   - Symbol (optional)
3. Klicke auf **Aufgabe hinzufügen**.
4. Fällige und überfällige Aufgaben werden im Panel angezeigt.
5. Mit **Abschließen** wird „Zuletzt durchgeführt“ auf heute gesetzt.

| Aufgabe                | Intervall | Zuletzt erledigt |
|------------------------|-----------|------------------|
| Heizungsfilter wechseln | 90 Tage   | 15.01.2025       |
| Rauchmelder testen      | 6 Monate  | 01.12.2024       |
| Dachrinne reinigen      | 8 Wochen  | 01.10.2024       |

### 🔁 Verfügbare Aktion

#### `home_maintenance.reset_last_performed`

Markiert eine Aufgabe als erledigt und aktualisiert `last_performed` und `next_due`. Optional kann ein Datum für `last_performed` angegeben werden.

```yaml
action: home_maintenance.reset_last_performed
data:
  entity_id: binary_sensor.dachrinne_reinigen
  performed_date: "2025-06-19"
```

### 💬 Hilfe

Eröffne ein [Issue auf GitHub](https://github.com/Noack1978/home_maintenance/issues).

### 📄 Lizenz & Herkunft

MIT-Lizenz – frei nutzbar, teilbar und erweiterbar. Dieses Projekt basiert auf [TJPoorman/home_maintenance](https://github.com/TJPoorman/home_maintenance) und wird eigenständig weiterentwickelt.

[⬆️ Nach oben / Back to top](#-home-maintenance-für-home-assistant--home-maintenance-for-home-assistant)

---

## English

Keep your home in top shape by tracking recurring maintenance tasks right inside Home Assistant!

This custom integration helps you remember chores like changing air filters, cleaning gutters, or testing smoke alarms – and shows you when they are due.

### ✨ Features

- 📋 Create recurring tasks (e.g. “Change HVAC filter every 90 days”)
- 🔔 An entity is created for every task – use it for automations and dashboards
- ✅ Mark tasks as completed; the next due date is calculated automatically
- 🏷️ Optional: mark a task as completed by scanning an NFC tag
- 📊 Clean, easy-to-use panel in the Home Assistant sidebar

### ⚠️ Important Note

This integration fills a simple but important gap in Home Assistant: recurring tasks without relying on multiple helpers and automations. It is intentionally minimal and focused solely on task tracking.

Home Assistant already provides powerful dashboards, automations and alerts – this integration complements them instead of replacing them.

### 🛠️ Installation

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Noack1978&repository=home_maintenance&category=integration)

1. Install via **HACS**: add the repository with the button above, search for “Home Maintenance” and click **Download**.
2. Restart Home Assistant.
3. Go to **Settings → Devices & services → Add integration** and choose “Home Maintenance”.
4. You will then find the panel in the sidebar.

Options (admin-only panel, sidebar title) can be changed at any time via the integration.

### 📖 How to Use

1. Open **Home Maintenance** from the sidebar.
2. Add a new task by entering:
   - A title (e.g. “Clean dryer vent”)
   - The interval (number) and unit (days, weeks, months)
   - Last performed (optional, defaults to today)
   - An NFC tag (optional, marks the task complete when scanned)
   - An icon (optional)
3. Click **Add Task**.
4. Due and overdue tasks are highlighted in the panel.
5. Click **Complete** to reset “Last performed” to today.

| Task               | Interval | Last done    |
|--------------------|----------|--------------|
| Change HVAC filter | 90 days  | Jan 15, 2025 |
| Test smoke alarms  | 6 months | Dec 1, 2024  |
| Clean gutters      | 8 weeks  | Oct 1, 2024  |

### 🔁 Available Action

#### `home_maintenance.reset_last_performed`

Marks a task as completed and updates `last_performed` and `next_due`. Optionally specify a date for `last_performed`.

```yaml
action: home_maintenance.reset_last_performed
data:
  entity_id: binary_sensor.clean_gutters
  performed_date: "2025-06-19"
```

### 💬 Need Help?

Open an [issue on GitHub](https://github.com/Noack1978/home_maintenance/issues).

### 📄 License & Origin

MIT License – free to use, share, and improve. This project is based on [TJPoorman/home_maintenance](https://github.com/TJPoorman/home_maintenance) and is developed independently.

[⬆️ Back to top / Nach oben](#-home-maintenance-für-home-assistant--home-maintenance-for-home-assistant)
