# Product Definition: Grizzl-E_REST

## Initial Concept
Home Assistant REST Integration for Grizzl-E Ultimate 48A charger. Since they have put the OCPP integration behind a paywall, this is a workaround for local monitoring and control.

## Target Users
- Home Assistant users who own a Grizzl-E Ultimate charger and want local control.
- Users who want to avoid the Grizzl-E OCPP paywall.
- Home automation enthusiasts looking for YAML-based REST integration examples.

## Goals & Features
- **Local Monitoring:** Provide real-time monitoring of charging status and metrics directly within Home Assistant.
- **Local Control:** Enable control over charger settings, such as adjusting the charging current, without relying on external cloud services.
- **OCPP Alternative:** Serve as a robust local alternative to the manufacturer's subscription-based OCPP integration.

## Desired Outcomes
- **Functional Dashboard:** Users can create a comprehensive Home Assistant dashboard to visualize their charger's state.
- **Seamless Automation:** Charging can be automated based on home energy demand or specific user-defined input helpers.
- **Subscription Independence:** Users achieve complete independence from manufacturer-imposed paywalls for core charger functionality.

## Technical Requirements
- **Home Assistant Integrations:** Requires the use of standard Home Assistant REST and Template integrations.
- **Interactive Control:** Utilizes Template entities (Switch, Select) to provide a seamless UI experience and direct control over charger settings.

## Documentation Strategy
- **Setup Guide:** Maintain a detailed README with clear, step-by-step instructions for installation and configuration.
- **Example Assets:** Provide ready-to-use example automations and dashboard card configurations to accelerate user adoption.
