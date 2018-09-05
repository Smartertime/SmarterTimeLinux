# Smarter Time Linux Releases

<h1 align="center">
  <img src="https://www.androidplanet.nl/wp-content/uploads/2018/01/smartertime-580x375.jpg" alt="smartertime-logo">
</h1>

# Content
- [Getting Started](#getting-started)
  * [Prequisites](#prequisites)
    + [Xdotool](#xdotool)
  * [Usage](#usage)
    + [Retrieve your login informations](#retrieve-your-login-informations)
    + [Update Smartertime](#update-smartertime)
    + [Crash Reports](#crash-reports)

## Getting Started

### Prequisites

#### Xdotool

You may need to install `xdotool` on your environment (it's installed by default on most Linux distros).
If you don't have it, please check this page: https://blog.hostonnet.com/installation-of-xdotool-on-linux.

### Usage

Download the `AppImage` file that is available on the [releases page](https://github.com/Smartertime/SmarterTimeLinux/releases).  
The name of the file should be `SmarterTime*.AppImage`. Then mark it executable:
```
chmod a+x SmarterTime*.AppImage
```
And run it:
```
./SmarterTime*.AppImage
```

#### Retrieve your login informations

On the mobile app, roll out the menu on the left and click on `My Devices`.  
Then click on the `+` button (top right) and the email and code will be provided.  

#### Update Smartertime

Smartertime is weekly updated (it asks for your permission before).

Or you can also manually update it: run Smartertime then click on `Help > Check for Updates`.  
After the update, there are two `.AppImage` files: the new updated one and the old one, you can remove the last one by running:

```
rm SmarterTime-*.AppImage.zs-old
```

#### Crash Reports

Whenever the app crashes, a log file is automatically filled and sent.  
You may disable this behavior by running Smartertime and unchecking the option in `Help > Send Crash Reports`.
  
Crash logs are also stored in `/tmp/smartertime_crashlogs/`.
