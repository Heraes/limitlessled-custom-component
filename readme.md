# LimitlessLED Custom Component for Home Assistant

[![License](https://img.shields.io/github/license/markovrv/limitlessled-custom-component)](LICENSE)
![Version](https://img.shields.io/badge/version-1.0.0-blue)

Custom implementation of LimitlessLED integration for Home Assistant with enhanced features.

## Features

- Custom unique ID assignment via YAML configuration
- Backward compatible with standard LimitlessLED configuration
- Improved entity management
- All standard LimitlessLED features preserved

## Installation

1. Create `custom_components` folder in your Home Assistant config directory (if it doesn't exist)
2. Create `limitlessled` folder inside `custom_components`
3. Copy all files from this repository into the `limitlessled` folder
4. Restart Home Assistant

## Configuration

```yaml
# Example configuration.yaml entry
light:
  - platform: limitlessled
    bridges:
      - host: 192.168.1.100
        groups:
          - name: Living Room Lights
            number: 1
            type: rgbw
            unique_id: living_room_main  # Custom unique ID
          - name: Bedroom Lights
            number: 2
            type: rgbww
            # unique_id will be auto-generated if not specified
```

## Unique ID Configuration

You can specify custom unique IDs for each light group in YAML:

```yaml
groups:
  - name: "My Lights"
    number: 1
    unique_id: my_custom_light_id  # Add this line
```

If not specified, unique ID will be generated in format: `limitlessled_{group_name}_{group_number}`

## Migration from Standard Integration

1. Backup your current configuration
2. Remove the standard LimitlessLED integration
3. Install this custom component
4. Update your configuration if needed
5. Restart Home Assistant

## Support

For issues and feature requests, please [open an issue](https://github.com/markovrv/limitlessled-custom-component/issues).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
