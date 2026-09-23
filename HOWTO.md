# Operator how-to

1. Obtain the approved package from the project owner.
2. Install it in Torch's `Plugins` folder and start Torch once.
3. Configure the generated updater configuration before enabling a managed plugin.
4. Restart Torch after the updater reports a staged update.

Managed plugins are opt-in. Turning a configuration entry off prevents its update checks and downloads.
