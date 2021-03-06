# Smarter Time Linux Releases

<h1 align="center">
  <img src="https://www.androidplanet.nl/wp-content/uploads/2018/01/smartertime-580x375.jpg" alt="smartertime-logo">
</h1>

# Content
- [Getting Started](#getting-started)
  * [Prequisites](#prequisites)
    + [Xdotool](#xdotool)
    + [grep](#grep)
    + [strings](#strings)
    + [python](#python)
  * [Usage](#usage)
    + [Retrieve your login informations](#retrieve-your-login-informations)
    + [Update Smartertime](#update-smartertime)
    + [Chrome Plugin](#chrome-plugin)
    + [Firefox Plugin](#firefox-plugin)
    + [Crash Reports](#crash-reports)
    + [Run SmarterTime on Boot](#run-smartertime-on-boot)
        - [Solution 1](#solution-1)
        - [Solution 2](#solution-2)
- [Release Notes](#release-notes)

## Getting Started

### Prequisites

#### Xdotool

You may need to install `xdotool` on your environment (it's installed by default on most Linux distros).
If you don't have it, please check this page: https://blog.hostonnet.com/installation-of-xdotool-on-linux.

#### grep

This is installed by default on most distros.  
  
On Debian/Ubuntu: `sudo apt-get install grep`

#### strings

Also installed by defaults on most distros.  
  
On Debian/Ubuntu: `sudo apt-get install binutils`

##### python

Recommended if you're using Firefox or Chrome, see https://docs.aws.amazon.com/cli/latest/userguide/awscli-install-linux-python.html

### Usage

Download the `AppImage` file that is available on the [releases page](https://github.com/Smartertime/SmarterTimeLinux/releases).  
The name of the file should be `SmarterTime*.AppImage`. Then mark it executable:
```bash
chmod a+x SmarterTime*.AppImage
```
And run it:
```bash
./SmarterTime*.AppImage
```

#### Retrieve your login informations

On the mobile app, roll out the menu on the left and click on `My Devices`.  
Then click on the `+` button (top right) and the email and code will be provided.  

#### Update Smartertime

Smartertime is weekly updated (it asks for your permission before).

Or manually update it: run Smartertime then click on `Help > Check for Updates`.  
  
If for any reason you can't run Smartertime, you can still update it by downloading AppImageUpdate tool on this [page](https://github.com/AppImage/AppImageUpdate/releases/).  
Look for `AppImageUpdate-*.AppImage` then apply it on Smartertime AppImage as follows:

```bash
./AppImageUpdate-*.AppImage SmarterTime-*.AppImage
```

After the update, there are two `.AppImage` files: the new updated one and the old one, you can remove the last one by running:

```
rm SmarterTime-*.AppImage.zs-old
```

#### Chrome Plugin

The plugin is still experimental and has been tested on `Ubuntu 18.04` for `Chrome (69.0.3497.100 64-bit)`.  
Note that `python` is required to use the plugin, see above section.  
  
Dowload the plugin: https://chrome.google.com/webstore/detail/smartertime/jbfgcoefigmnjcagjbcfagobiahnkobn and you're done!

#### Firefox Plugin

The plugin is still experimental and has been tested on `Ubuntu 18.04` for `Firefox 62.0 (64 Bit)`.  
Note that `python` is required to use the plugin, see above section.  
  
Download the plugin: https://addons.mozilla.org/en-US/firefox/addon/smartertime-linux/ and you're done!  
  
If you want to set it for global users, then copy `getfirefoxmessage.json` in `/usr/{lib,lib64,share}/mozilla/native-messaging-hosts/` as follows:

```bash
sudo cp ~/.mozilla/native-messaging-hosts/getfirefoxmessage.json /usr/lib/mozilla/native-messaging-hosts/
```

Be sure to replace `lib` with the correct value.

#### Crash Reports

Whenever the app crashes, a log file is automatically filled and sent.  
You may disable this behavior by running Smartertime and unchecking the option in `Help > Send Crash Reports`.
  
Crash logs are also stored locally in `/tmp/smartertime_crashlogs/`.

#### Run SmarterTime on boot

##### Solution 1

On Ubuntu, press Super Key (Windows key) then look for `Startup Applications` and open it. 
Click on `Add` button then look for `SmarterTime-*.AppImage` and add it, that's it, the job's done!  
See https://help.ubuntu.com/stable/ubuntu-help/startup-applications.html.en for further details

##### Solution 2

If you have enabled `crontab`, then type in terminal:

```bash
crontab -e
```

Then add the following line:

```
@reboot PATH/TO/SMARTERTIME.APPIMAGE
```

To get the absolute path of a file, use `readlink -f SmarterTime-*.AppImage`.

## Release Notes

**03/19**:
- Fixed memory leaks with Firefox & Chrome plugins.

**12/05**:
- Fixed a crash that may happen when using Chrome.
- Fixed a bug when user suddenly loses connection to Internet.
- Display an error message if active window name cannot be found.

**09/28**:
- Fixed a bug where weird visual effects may appear when signing-in
- Fixed a bug that could cause the PC to crash
- Fixed minor bugs

**09/27**:
- Send Chrome's active tab's URL for local user

**09/26**:
- Send Firefox's active tab's URL for local user
- Fixed minor bug

**09/25**:
- Send Firefox's active tab's URL

**09/17**:
- Automatically sign-in when running the app (still requires a first connection)

**09/14**:
- Fixed a bug where more than one device was created when signing in
