Watchman Monitoring Recipes
===========================

A recipe to download the latest Monitoring Client version for a given subscription

### Override Required

This recipe includes a spot for your subscription's subdomain. The recipe will not function without an override file to set your subdomain.

Override files can be created with [AutoPkgr](http://www.lindegroup.com/autopkgr/), by hand, or by simply downloading a pre-configured override file from your [Watchman Monitoring Installers Page.](https://ors.monitoringclient.com/installers/mac#autopkg)


### Downloading the client
With AutoPkg, an IT administrator can download the latest build of their installer. 

### Set Defaults Pre-Install

There are many settings which a Watchman Monitoring administrator may want to adjust. They can all be set with `defaults write`, if you know where to put the key.

The most common are documented with examples in this support article:  
https://www.watchmanmonitoring.com/terminal-commands

When handling mass deployments, two keys stand out in importance; the Group name, and auto-update.

### Set the Group name before deployment

Each computer is sorted into a [Group](https://watchmanmonitoring.zendesk.com/hc/articles/298904-What-is-a-Group). Good Group names include the company, department, or family who owns the computer.

Without a Group set, computers will fall into a group named `Blank`. They can be sorted from there, but setting the Group before installation is more efficient. 

The following command will set a Group name, even before installation. Replacing `ENTER_GROUP_NAME` is suggested, of course.

`/usr/bin/defaults write /Library/MonitoringClient/ClientSettings ClientGroup -string "ENTER_GROUP_NAME"`


### Auto update consideration
The MonitoringClient will auto-update by default. When a workflow or environment calls for disabling auto-update, the following command can be sent prior to installation: 

`/usr/bin/defaults write /Library/MonitoringClient/ClientSettings Update_Enabled -bool false`

