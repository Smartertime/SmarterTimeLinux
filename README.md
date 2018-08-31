# Smarter Time Linux Releases

<h1 align="center">
  <img src="https://www.androidplanet.nl/wp-content/uploads/2018/01/smartertime-580x375.jpg" alt="smartertime-logo">
</h1>

# Content
- [Getting Started](#getting-started)
  * [Prequisites](#prequisites)
    + [Xdotool](#xdotool)
    + [Java](#java)
  * [Usage](#usage)
    + [Retrieve your login informations](#retrieve-your-login-informations)

## Getting Started

### Prequisites

#### Xdotool

You may need to install `xdotool` on your environment (it's installed by default on most Linux distros).
If you don't have it, please check this page: https://blog.hostonnet.com/installation-of-xdotool-on-linux.  
  

#### Java

A Java environment is also required, see [Install Java on Linux](https://www.wikihow.com/Install-Java-on-Linux). You may also need to set your `JAVA_HOME` environment variable. In a terminal, open with your text editor `/etc/environment`:

```
sudo nano /etc/environment
```

At the end of the file, add the following line:

```
JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"
```

Make sure to replace the last part `java-11-openjdk-amd64` with your own directory containing the JRE, e.g. it could be `java-8-oracle`. To find where it is located, type in a terminal:

```
readlink -f $(which java)
```

Save and exit the file then source it:

```
sudo source /etc/environment
```

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
