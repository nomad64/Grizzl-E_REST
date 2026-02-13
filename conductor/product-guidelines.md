# Product Guidelines: Grizzl-E_REST

## Communication Tone
- **Technical and Direct:** Documentation and communication should prioritize clarity, brevity, and technical accuracy. Given the nature of YAML-based integrations, information should be presented straightforwardly to minimize ambiguity.

## Design & Organization
- **Entity Naming Convention:** All Home Assistant entities created by this integration must use the `grizzl_e_` domain-prefix (e.g., `sensor.grizzl_e_current_voltage`, `rest_command.grizzl_e_set_current`). This ensures entities are easily identifiable and organized within a user's Home Assistant instance.
- **Modular Configuration:** Maintain a modular structure for YAML files. Configuration should be organized into logical, separate files (like `rest.yaml`, `rest_command.yaml`, and `template.yaml`) to improve maintainability and readability.

## Security & Privacy
- **Secrets Management:** Users must be instructed to use Home Assistant `!secret` tags for all sensitive or user-specific information, such as IP addresses or unique identifiers. Example configurations should clearly demonstrate this practice.

## Documentation Standards
- **Markdown-centric Style:** All documentation, particularly the README, must adhere to clean, standard Markdown. Use hierarchical headings, fenced code blocks for snippets, and consistent formatting to ensure high readability and professional presentation on platforms like GitHub.
