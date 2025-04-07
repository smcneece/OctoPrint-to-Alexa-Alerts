# 🔊 OctoPrint Job Status Notifications via Alexa (v10)

This Home Assistant automation sends real-time announcements to multiple Alexa devices when your OctoPrint 3D printer starts, pauses, resumes, or completes a print job. It also supports persistent notifications as a backup, so you’ll never miss a print update—even when you're blasting tunes or in the bathroom.

## 🎸 Features

- ✅ Announces print job events via **multiple Alexa devices**
- ✅ Optional persistent notifications via Home Assistant
- ✅ Only announces via Alexa during your defined "awake" hours
- ✅ Friendly printer names for each sensor
- ✅ Fully modular—easy to expand for more printers or Alexa devices
- ✅ Cleanly structured with safe-edit zones for beginners

## ⚙️ Requirements

Before you rock this automation, make sure your Home Assistant setup has the following:

### 1. [HACS – Home Assistant Community Store](https://hacs.xyz/)
Used for installing custom integrations like Alexa Media Player.

### 2. [Alexa Media Player](https://github.com/custom-components/alexa_media_player)
Lets Home Assistant communicate with your Alexa devices for announcements.

### 3. [OctoPrint Integration](https://www.home-assistant.io/integrations/octoprint/)
Connects your 3D printer(s) to Home Assistant and exposes state sensors.

## 🚀 Setup

### 1. **Add the Automation YAML**
Copy the full YAML into Home Assistant as a new automation. You can paste it directly into the Automation Editor (YAML mode) or save it as a new file if you're using file-based automations.

### 2. **Customize These Variables (at the top of the YAML):**
```yaml
alexa_notify_services:
  - notify.alexa_media_basemenmancave
  - notify.alexa_media_echoclockdot
  - notify.alexa_media_basement_bathroom_echo_flex  # Add/remove devices as needed

enable_persistent_notifications: true  # Set to false to disable persistent messages

alexa_start_hour: 9
alexa_start_minute: 0
alexa_end_hour: 12
alexa_end_minute: 0

printer_names:
  sensor.chiron_right_current_state: Chiron Right
  sensor.chiron_left_current_state: Chiron Left  # Use your actual sensor IDs
