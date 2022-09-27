# Systemback

This is a fork of Systemback. The [original project](https://sourceforge.net/projects/systemback) is no longer maintained by the creator.

It's a simple system backup and restore application with extra features.

Systemback makes it easy to create backups of the system, configuration files, and user files. In case of problems you can easily restore the previous state of the system.

## Donate

Systemback is free so you can use it without any limitations.

Keeping the project alive takes a lot of work and research. If you want to contribute, you can help with a small donation. Any amount will be very welcome. Your contribution will help keep the project running for a long time.

I hope this program will be very useful to you.

You can donate by clicking on [this link](https://www.paypal.com/donate/?hosted_button_id=NT6YZP9PV7SY6 "Click to Donate Here").

or

By scanning the QR Code below.

![QR Code](.donate/image/MaranBr.png "Scan to Donate Here")

## Features

- System backup
- System copy
- System install
- System repair
- System restore
- System upgrade
- Live system create

## Requirements

Works as expected on:

- Linux Mint 19/20/21

It's possible that it works on other equivalent distributions based on Ubuntu as well.

## Downloads

You can get the latest builds on the [release page](https://github.com/MaranBr/Systemback/releases).

## Build From Source

### Install Build Dependencies

Install all dependencies needed to compile the source code using the command below:

```
$ sudo apt-get install build-essential debhelper devscripts libblkid-dev libmount-dev libncursesw5-dev libparted-dev qtbase5-dev qttools5-dev-tools git-all gnupg
```

### Generate GPG Key

If needed, you can generate a GPG key to sign the build for distribution using the command below:

```
$ gpg --full-generate-key
```

You will also need to change the `systemback/debian/changelog` in the application's source code to match the information used to generate the GPG key.

### Build Systemback

Clone the repository and follow the steps below:

```
$ git clone https://github.com/MaranBr/Systemback
```
```
$ cd Systemback/systemback
```

Generate signed builds (a valid gpg key is required):

```
$ debuild
```

Generate unsigned builds (no gpg key is required):

```
$ debuild -us -uc
```

The build files will be generated inside the Systemback root directory.

### Install Systemback

In the Systemback root directory, run dpkg command to install the packages:

```
$ cd Systemback
```
```
$ sudo dpkg -i *.deb
```

If there are dependency issues, install the missing dependencies with the following command:

```
$ sudo apt-get install -f
```

Then install the Systemback packages again:

```
$ sudo dpkg -i *.deb
```
