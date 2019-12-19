---
title: "Kumo"
description: "Instructions on how to integrate Kumo into Home Assistant."
logo: kumo.png
ha_category:
  - Hub
  - Climate
  - Fan
  - Sensor

ha_iot_class: Local Polling
ha_release: 0.TBD
---

The `kumo` integration is the main integration to integrate [Kumo-Cloud](https://www.mitsubishicomfort.com/kumocloud) related devices.

There is currently support for the following device types within Home Assistant:

- Climate
- Fan
- Sensor


## Configuration

To enable this component, add the following lines to your `configuration.yaml`:

```yaml
# Example configuration.yaml entry
kumo:
  username: YOUR_KUMO_USERNAME
  password: YOUR_KUMO_PASSWORD
```

{% configuration %}
username:
  description: kumo account username (email address).
  required: true
  type: string
password:
  description: kumo account password.
  required: true
  type: string
prefer_cache:
  description: "prefer the locally-cached file (if present), which will speed up startup a bit, and avoid HomeAssistant talking to KumoCloud at all after the initial setup. This comes at the cost of not picking up configuration changes to your account. Note that this config information includes the indoor units’ names and IP addresses, so if you use this option and those change (even including the indoor units getting a different DHCP lease), you’ll want to delete the cached file. Set to True of False"
  required: false
  type: string
{% endconfiguration %}







## Climate

The `kumo` climate platform allows you to control your Mitsubishi Mini Split. F

### Component services

This integration supports the following services (see [Climate](/integrations/climate/)):

- [`turn_on`](/integrations/climate/#service-climateturn_on)
- [`turn_off`](/integrations/climate/#service-climateturn_off)
- [`set_temperature`](/integrations/climate/#service-climateset_temperature)
- [`set_fan_mode`](/integrations/climate/#service-climateset_fan_mode)
- [`set_hvac_mode`](/integrations/climate/#service-climateset_hvac_mode)



### Attributes

There are several attributes which can be used for automations and templates.

| Attribute | Description |
| --------- | ----------- |
| `hvac_modes` | These are the modes that the device currently supports.|
| `current_temperature` | The current temparture recorded by the device.|
| `min_temp` | The minimum temp to be displayed on the thermostat card.|
| `max_temp` | The maximum temp to be displayed on the thermostat card.|
| `temperature` | ???.|
| `target_temp_high` | The highest temp to maintain when in auto mode|
| `targe_temp_low` |  The lowest temp to maintain in auto mode.|
| `fan_mode` | The current fan mode set on the device.|
| `fan_modes` | The fan modes that the device supports.|
| `hvac_action` | The current hvac mode.|
| `swing_mode` | The current swing mode set on the device.|
| `swing_modes` | List of available swing modes supported by the device.|
| `friendly_name` | friendly name of the device set in kumo cloud.|
| `supported_features` | ??????.|



