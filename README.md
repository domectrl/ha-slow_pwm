# Slow PWM integration

[![GitHub Release][releases-shield]][releases]
[![GitHub Activity][commits-shield]][commits]
[![License][license-shield]](LICENSE)

[![hacs][hacsbadge]][hacs]
![Project Maintenance][maintenance-shield]

[![Discord][discord-shield]][discord]
[![Community Forum][forum-shield]][forum]

**This integration will set up the following platforms.**

Platform | Description
-- | --
`number` | The SlowPWM integration can be used to control one or multiple digital switches in an analog control algorithm. The switches will be controlled by pulse width modulation (PWM, see https://en.wikipedia.org/wiki/Pulse-width_modulation). This enables the usage of digital switches in modulated modes. This is typically useful in slow systems like floor heater or boiler heater controller systems. The [PID controller][pid_controller] and the [PID thermostat][pid_thermostat] can use this number as regulated output.

## Installation

### HACS (Preferred)
1. [Add](http://homeassistant.local:8123/hacs/integrations) the custom integration repository: https://github.com/antonverburg/ha_slow_pwm
2. Select `Slow PWM` in the Integration tab and click `download`
3. Restart Home Assistant
4. Done!

### Manual
1. Using the tool of choice open the directory (folder) for your HA configuration (where you find `configuration.yaml`).
1. If you do not have a `custom_components` directory (folder) there, you need to create it.
1. In the `custom_components` directory (folder) create a new folder called `slow_pwm`.
1. Download _all_ the files from the `custom_components/slow_pwm/` directory (folder) in this repository.
1. Place the files you downloaded in the new directory (folder) you created.
1. Restart Home Assistant

## Configuration via user interface:
* In the user interface go to "Configuration" -> "Integrations" click "+" and search for "Slow PWM"
* For a description of the configuration parameters, see [Configuration parameters]

## YAML Configuration

Alternatlively, this integration can be configured and set up manually via YAML
instead. To enable the Integration sensor in your installation, add the
following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
number:
  - platform: slow_pwm
    name: Floorheater living room
    outputs:
      - "switch.living_room_group1"
``` 

### Configuration parameters:
- name: Name of the slow_pwm. 
  > required: true | type: string  
- outputs: `entity_id`'s for switches, must be toggle devices. When multiple outputs are selected, the range of 0..100% will be shared over the multiple switches. For example, with 2 switches at 50% output only the first switch will be on full time, at 75% the first switch will be on 100% of the time, and the second 50%.
  > required: true | type: multiple strings
- minimum: Minimal value of the slow_pwm number. Timed output will be normalized between minimum and maximum.
  > required: false | default: 0 | type: float
- maximum: Maximal value of the slow_pwm number. Timed output will be normalized between minimum and maximum.
  > required: false| default: 100 | type: float
- cycle_time: Cycle time for the PWM cycle.
  > required: false | default: "{'minutes': 30}" | type: time_period
- step: Step value. Smallest value `0.001`.
  > required: false | type: float | default: 1
- mode: Control how the number should be displayed in the UI. Can be set to `box` or `slider` to force a display mode.
  > required: false | type: string | default: '"auto"'
- unique_id: Unique id to be able to configure the entity in the UI.
  > required: false | type: string

### Full configuration example

```yaml
number:
  - platform: slow_pwm
    name: Floorheater living room
    outputs:
      - "switch.living_room_group1"
      - "switch.living_room_group2"
    minimum: 10
    maximum: 200
    cycle_time:  {'hours':0, 'minutes':20, 'seconds': 00}
    minimal_switch_time: {'hours':0, 'minutes':0, 'seconds': 30}
    step: 3
    mode: "auto"
    unique_id: "MyUniqueID_1234"
```

## Contributions are welcome!

If you want to contribute to this please read the [Contribution guidelines](CONTRIBUTING.md)

***

[commits-shield]: https://img.shields.io/github/commit-activity/y/antonverburg/ha_slow_pwm.svg?style=for-the-badge
[commits]: https://github.com/antonverburg/ha_slow_pwm/commits/main
[hacs]: https://hacs.xyz/
[hacsbadge]: https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge
[discord]: https://discord.gg/Qa5fW2R
[discord-shield]: https://img.shields.io/discord/330944238910963714.svg?style=for-the-badge
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[forum]: https://community.home-assistant.io/
[license-shield]: https://img.shields.io/github/license/antonverburg/ha_slow_pwm.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-antonverburg-blue.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/antonverburg/ha_slow_pwm.svg?style=for-the-badge
[releases]: https://github.com/antonverburg/ha_slow_pwm/releases
[pid_controller]: https://github.com/antonverburg/ha_pid_controller
[pid_thermostat]: https://github.com/antonverburg/ha_pid_thermostat

