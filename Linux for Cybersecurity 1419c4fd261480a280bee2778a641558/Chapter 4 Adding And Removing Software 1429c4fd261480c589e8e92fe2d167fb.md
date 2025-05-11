# Chapter 4 Adding And Removing Software

# Using apt to Handle Software

### `apt-cache search “snort”` - search for a software package in your repository

### `apt-get install “snort”` - Adding Software

## Removing Software

`apt-get remove “snort”` -  To remove software in Linux

`apt-get purge “snort”` -  If you want to remove the configuration files as well

`apt-get autoremove “snort”` - After uninstalling, remove unnecessary dependencies

## Updating Packages

`apt-get update` - This checks your system’s package list against the repository for updates.

`apt-get upgrade` -This upgrades all outdated packages found in the repository. **Updating** only refreshes the list of available software; it doesn’t install updates. To apply updates, use the upgrade command

## Adding Repositories to Your `sources.list` File

`vim /etc/apt/source.list` - Repositories store software packages for Linux distributions, and you can customize your system by adding new ones to your `sources.list` file.

## **Structure of Repositories**

Repositories are categorized based on their content:

- **main**: Supported open-source software.
- **universe**: Community-maintained open-source software.
- **multiverse**: Software restricted by copyright or licensing.
- **restricted**: Proprietary drivers.
- **backports**: Packages from later releases.

### Synaptic gui installation

- **Search for Packages**:
    - Use the **Search** tab to find specific software (e.g., `snort`).
    - Type the package name in the search window and click **Search**.
- **Install Packages**:
    - Once found, check the box next to the package.
    - Click **Apply** to install the selected package along with its dependencies.

## `git clone “httpls//…”` - download repository from git