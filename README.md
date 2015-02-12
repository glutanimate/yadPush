# yadPush

<p align="center">
  <img src="https://github.com/Glutanimate/yadPush/blob/master/desktop/yadpush-header.png" alt="yadPush header"/>
</p>

**yadPush** is a simple graphical Pushbullet client designed for Linux. It is based on [`pushbullet-gui`](https://github.com/lbrfabio/bash/tree/master/pushbullet-gui) by [lbrfabio](https://github.com/lbrfabio).

## Table of Contents

<!-- MarkdownTOC -->

- [Features and screenshots](#features-and-screenshots)
- [Installation](#installation)
    - [Dependencies](#dependencies)
    - [Authentication with Pushbullet](#authentication-with-pushbullet)
    - [Setup](#setup)
- [Usage](#usage)
- [Known issues](#known-issues)
- [Credits](#credits)
- [License](#license)

<!-- /MarkdownTOC -->

## Features and screenshots

*yadPush* is write-only Pushbullet client. It can send pushes, but cannot receive any. 

The following types of pushes are supported:

- notes
- links
- lists
- addresses
- files (support is somewhat [unreliable](#known-issues))

![yadPush Screenshot 1](https://github.com/Glutanimate/yadPush/blob/master/screenshots/yadpush-1.png)

![yadPush Screenshot 2](https://github.com/Glutanimate/yadPush/blob/master/screenshots/yadpush-2.png)

## Installation

### Dependencies

*yadPush* depends on `yad`, `libnotify-bin`, and `pushbullet-bash`.

On Ubuntu 12.04 and up you can install the first two dependencies with the following commands:

    sudo add-apt-repository ppa:webupd8team/y-ppa-manager
    sudo apt-get update
    sudo apt-get install yad libnotify-bin

You will have to install `pushbullet-bash` manually by checking it out of [its repository](https://github.com/Red5d/pushbullet-bash) and adding it to your `$PATH`, e.g.:

    git clone https://github.com/Red5d/pushbullet-bash.git
    cd pushbullet-bash
    sudo ln -s pushbullet /usr/local/bin/pushbullet

### Authentication with Pushbullet

`pushbullet-bash` requires a Pushbullet API key to work. You can find your personal access token on your [Pushbullet account page](https://www.pushbullet.com/account). 

To complete the installation of `pushbullet-bash` you will have to set your API key by creating `$HOME/.config/pushbullet` and adding the following line to it:

    API_KEY=1sa6712s9n219n912

(where `1sa6712s9n219n912` is your personal access token copied from your account page). 

Please be aware that your access token is similar to a password and has to be kept safe. To quote the Pushbullet documentation:

> Keep in mind that this key has full access to your account, so don't go posting it all over the internets.

### Setup

1. Install all dependencies and set your API key up

2. Clone this repository or download the latest zip-file and extract it. Place the folder wherever you prefer, but make sure not to delete it after completing these steps.

3. Navigate to the extracted folder and run `yadpush`

4. (optional) Add `yadpush` to your `$PATH`:

        cd yadPush
        sudo ln -s ./yadpush /usr/local/bin/yadpush

5. (optional) Install the launcher:

        sudo ln -s ./desktop/yadpush.desktop /usr/local/share/applications/yadpush.desktop

6. (optional) Install the icon:

        sudo ln -s ./desktop/yadpush.svg /usr/local/share/icons/hicolor/scalable/apps/yadpush.svg

## Usage

Having followed the installation procedure correctly you should now be able to find a *yadPush* entry in your launcher. Click on it to launch *yadPush*. To push something to Pushbullet simply select the respective tab and fill out all fields.

*yadPush* also supports pushing files directly via your file manager's context menu. 

To use this functionality right click on a file of your choice and invoke the extended list of applications under the *Open with* entry. If you installed the `.desktop` launcher correctly you should be able to find *yadPush* in the list of supported apps. Select the entry to push your file to Pushbullet. You will be asked to confirm your choice before the file is uploaded.

Please note that the Pushbullet API supports a maximum file size of 25 MB. Depending on your Internet connection the file upload might take a while. As it stands, *yadPush* does not come with a progress window. You will simply have to wait for your upload to complete.

## Known issues

- while `pushbullet-bash` supports file uploads, the support can be somewhat spotty. I've found that in some cases the Android Pushbullet client wouldn't download files uploaded via *yadPush*. Unfortunately I haven't been able to track this issue down, yet.

## Credits

I would like to extend my heartfelt thanks to [lbrfabio](https://github.com/lbrfabio) for his work on [`pushbullet-gui`](https://github.com/lbrfabio/bash/tree/master/pushbullet-gui). *yadPush* would not exist without it.

I would also like to thank [Red5d](https://github.com/Red5d) and everyone else who contributed to [pushbullet-bash](https://github.com/Red5d/pushbullet-bash).

## License

*yadPush* copyright 2015 Glutanimate

*yadPush* is licensed under the [GNU GPLv3](http://www.gnu.de/documents/gpl-3.0.en.html).

This project is not endorsed, certified or otherwise approved in any way by Pushbullet™.