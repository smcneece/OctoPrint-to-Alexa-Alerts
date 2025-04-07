# 💥 **The Ultimate OctoPrint Job Notification Automation** 💥  
**Blasting through your smart home like a sonic boom!**

Fed up with sitting around watching your 3D printer? Wish your home assistant would give you the lowdown without you having to babysit? Now your OctoPrint jobs won’t just update you – **they’ll shake your world with Alexa-powered notifications**!  
And for those quieter moments (or when Alexa’s feeling lazy), **persistent notifications** will make sure you're always in the loop. Never miss a print!

---

## 🤘 **Killer Features That’ll Rock Your Print Bed** 🎸

* 📢 **Alexa’s Got the Mic!** Instantly blast job statuses through Alexa – Start, Pause, Resume, Complete, or even Fail, Alexa's there for the newsflash!
* 🤫 **Quiet Time? No Problem!** Define your own hours for when Alexa gets to speak. No more midnight interruptions! 🕛
* 🔔 **Persistent Power-Ups!** Flip the switch and get trusty persistent notifications in the Home Assistant UI. Even when Alexa is silent, you'll stay updated.
* ✨ **Configuration Made Easy-Peasy!** No need to dig through lines of code – all the critical settings are right at the top.
* 🎉 **Printer Posse Ready!** Got multiple printers? Easy! Customize names for each, and get individual updates for each machine.
* 🚀 **Noob-Proof Zone!** You’ve got a clear warning label to protect from accidental edits. This automation’s for everyone – beginners to experts!

---

## 🛠️ **Gear You’ll Need** 🔧

Before you hit the ground running, make sure you’ve got these tools set up:

### ✅ **HACS – Power Up Your Home Assistant!**  
The easiest way to grab killer community add-ons. Get it [here](https://hacs.xyz/).

### ✅ **Alexa Media Player – Talk to Your Echo Devices!**  
This lets Home Assistant send messages to your Echo. Get it [here](https://github.com/custom-components/alexa_media_player).

### ✅ **OctoPrint Integration – Get Printer Data Into Home Assistant!**  
This integration syncs your 3D printer’s status directly with Home Assistant. [Setup guide](https://www.home-assistant.io/integrations/octoprint/).

---

## 🚀 **Engage! Setting Up the Automation** 🎯

Time to unleash the notification magic! Here's how to get it going:

### 1. **Open the Automation Editor!**  
Go to **Home Assistant > Settings > Automations & Scenes > Automations**, hit **"+ Create Automation"**, and pick **"Start with an empty automation"**. Then, jump to the **YAML tab** in the top-right and paste in the code below!

### 2. **Customize Your Setup!**  
Tweak the "Variables to Edit" section, which is like your control panel for ultimate printer status updates:

```yaml
variables:
  # === Alexa Devices Ready to Announce! ===
  alexa_notify_services:
    - notify.alexa_media_living_room_echo   # Example: Living room’s Echo
    - notify.alexa_media_kitchen_dot        # Example: Kitchen Alexa
    - notify.alexa_media_bedroom_echo      # Example: Bedroom's Echo
    # Add/remove your Alexa notify service names here! (Find them in Developer Tools -> States)

  # === Persistent Notifications - Always On! ===
  enable_persistent_notifications: true   # Set to 'false' if you don’t want persistent notifications.

  # === Alexa's Notification Time Window ===
  alexa_start_hour: 8    # Set when Alexa notifications can start (8 AM).
  alexa_start_minute: 0
  alexa_end_hour: 23     # Set when Alexa notifications can end (11 PM).
  alexa_end_minute: 59

  # === Printer's Friendly Names ===
  printer_names:
    sensor.ender_3_pro_state: "The Mighty Ender!"   # Example: Ender 3 Pro’s name
    sensor.prusa_mini_state: "Speedy Prusa Mini"   # Example: Prusa Mini’s name
    # Map your printer’s state sensor entity IDs to friendly names here!
```

🛸 How It Works 💥

Once you’ve got it installed and configured, the automation’s all set! When your OctoPrint printer starts, pauses, resumes, finishes, or fails, you'll get an Alexa-powered announcement (during your set hours) and persistent notifications in Home Assistant (if enabled). Simple as that.
🚑 Troubleshooting 🔧

Here’s some stuff to check if things aren’t working right:

    Silent Alexa? Double-check your notify.alexa_media_... service names. Make sure your Alexa is on, and within the announcement window. Peek at the Home Assistant logs to see if something’s wrong.

    No Persistent Notifications? Check that enable_persistent_notifications is true. If it's still not working, look at your logs for more info.

    Missing Printer Names? Go back to the printer_names section and make sure your printer’s state entity is properly linked to a nickname.

    Automation Not Running? Make sure the automation is saved and enabled. Logs are your best friend for finding errors.

🤝 Contribute & Get Involved!

Got an awesome idea to improve this? Found a bug? Let’s make it even better. Fork it and send in pull requests – the more, the merrier!
📜 License – The Freedom to Rock!

This project is licensed under the MIT License. See the LICENSE file for more details.
🎤 Big Shoutouts to the MVPs 🏆

The Home Assistant community – you all rule!
The OctoPrint and Alexa Media Player integration wizards – your magic is undeniable!

