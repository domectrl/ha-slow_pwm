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

You can install this integration manually or via [HACS][hacs].

For manual installation:

1. Using the tool of choice open the directory (folder) for your HA configuration (where you find `configuration.yaml`).
1. If you do not have a `custom_components` directory (folder) there, you need to create it.
1. In the `custom_components` directory (folder) create a new folder called `slow_pwm`.
1. Download _all_ the files from the `custom_components/slow_pwm/` directory (folder) in this repository.
1. Place the files you downloaded in the new directory (folder) you created.
1. Restart Home Assistant

After installation, configuration is done in the UI:
* In the HA UI go to "Configuration" -> "Integrations" click "+" and search for "Slow PWM"

<!---->

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

