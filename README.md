# 🔊 OctoPrint Job Status Notifications via Alexa - v11

This Home Assistant automation blasts your Alexa devices with real-time announcements when your OctoPrint printers start, pause, resume, or complete a print job. Missed the alert while rockin’ out or takin’ a dump? Don’t worry—we’ve got optional persistent notifications too.

## 🎸 Features

- 🔈 Announces job status through **multiple Alexa devices**
- 🕘 Alexa notifications only fire during **quiet hours you define**
- 🧱 Persistent notifications are always on (if enabled)
- 🧾 Clean structure with all editable parts at the top
- 🖨️ Supports multiple OctoPrint printers with friendly names
- 🛠️ Built-in safety banner so newbies don’t bork it

## ⚙️ Requirements

Make sure these are installed before using this automation:

### ✅ [HACS – Home Assistant Community Store](https://hacs.xyz/)
Used to install community integrations like Alexa Media Player.

### ✅ [Alexa Media Player](https://github.com/custom-components/alexa_media_player)
Lets Home Assistant send announcements to your Alexa devices.

### ✅ [OctoPrint Integration](https://www.home-assistant.io/integrations/octoprint/)
Exposes your printer’s state (`sensor.yourprinter_current_state`).

## 🚀 Setup

### 1. Add the Automation
Open **Home Assistant > Settings > Automations & Scenes > Automations**  
Click **“+ Create Automation”**, choose **“Start with an empty automation”**, switch to **YAML mode**, and paste the whole thing in.

### 2. Customize the Top Section
All the editable stuff is grouped at the top for your convenience:

```yaml
alexa_notify_services:
  - notify.alexa_media_basemenmancave
  - notify.alexa_media_echoclockdot
  - notify.alexa_media_basement_bathroom_echo_flex  # Add/remove devices as needed

enable_persistent_notifications: true  # Set false to disable persistent notifications

alexa_start_hour: 9     # Alexa alerts allowed from 9:00 AM...
alexa_start_minute: 0
alexa_end_hour: 22      # ...to 10:00 PM
alexa_end_minute: 0

printer_names:
  sensor.chiron_right_current_state: Chiron Right
  sensor.chiron_left_current_state: Chiron Left  # Replace with your printer sensors
