# HA Flower Blueprint

A Home Assistant Blueprint to regularly check all plants for low moisture or conductivity.

> **Based on the original work by [H0W2D017](https://github.com/H0W2D017)**  
> Original repository: [H0W2D017/HA_Flower_Blueprint](https://github.com/H0W2D017/HA_Flower_Blueprint)

---

## Changes in this fork

The following issues from the original blueprint have been fixed:

- **Notifications only trigger on problems** – Mobile app and Alexa notifications are now silent when all plants are healthy. Previously, Alexa would announce "Achtung" and the mobile app would send a notification every evening even when no plants needed attention.
- **Exclude filter now works correctly** – The excluded sensors are now properly filtered in all four sensor variables (`sensors`, `water`, `nutritions`, `both`). Previously the exclude input was defined but never applied.
- **Actions only run on plant problems** – Actions 1, 2 and 3 now only execute when actual plant problems are detected after the exclusion filter is applied. Previously they would run regardless of plant status.

---

## Requirements

- [Plant Monitor integration](https://www.home-assistant.io/integrations/plant/) for Home Assistant
- [Alexa Media Player](https://github.com/alandtse/alexa_media_player) (HACS) – optional, only required for Alexa announcements
  - Install via **HACS → Integrations → Search for "Alexa Media Player" → Download**
  - Then add the integration under **Settings → Devices & Services → Add Integration → Alexa Media Player**
  - If you don't use Alexa, simply leave the Alexa option disabled in the Blueprint
- Met.no weather integration – optional, for night temperature warnings

---

## Installation

[![Open your Home Assistant instance and show the blueprint import dialog.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/Gubelat/Home-Assistant-Flower-Blueprint/blob/main/flowers_blueprint.yaml)

Or manually import via **Settings → Automations → Blueprints → Import Blueprint** and use this URL:

```
https://github.com/Gubelat/Home-Assistant-Flower-Blueprint/blob/main/flowers_blueprint.yaml
```

---

## Features

- Check all plants at a configurable time and day
- Separate notifications for low moisture, low nutrition, or both
- Optional night temperature warning based on hourly weather forecast
- High and low temperature alarms
- Alexa announcement support
- Persistent and actionable mobile notifications
- Exclude specific plants from monitoring
- Up to three configurable custom actions

---

## Credits

Original blueprint created by [H0W2D017](https://github.com/H0W2D017).  
Fixes and improvements by [Gubelat](https://github.com/Gubelat).
