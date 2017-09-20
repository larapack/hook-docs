# Getting Started

A hook is basicly a Laravel service provider that is loaded automatically when that hook is enabled.  
A hook can have 3 states:
* **Not-installed** - This hook is not installed, but exists in the application for some reason, this is mostly only the case if you are building your own hook. In this case you have the option to install or delete the hook.
* **Disabled** - This hook is installed, means that it have been installed but its service providers are not loaded yet. In this case you have the option to uninstall or enable the hook.
* **Enabled** - This hook is installed and enabled, means that it's service providers will now be loaded. In this case you have the option to disable or uninstall the hook.

When working with hook there are 4 actions:
* **Install** - This will download the hook if not already downloaded and then run the installation of that hook.
* **Enable** - After installing a hook, you will have to enable it in order to load it service providers.
* **Disable** - If you ever need to disable the functionality that the hook came along with, you can always disable it to keep its configuration.
* **Uninstall** - This will disable a hook if not already disabled and then remove all the configurations and undo the whole installation of a hook along with deleting it from the system.

The hook system comes with multiple Artisan commands:
* *hook:check* - Check for updates and show hooks that can be updated
* *hook:disable* - Disable a hook
* *hook:enable* - Enable a hook
* *hook:info* - Get information on a hook
* *hook:install* - Download and install a hook from remote https://larapack.io
* *hook:list* - List installed hooks
* *hook:make* - Make a hook
* *hook:setup* - Prepare Composer for using Hooks
* *hook:uninstall* - Uninstall a hook
* *hook:update* - Update one or more hooks
