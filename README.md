# Grizzl-E Ultimate Home Assistant REST Integration

This project provides a comprehensive local integration for the Grizzl-E Ultimate 48A EV charger with Home Assistant. It bypasses the manufacturer's subscription-based OCPP paywall by utilizing the charger's local REST API for monitoring and control.

## Features

- **Local Monitoring:** Real-time sensors for charging status, current, voltage, energy, temperature, and more.
- **Local Control:** Toggle charging (EVSE) and OCPP integration, and set the maximum charging current.
- **Privacy Focused:** All communication is local to your network.
- **Standardized Naming:** All entities follow the `grizzl_e_` naming convention for easy organization.

## Architecture

The integration is split into three modular YAML files:

1.  **`rest.yaml`**: Handles polling the charger's API for status updates and metrics.
2.  **`rest_command.yaml`**: Defines the actions used to send commands to the charger.
3.  **`template.yaml`**: Creates user-friendly switches and processes raw data from the REST sensors.

## Setup Instructions

### 1. Prerequisites

- A Grizzl-E Ultimate series charger connected to your local network.
- Knowledge of your charger's IP address.

### 2. Configure Secrets

Add your charger's IP address to your Home Assistant `secrets.yaml` file:

```yaml
grizzl_e_ip: 192.168.1.XXX # Replace with your charger's IP
```

### 3. Include Configuration Files

Copy `rest.yaml`, `rest_command.yaml`, and `template.yaml` to your Home Assistant configuration directory. Then, reference them in your `configuration.yaml`:

```yaml
rest: !include rest.yaml
rest_command: !include rest_command.yaml
template: !include template.yaml
```

*Note: If you already have these sections in your `configuration.yaml`, you may need to merge the contents instead of using `!include`.*

### 4. Restart Home Assistant

Restart Home Assistant or reload the REST, REST Command, and Template configurations to apply the changes.

## Control & Automation

### Setting Charging Current

To set the charging current from the UI, it is recommended to create an `input_number` helper and an automation:

1.  Create an `input_number.grizzl_e_charge_current` with a range (e.g., 6 to 48).
2.  Create an automation that calls the `rest_command.grizzl_e_set_charge_rate` action whenever the `input_number` changes:

```yaml
automation:
  - alias: "Grizzl-E Set Charge Current"
    trigger:
      - platform: state
        entity_id: input_number.grizzl_e_charge_current
    action:
      - action: rest_command.grizzl_e_set_charge_rate
        data:
          current: "{{ states('input_number.grizzl_e_charge_current') | int }}"
```

## Documentation

- [Product Definition](./conductor/product.md)
- [Technology Stack](./conductor/tech-stack.md)
- [Project Guidelines](./conductor/product-guidelines.md)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
