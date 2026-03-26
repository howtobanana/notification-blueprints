# Notification Blueprints

Home Assistant Blueprints für Benachrichtigungen.

## Tür-Offen Benachrichtigung

All-in-One Blueprint für Tür-Überwachung mit drei Szenarien:

### Szenarien

| Szenario | Auslöser | Empfänger | Alarm-Typ |
|----------|----------|-----------|-----------|
| **Vergessen zu schließen** | Person verlässt Home-Zone, Tür offen nach X Sek. | Nur die Person die gegangen ist | Kritisch |
| **Fallback-Alarm** | Tür durchgehend offen nach X Min. | Alle Personen | Normal oder Kritisch (konfigurierbar) |
| **Einbruch-Erkennung** | Niemand zuhause, Tür öffnet sich | Alle Personen | Kritisch |

### Features

- 1–4 Personen konfigurierbar
- Kritische iOS/Android Push-Alarme (durchbrechen Lautlos-Modus)
- Alle Zeitintervalle per Slider einstellbar
- Self-Healing: Fehler in einem Szenario stoppen nicht die anderen
- Auto-Stop: Benachrichtigungen enden automatisch wenn die Tür geschlossen wird
- Debug-Modus für Diagnose-Informationen

### Installation

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FUSERNAME%2Fnotification-blueprints%2Fblob%2Fmain%2Fdoor_open_notification.yaml)

Oder manuell: Den Inhalt von `door_open_notification.yaml` in Home Assistant unter **Einstellungen → Automationen & Szenen → Blueprints → Blueprint importieren** einfügen.

### Voraussetzungen

- Home Assistant 2024.6.0 oder neuer
- Mindestens ein `binary_sensor` mit Device-Class `door`
- Home Assistant Companion App auf iOS oder Android
- `person`-Entitäten mit konfiguriertem Zone-Tracking

### Konfiguration

1. **Basis-Einstellungen**: Tür-Sensor auswählen und Zeitintervalle anpassen
2. **Personen**: Person-Entitäten und zugehörige `mobile_app` Notify-Services eintragen
3. **Debug**: Optional aktivieren für Diagnose-Nachrichten
