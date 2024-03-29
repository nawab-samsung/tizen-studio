# Install Tizen Studio on Ubuntu

This section guides you with downloading and installing Tizen Studio on your development hardware. 

To have the optimal installation experience, follow these steps chronologically:

- System prerequisites
  - Hardware requirements
  - Software requirements
- Setup Open JDK in Ubuntu
- Install dependencies
- Launch installer
- Verify installation

<style type="text/css">
a.clickable   { width: 100%; height: 100%; }
a.clickable:hover   { background-color: #FF0000; color: #FFFFF; }
</style>
### System Prerequisites

Ensure that the following system prerequisites are met:

#### Hardware Requirements
<table>
  <tr>
      <td width=150px>CPU</td>
    <td colspan="3" width=50px>Dual Core, 2Ghz or faster</td>
  </tr>
  <tr>
    <td>Architecture</td>
    <td width=520px>x32 or x64 </td>
  </tr>
  <tr>
    <td>Memory</td>
    <td colspan="3">3GB or more </td>
  </tr>
  <tr>
    <td>Disk Space</td>
    <td colspan="3">6 GB or more </td>
  </tr>
</table> 

#### Software Requirements
<table>
  <tr>
    <th colspan="2" align=left>Ubuntu</th>
  </tr>
  <tr>
    <td width=150px>Version</td>
    <td width=520px>16.04/ 14.04/ 18.04</td>
  </tr>
  <tr>
    <td>Bit</td>
    <td>32 or 64 bit</td>
  </tr>
</table>

<table>
  <tr>
    <th>Software</th>
    <th>Download Link </th>
  </tr>
  <tr>
    <td>Open JDK</td>
    <td width=520px>
    <a href="https://download.java.net/java/GA/jdk10/10/binaries/openjdk-10_linux-x64_bin.tar.gz"  class="clickable" target="_blank">https://download.java.net/java/GA/jdk10/10/binaries/openjdk-10_linux-x64_bin.tar.gz</a>
    </td>
  </tr>
  <tr>
    <td>OpenJavaFX</td>
    <td><a href="http://gluonhq.com/download/javafx-11-0-2-sdk-linux/" class="clickable" target="_blank">http://gluonhq.com/download/javafx-11-0-2-sdk-linux/</a></td>
  </tr>
  <tr>
    <td>Tizen Studio setup file</td>
    <td><a href=https://developer.tizen.org/development/tizen-studio/download# class="clickable" target="_blank">https://developer.tizen.org/development/tizen-studio/download#</a></td>
  </tr>
</table>

> **Note:**
>
> - Download the relevant version based on target device operating system, for example, **openjdk-10_linux-x64_bin.tar.gz**. 
> - Ensure you download the JavaFX <OS> SDK product only, for example: JavaFX Linux SDK.

**Disclaimer:** The third party download links are subjected to change. Alternatively, search and download the appropriate software.

## Set Up Open JDK

To set up Open JDK, follow these steps: 

1. Extract the downloaded **openjdk-10_linux-x64_bin.tar.gz** and **javafx-11-0-2-sdk-linux.zip** files at your preferred location.
   - Locate **jdk-10** and **javafx-sdk-11.0.2** directories.
     > **Note:**
     >
     >**jdk-10**, **javafx-sdk-11.0.2** directories are created as a result of extraction. 
   
2. Copy all the files except **src.zip** file from **lib** folder located in **javafx-sdk-11.0.2** directory.
3. Paste all the copied files in **lib** folder located in the **jdk-10** directory. 
   >Note:
   >
   >- In this installation guide, setting up OpenJDK is covered. However, Oracle JDK versions until version 10 are also supported.
   >- For Oracle JDK 10 installation steps, see the [Oracle official site](https://docs.oracle.com/javase/10/install/installation-jdk-and-jre-linux-platforms.htm#JSJIG-GUID-79FBE4A9-4254-461E-8EA7-A02D7979A161). 
   >- If you have installed Oracle JDK 10 or below already, you can skip the step. 
### Set Up Open JDK Path 

To set up the JDK path, follow these steps:  

1.	Open the Terminal.
2.	Type the following command in the terminal to set the JAVA_HOME as OpenJDK directory path, for example:
	- `JAVA_HOME=/home/<username>/Desktop/openJDK/jdk-10.0.2/`.
3.	Type the following commands in the terminal one after the other to complete the process:
	- `sudo update-alternatives --install /usr/bin/java java ${JAVA_HOME%*/}/bin/java 20000`
	- `sudo update-alternatives --install /usr/bin/javac javac ${JAVA_HOME%*/}/bin/javac 20000`
4.	Type the following command to get a list of JDK versions installed:
	- `sudo update-alternatives --config java`
	    > **Note:**
      >
      >If there are multiple versions of JDK installed, enter the selection number to choose your desired JDK version.

5. To configure the default Java compiler, type the following command:
	
   - `sudo update-alternatives --config javac`
	
	   > **Note:**
     >
     >**javac** is used for compilation. For more information on the differences between java and javac, see the official [site](https://docs.oracle.com).
	
6.	Type the `java –version` command to verify whether the OpenJDK version 10 is installed.
	
## Install Dependencies

The installer package consists of basic and immediate libraries. However, the Tizen Studio application requires additional libraries in order to work flawlessly. 

To install the dependencies: 
1.  Open the terminal, execute the following commands: 

- `sudo apt-get install expect`
- `sudo apt-get install gtk2-engines-pixbuf`
- `sudo apt-get install libgnome2-0`
- `sudo apt-get install qemu-user-static`
- `sudo apt-get install libwebkitgtk-1.0-0`
- `sudo apt-get install gettext`
- `sudo apt-get install gksudo`
- `sudo apt-get install module-init-tools`
- `sudo apt-get install libudev-dev`
- `sudo apt-get install libsdl1.2debian`
- `sudo apt-get install bridge-utils`
- `sudo apt-get install openvpn`

## Launch Installer 
To launch the installer, follow these steps:

1. Open your terminal and execute the following commands:
	
	- `chmod +x web-ide_Tizen_Studio_x.x_ubuntu-64.bin`
	- `./web-ide_Tizen_Studio_x.x_ubuntu-64.bin` 
	>Note:
	>
	>**x.x** represents the latest version of Tizen Studio, for example: web-ide_Tizen_Studio_**3.2**_ubuntu-64.bin.
2. Accept the software license.
   
   > **Note:**
   >
   >The license contains important legal notices for using Tizen Studio. Read it fully, and click **Accept** only if you agree with the license terms.

   ![Tizen Studio License Agreement](./media/install_sdk_license.png)

3. Click **...** and specify a new directory to set the SDK and the data location.

   ![Set SDK and data location](./media/install_sdk_directory.png)
   >**Note:** 
   > 
   >If the new directory is valid, it shows no errors.
4. Click **Install**.
   >Note:
   >
   >You can monitor the installation process or cancel the installation. The installation process takes a few minutes, unless you cancel it.

5. Click **Finish** to close the installer.

   ![Installation complete](./media/migration_finish_instal.png)

   > **Note**
   >
   >If you want to install additional platforms and tools, launch the Package Manager by checking the **Launch the Package Manager** check box and click **Finish**.
   > - Use Tizen Studio Package Manager, to install and update additional tools. 
   > - For more information on the Package Manager, see [Updating Tizen Studio](./update-sdk.md).

### Verify Installation
   
To verify whether the installation is successful, follow these steps: 
   
   1. Click **Tizen Studio icon**, Tizen Studio IDE appears.