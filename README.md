# Home Assistant Blueprints

A collection of Home Assistant blueprints for automations and scripts.

## Requirements

- [Home Assistant](https://www.home-assistant.io/) (recent stable release recommended)
- The [Home Assistant Companion App](https://companion.home-assistant.io/) installed on any devices you want to notify

---

## Blueprints

### Advanced Actionable Notification

Send a notification to one or more devices with optional action buttons, configurable timeout, and automatic clearing. Supports iOS notification levels (Critical, Time Sensitive, Default, Quiet), custom sounds, click URLs, and notification tags. Each action button can trigger its own automation sequence, and a separate action can run on timeout.

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?url=https://github.com/JohnBehnke/home-assistant-blueprints/raw/main/advanced_actionable_notification.yaml)

#### Options

| Input | Description | Default |
|---|---|---|
| Devices to Notify | One or more devices running the HA Companion App | — |
| Title | Notification title | *(empty)* |
| Message | Notification body | — |
| Enable Confirmation Button | Show a confirmation action button | Enabled |
| Confirmation Text | Label for the confirmation button | `Confirm` |
| Confirmation Action | Actions to run when confirmed | — |
| Enable Dismiss Button | Show a dismiss action button | Enabled |
| Dismiss Text | Label for the dismiss button | `Dismiss` |
| Dismiss Action | Actions to run when dismissed | — |
| Timeout (Minutes) | Minutes to wait before timing out. Set to `0` to wait indefinitely | `30` |
| Timeout Action | Actions to run on timeout | — |
| Clear Notification After Response | Clear the notification from all devices after a button is pressed or on timeout. Requires a Notification Tag | Enabled |
| Click URL | URL to open when the notification body is tapped | *(empty)* |
| Interruption Level *(iOS only)* | `Default`, `Critical`, `Time Sensitive`, or `Quiet` | `Default` |
| Notification Sound *(iOS only)* | Custom sound filename including extension | *(empty)* |
| Notification Tag | Tag to prevent duplicate notifications. Required for clear-after-response | *(empty)* |

#### Notes

- **Critical** and **Time Sensitive** interruption levels must be enabled in the Home Assistant app settings on each device.
- **Time Sensitive** notifications must also be permitted in your iOS Focus settings.
- The **Clear Notification After Response** feature requires a **Notification Tag** to be set.

---

## Contributing

Contributions are welcome. If you have a blueprint you'd like to add:

1. Fork the repository
2. Add your blueprint YAML file to the root of the repo
3. Update `README.md` with a description, import button, and options table for your blueprint
4. Open a pull request with a brief description of what the blueprint does

Please keep blueprints self-contained in a single YAML file and test them against a recent stable release of Home Assistant before submitting.

---

## License

[MIT](LICENSE)