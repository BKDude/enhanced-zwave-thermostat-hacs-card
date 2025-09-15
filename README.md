# Enhanced Z-Wave Thermostat

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)
[![GitHub Release][releases-shield]][releases]
[![License][license-shield]](LICENSE)

A comprehensive Home Assistant custom integration that provides enhanced Z-Wave thermostat functionality with Nest-like features.

## Features

✅ **Advanced Safety Controls**
- Safety temperature limits with override protection
- Temperature range validation (configurable 40°F - 90°F)
- Automatic temperature clamping

✅ **Smart Scheduling**
- Complete scheduling system with persistence
- Weekly temperature schedules
- Automatic schedule evaluation and application
- Schedule enable/disable functionality

✅ **Home/Away Intelligence**
- Automatic home/away mode detection
- Preset temperature configurations
- Energy-saving away temperatures

✅ **Multi-Thermostat Support**
- Automatic Z-Wave thermostat discovery
- Support for multiple zones
- Individual configuration per thermostat

✅ **Enhanced Services**
- `set_schedule` - Create and manage temperature schedules
- `set_home_away` - Control home/away modes
- `override_safety` - Temporary safety limit overrides

✅ **Seamless Integration**
- Native Home Assistant configuration flow
- Real-time state synchronization with Z-Wave devices
- Professional device management and entity structure

## Installation

### Via HACS (Recommended)

1. Open HACS in your Home Assistant instance
2. Go to "Integrations" 
3. Click the three dots in the top right corner
4. Select "Custom repositories"
5. Add this repository URL and select "Integration" as the category
6. Click "Install"
7. Restart Home Assistant

### Manual Installation

1. Download the latest release
2. Extract the `enhanced_zwave_thermostat` folder to your `custom_components` directory
3. Restart Home Assistant
4. Go to Configuration > Integrations
5. Click "Add Integration" and search for "Enhanced Z-Wave Thermostat"

## Requirements

- Home Assistant 2024.3.0 or newer
- Z-Wave JS integration installed and configured
- At least one Z-Wave thermostat device

## Configuration

1. Ensure your Z-Wave thermostats are working with the Z-Wave JS integration
2. Add the Enhanced Z-Wave Thermostat integration via the UI
3. Configure your safety temperature limits and default temperatures
4. The integration will automatically discover and enhance your existing Z-Wave thermostats

## Usage

### Basic Temperature Control
The enhanced thermostats work exactly like standard Home Assistant climate entities but with added safety features and intelligence.

### Scheduling
Create temperature schedules using the `enhanced_zwave_thermostat.set_schedule` service:

```yaml
service: enhanced_zwave_thermostat.set_schedule
data:
  entity_id: climate.enhanced_living_room_thermostat
  schedule:
    weekdays: ["monday", "tuesday", "wednesday", "thursday", "friday"]
    time: "07:00"
    temperature: 72
    name: "Weekday Morning"
```

### Home/Away Modes
Control home/away modes with the `enhanced_zwave_thermostat.set_home_away` service:

```yaml
service: enhanced_zwave_thermostat.set_home_away
data:
  entity_id: climate.enhanced_living_room_thermostat
  home_away_mode: "away"
```

## Troubleshooting

### No Thermostats Discovered
- Ensure Z-Wave JS integration is working properly
- Check that your thermostats appear as climate entities in Home Assistant
- Restart the Enhanced Z-Wave Thermostat integration

### Schedules Not Working
- Verify the thermostat is in "schedule" preset mode
- Check that the schedule service was called successfully
- Review Home Assistant logs for any error messages

## Support

- [Issues](https://github.com/homeassistant-community/enhanced-zwave-thermostat/issues)
- [Discussions](https://github.com/homeassistant-community/enhanced-zwave-thermostat/discussions)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

[releases-shield]: https://img.shields.io/github/release/homeassistant-community/enhanced-zwave-thermostat.svg
[releases]: https://github.com/homeassistant-community/enhanced-zwave-thermostat/releases
[license-shield]: https://img.shields.io/github/license/homeassistant-community/enhanced-zwave-thermostat.svg