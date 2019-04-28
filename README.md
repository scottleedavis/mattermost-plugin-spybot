# Mattermost Plugin Spybot  [![CircleCI](https://circleci.com/gh/scottleedavis/mattermost-plugin-spybot.svg?style=svg)](https://circleci.com/gh/scottleedavis/mattermost-plugin-spybot)

Inspired by the [mattermost-spybot](https://github.com/prabhu43/mattermost-spybot) integration.

Has the slash commands `/spy @username` and `/unspy @username`

You get a notification when the person is online, offline, or 'do not disturb'.  (away is ignored)

![screenshot.png](screenshot.png)


### Installation

_requires Mattermost 5.10 or greater_

1) Go to the [releases page](https://github.com/scottleedavis/mattermost-plugin-remind/releases) of this GitHub repository and download the latest release for your Mattermost server.
2) Upload this file in the Mattermost System Console > Plugins > Management page to install the plugin. To learn more about how to upload a plugin, see the documentation.
    
### Building
```
make
```

This will produce a single plugin file (with support for multiple architectures) for upload to your Mattermost server:

```
dist/com.example.my-plugin.tar.gz
```

There is a build target to automate deploying and enabling the plugin to your server, but it requires configuration and [http](https://httpie.org/) to be installed:
```
export MM_SERVICESETTINGS_SITEURL=http://localhost:8065
export MM_ADMIN_USERNAME=admin
export MM_ADMIN_PASSWORD=password
make deploy
```

Alternatively, if you are running your `mattermost-server` out of a sibling directory by the same name, use the `deploy` target alone to  unpack the files into the right directory. You will need to restart your server and manually enable your plugin.

In production, deploy and upload your plugin via the [System Console](https://about.mattermost.com/default-plugin-uploads).
