# finito
📣 Get a push notification when a command has finished running

![finito screenshots](https://i.imgur.com/KkvCnu4.png)

## What

`finito` is a tool that runs the command you supplied and then sends you a push notification
when the command has finished running.<br>
You use `finito` by adding it before the command you want to run.
For example, to be notified when `bitbake core-image-minimal` has finished running:

```bash
finito bitbake core-image-minimal
```

## Why

`finito` was created to minimize the "lost" time between a long-running command finishing
and the moment you realize it did.<br>
I often execute commands that take a long time to run.
While I do not want to continuously monitor the command, I would like to know when it does as soon as possible.
This can be a considerable time-saver since the tool allows you to focus on other activities,
without periodically distracting yourself to check the progress of the command.

## How

`finito` depends on [IFTTT](https://ifttt.com/) and `curl` to send push notifications to your mobile device.

To set the script up, the easiest way is to run the [finito-config.sh](finito-config.sh) script.
It includes a step-by-step guide on how to:
1. Set up an IFTTT account
2. [Create an applet](https://ifttt.com/create) with a webhook trigger and a notifications action
3. Getting your access key

The configuration script will make all the necessary modifications to `finito` to work with your IFTTT account.
You can run `finito-config.sh` either by downloading it from here, making it executable and running it on your computer
or by executing the following command:

```bash
source <(curl -s https://raw.githubusercontent.com/platisd/finito/master/finito-config.sh)
```

Alternatively, you may download [finito](finito) directly, make it executable and change the appropriate fields yourself.<br>
Another way to configure `finito` is by setting the appropriate environment variables. Review the [script](finito)
for further details.

Finally, to receive notifications you will need to install the IFTTT app on your phone
([Android](https://play.google.com/store/apps/details?id=com.ifttt.ifttt),
[iOS](https://apps.apple.com/us/app/ifttt-automation-workflow/id660944635)) and login with your account.
