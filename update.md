# Update Tizen Studio

This page explains how to install, update, and remove packages using package manager tool, and also guides advanced users to manage packages with the CLI version of the tool. 

Tizen Studio primarily consists of collections of packages with necessary files, metadata, installation and removal scripts. Each package is intertwined with dependencies. The Package Manager offers an easy and simple way to manage packages without getting into the complicated package dependencies.

In addition, the Tizen Package Manager is a comprehensive package management tool included with Tizen Studio to manage processes like installation, updation, and uninstallation of packages and platforms using GUI or CLI versions of the tool. 

The page guides you with the following:

- Start Package Manager.
- Components of Package Manager. 
- Update packages and platforms.
- Install additional packages.
- Cancel installation.
- Retry cancelled installation.
- Remove packages. 
- Monitor progress.
- Update with CLI tool.


## Start Package Manager

Follow these steps to open package manager corresponding to your operating system:

**Windows&reg:**
- Click **Start > All Programs > Tizen Studio > Tools > Package Manager**.

**MacOSX:**
- Click **Launchpad > Package Manager**.

**Ubuntu:**
- Click **Dashboard Home > Package Manager**.

**Figure: Package Manager Main Window**

![Package Manager main window](./media/updating_sdk_main.png)

## Package Manager Components: 

The Package Manager consists of the following components:

- **Header area** component comprises of the following elements:

  - **Trouble Shooting** (![Inside Trouble Shooting icon](./media/updating_sdk_icon_troubleshoot.png)) to access troubleshooting guides that help you resolve common issues related to Package Manager.
  - **Configuration** (![Configuration icon](./media/updating_sdk_icon_config.png)) to change Package Manager configuration and other related settings, such as package repository locations and proxy options etc.
  - **Information** (![Information icon](./media/updating_sdk_icon_info.png)) to access the details about Package Manager, such as the version number, installation path, package repository URL, distribution name, and package snapshot.

- **Main area** component comprises of the following elements:

  - **Main SDK** tab: enables you to install, remove packages, platforms and tools. In addition, the filter buttons narrows down the choice of the package list display based on the selected profiles.
  - **Extension SDK** tab: enables you to install or remove extension tools and packages, such as the Samsung Certificate Extension etc.
  - **Progress** tab: facilitates you to see which packages are being installed or removed.

  In **Main SDK** and **Extension SDK** tabs, you can also list the installed packages by selecting the **View installed packages** check box.

  **Figure: Package list**

  ![Package list](./media/updating_sdk_main_area.png)

- **Description area**: shows detailed description of each package or platform that is currently selected on the list in the main area.

  **Figure: Description area**

  ![Description area](./media/updating_sdk_description.png)

## Update Packages

Package Manager makes it effortless to update your packages and platforms. You can use Package Manager tool to locate and install updates and new features for packages that are installed. 
- Before you begin to update a package, ensure that the Package Manager has access to the repository that contains the packages, and you have access to Internet. 
- If the updates are available for your existing Tizen Studio packages and platforms, **Updates available** button appears in Package Manager window. 

To update the packages, follow these steps: 

1. Click **Updates available** to update all the packages that are currently installed. 
    
**Figure: Updates available button**

![Updates available button](./media/updating_sdk_updates.png)

>**Note:**
>
>To ensure system integrity across all the packages in Tizen Studio, Package Manager does not support updating packages individually.

In case, you do not have access to internet, you can update the packages with an image file, which can be downloaded separately. 

### Update Packages Offline
To install the packages with an image file, follow these steps:

1. Click **Configuration** (![Configuration icon](./media/updating_sdk_icon_config.png)) in the Package Manager.
2. Enter the full path of the image file in the **Package Repository** box. Alternatively, click **...** next to the combo box to open the file browser and select the image file.
3. Click **Open** to close the dialog.

    >**Note:**
    >
    >If the image file is valid, detailed information about the image is displayed below the combo box.

4. Click **OK** to close the **Configuration** dialog, by doing so, **Update available** button appears. Now, you can update and install additional platforms and tools with the image file.

    > **Note**  
    > 
    > Make sure that the image file includes a newer Tizen Studio version than your installed version before updating or installing with the image file.

## Install Additional Packages

If you plan to install a specific platform or tool, using the **Main SDK** and **Extension SDK** tabs, follow this step:
1. Click **install** next to that platform or tool in the list.

The Package Manager installs all packages that are required for that platform or tool.

To install individual packages for a particular platform or tool, follow these steps: 
 
 1. Click on **collapsible** icon located on the left of the main area for each platform or tool to view more packages and tools.
 2. Click **install** next to the package you want to install.

**Figure: Installing platform packages**

![Installing platform packages](./media/updating_sdk_install_platform.png)

## Cancel Installation

In case, if you plan to cancel the installation process, follow this step: 

1. Click the **x** button on **Progress** tab next to the package. 

>**Note:** 
>
>Due to package dependencies, cancelling the installation of a single package may cancel the installation of other packages also.

**Figure: Cancelling installation**

![Cancelling the installation](./media/updating_sdk_install_cancel.png)

## Retry Cancelled Installation 

In case, if you plan to retry a cancelled or failed installation, follow this step: 

1. Click **retry** (![Retry icon](./media/updating_sdk_icon_retry.png)). 

>**Note:**
>
>Due to package dependencies, retrying the installation of a single package may cause the installation of other packages also.

## Remove Packages

Package manager is a comprehensive tool that manages all the package removal tasks effortlessly. 

To remove a package, follow this step: 

1. Click **delete** located next to the respective package. 

>**Note:**
>
>- Due to package dependencies, removing a single package may cause other packages to be removed also. 
>- To ensure system integrity across all installed Tizen Studio packages, package removal cannot be cancelled while removal process is in progress.

**Figure: Removing packages**

![Removing packages](./media/updating_sdk_install_remove.png)

## Monitor Progress

Tizen studio provides a progress bar where you can monitor the installation, update, or removal progress.

This intuitive progress bar appears on the header area and helps in checking the overall progress of a respective process. 

Also, to monitor the progress of specific installation, uninstallation, or update, as well as view the expected time of completion, use the **Progress** tab.

**Figure: Progress tab**

![Progress tab](./media/updating_sdk_progress.png)

## Update with CLI Package Manager

For advanced users, Tizen Studio provides command line version of package manager tool. It can be used to install, update, remove packages and platform tools respectively.  

To Run CLI version of Package Manager with the `update` command, use the following syntax:

```
package-manager-cli update [--accept-license] [--no-java-check] [--proxy <value>] [-f <file path>] [-p <password>] [--latest]
```

The following table lists various options that must be appended to the syntax for desired choice of the process:   
**Table: Update command parameters**

| Parameter                   | Description                              |
|---------------------------|----------------------------------------|
| `--accept-license`          | Accepts the license terms.               |
| `--no-java-check`           | Skips the Java version check.            |
| `--proxy <value>`           | Proxy configuration value. You can use one of the following values: **direct**, **auto**, or **ip:port**. |
| `-f, --file <file path>`    | If you want to install packages from a local SDK image, specify the full path of the SDK image file. |
| `-p, --password <password>` |specifies Administrator (sudo) password for authentication. Ubuntu only. |
| `--latest`                  | specifies the option useful for updating the Tizen Studio to the latest version, assuming that you have downgraded it manually to an earlier version. Otherwise, the Package Manager updates it to the latest version with or without this option. |

## Related Information
* Dependencies
  - Tizen Studio 1.0 and Higher
