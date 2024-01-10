# Installation

To manage git repositories on your local machine you need to have git installed locally.

Here's how to install git on major desktop operating systems.

## Windows

Using [winget](https://docs.microsoft.com/en-us/windows/package-manager/winget) (this tool is available on Windows 10 and up)

```bash
winget install --id Git.Git -e --source winget
```

You can also download a binary package from [here](https://github.com/git-for-windows/git/releases/download/v2.43.0.windows.1/Git-2.43.0-64-bit.exe).

## Linux

Install the `git` package using your distribution's package manager.

Here are some major distributions examples.

**Debian | Ubuntu**

```bash
sudo apt install git
```

**Fedora | RedHat**

```bash
sudo dnf install git
```

**openSUSE**

```bash
sudo zypper i git
```

**Arch | Manjaro | Endavour**

```bash
sudo pacman -S git
```

## macOS

- If you have [brew](https://brew.sh/) installed, use the following command.

  ```bash
  brew install git
  ```

- If you don't, download it from [Xcode](https://developer.apple.com/xcode/)

- If have [MacPorts](https://www.macports.org/) installed use the following command.

  ```bash
  sudo port install git
  ```

# Identity configurtion

Configuing your identity assigns your name and email to each commit you make on your machine, we'll talk about commits and blame later on, but do the configurtion now so Git won't get confused when you make a commit, you don't wanna upset Git, do you?

```bash
git config --global user.name "Full Name"
git config --global user.email "your@example.com"
```

The first thing you should do when you install Git is to set your user name and email address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating:

___

### [⇐ Previous](/README.md) | [Next ⇒](/material/02-basics.md)
