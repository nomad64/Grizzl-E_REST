# Technology Stack: Grizzl-E_REST

## Core Platform
- **Home Assistant:** The primary platform for this integration, utilizing its native YAML configuration capabilities for defining sensors, commands, and templates.

## Communication & Protocols
- **REST (HTTP/JSON):** The charger is monitored and controlled via RESTful API calls. Data is exchanged in JSON format over HTTP.

## Configuration Structure
- **REST Integration (`rest.yaml`):** Used for polling the charger's API to retrieve state information and metrics.
- **REST Command Integration (`rest_command.yaml`):** Used for sending specific commands to the charger, such as setting the charging current.
- **Template Integration (`template.yaml`):** Used for processing and transforming raw API data into user-friendly Home Assistant sensors and binary sensors.

## Target Hardware
- **Grizzl-E Ultimate 48A:** Specifically designed to interface with the local API of the Grizzl-E Ultimate series chargers.
