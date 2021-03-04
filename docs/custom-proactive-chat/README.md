# Custom Proactive Chat Notifications
If Gladly Sidekick is configured to use a custom minimized button, proactive chat notification will not be displayed to avoid UI discrepancies with the custom minimized button.

Proactive chat can still be used by utilizing the `campaign:triggered` Sidekick event together with the `Gladly.applyCampaign('<campaign-id>')` API.

This examples builds ontop of the "custom minimized button" example and the "working with events" example.

