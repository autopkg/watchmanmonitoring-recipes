Watchman Monitoring Recipes
===========================

A recipe to download the latest Monitoring Client version for a given subscription


## Fork this recipe

This recipe references a subscriber's subdomain. In order for this to work for you


## Downloading the client
Without AutoPkg, an IT administrator can download the latest build of their installer, and save it as a post-restore action in their deployment system of choice.

Using defaults to set preferences, even before deployment, the behavior of the monitoring client can be controlled.
See more at https://www.watchmanmonitoring.com/terminal-commands



## Auto update consideration
The MonitoringClient will auto-update by default. Installing any version 5.2 or better is ample for any environment which allows and desires auto-updating.

When a workflow or environment calls for disabling auto-update, the following command can be sent prior to* installation 

/usr/bin/defaults write /Library/MonitoringClient/ClientSettings Update_Enabled -bool false



* Within 10 minutes post-install would work as well.
