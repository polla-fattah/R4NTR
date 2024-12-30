---
layout: page
title: "Appendix A: Installation and Setup Guides"
chapter: true
order: 170
published: true
abstract: Step-by-step instructions for installing R and RStudio, ensuring readers can set up their working environment quickly and effectively.
---

## Installing R

Getting R onto your computer is a straightforward process, whether you’re using Windows, macOS, or Linux. The installation follows a similar pattern across all platforms: visit the CRAN website, choose the version appropriate for your system, and run the provided installer. Let’s walk through the steps for each operating system, and feel free to refer to the placeholder images for a visual guide as you go along.

### Windows Installation

On CRAN [https://cran.r-project.org/bin/windows/base/](https://cran.r-project.org/bin/windows/base/), click “Download R for Windows” and then “base.” Select the latest version of R and save the `.exe` installer to your computer

{% include figure.html
    caption="CRAN Windows download page"
    url="/assets/img/appendix01/windows-download.png"
%}

#### **Step 1:Run the Installer:**

Double-click the downloaded `.exe` file. The R Setup Wizard will open. Select your preferred language and click OK.  
{% include figure.html
    caption="Select the installer language"
    url="/assets/img/appendix01/win-install-01.png"
%}

#### **Step 2:Accept the License:**  R is distributed under GPL (General Public License), which allows you to use, modify, and distribute the software freely. Reade the License if you want to then Click “Next” to proceed.

{% include figure.html
    caption="Read and Agree to the license terms"
    url="/assets/img/appendix01/win-install-02.png"
%}

#### **Step 3:Select Installation Location:**  By default, R will install in the `C:\Program Files\R\R-x.x.x` directory. You can change this location if needed. Click “Next” to continue

{% include figure.html
    caption="Select Installation Location"
    url="/assets/img/appendix01/win-install-03.png"
%}

#### **Step 4:Select Components:**  The default components are sufficient for most users. If you have sufficient disck space you can install all components. Click “Next” to proceed

{% include figure.html
    caption="Select what to be installed"
    url="/assets/img/appendix01/win-install-04.png"
%}

#### **Step 5:Customize Startup:** You can accept the default startup options. Or customize then Click “Next” to proceed

{% include figure.html
    caption="Select Default Installation Options"
    url="/assets/img/appendix01/win-install-05.png"
%}

#### **Step 6:Select Start Menu Folder:**  By default, R will create a Start Menu folder for its shortcuts. You can change this if needed. Click “Next” to continue  

{% include figure.html
    caption="Specify Start Menu Folder"
    url="/assets/img/appendix01/win-install-06.png"
%}

#### **Step 7:More Customization:**  You can select shortcuts to be created on the desktop and the quick launch bar, However I hated these options. For registry entries make sure they are selected as these can make your life a bit easier in the future. Click “Next” to proceed.

{% include figure.html
    caption="Customizations"
    url="/assets/img/appendix01/win-install-07.png"
%}

#### **Step 8:Wait for installation to complete:**  The installer will copy files and set up R on your system. Once the process is complete, you’ll see a confirmation message. Click “Finish” to exit the installer

{% include figure.html
    caption="Wait for Installation to Complete"
    url="/assets/img/appendix01/win-install-08.png"
%}

### macOS Installation

#### **Step 1:Download the .pkg File:**  From [https://cran.r-project.org/bin/macosx/](https://cran.r-project.org/bin/macosx/), click “Download R for macOS” and choose the appropriate `.pkg` installer for your macOS version. Save it to your Downloads folder.  

{% include figure.html
    caption="CRAN macOS download page"
    url="/assets/img/appendix01/MacOs-Download.png"
%}

#### **Step 2:Open the Installer:** Locate the downloaded `.pkg` file in your Downloads folder and double-click it to start the installation process

{% include figure.html
    caption="Starting the R installation on macOS"
    url="/assets/img/appendix01/install-R-mac02.png"
%}

#### **Step 3:Welcome Screen:** The installer will display a welcome screen. Click “Continue” to proceed

{% include figure.html
    caption="Welcome screen for installation"
    url="/assets/img/appendix01/install-R-mac03.png"
%}

#### **Step 4:Read Me:** Review the Read Me information and click “Continue.”  

{% include figure.html
    caption="Read Me section of the installer"
    url="/assets/img/appendix01/install-R-mac04.png"
%}

#### **Step 5:Software Agreement:** Read the software license agreement, then click “Agree” to accept the terms

{% include figure.html
    caption="Software agreement screen"
    url="/assets/img/appendix01/install-R-mac05.png"
%}

#### **Step 6:Installation Type:** Choose the default installation settings and click “Install.” . You can customize the installation location if needed as well as changing the destination of the installation

{% include figure.html
    caption="Choosing installation type"
    url="/assets/img/appendix01/install-R-mac06.png"
%}

#### **Step 7:Enter Password:** Enter your macOS password to authorize the installation and click “OK.”  

{% include figure.html
    caption="Entering macOS password"
    url="/assets/img/appendix01/install-R-mac07.png"
%}

#### **Step 8:Wait for Installation:** The installer will copy files to your system. Wait for the process to complete

{% include figure.html
    caption="Installation in progress"
    url="/assets/img/appendix01/install-R-mac08.png"
%}

#### **Step 9:Summary of Installation:** Once the installation is complete, a summary screen will appear. Click “Close” to finish

{% include figure.html
    caption="Installation summary"
    url="/assets/img/appendix01/install-R-mac09.png"
%}

#### **Step 10:Launch R from Launchpad:** Open Launchpad and click the R icon to launch the application

{% include figure.html
    caption="Launching R from Launchpad"
    url="/assets/img/appendix01/install-R-mac10.png"
%}

#### **Step 11:Verify Installation in Terminal:** Open the Terminal app and type `R`. Press Enter to confirm that R is successfully installed and running

{% include figure.html
    caption="Verifying R installation in Terminal"
    url="/assets/img/appendix01/install-R-mac11.png"
%}

## Linux Installation

To install R on Ubuntu, follow these instructions:

### **Install R Using the Default Distribution Source**

This method installs R from the default Ubuntu repository. While simple and stable, the version may not be the most recent.

#### Step-by-Step Instructions

#### **Step 1:Update the Package List:**

   Begin by refreshing the package list to ensure you have the latest information:

```bash
sudo apt update
```

#### **Step 2:Install R from the Default Ubuntu Repository:**

Use the following command to install R:

```bash
sudo apt install r-base -y
```

The `-y` flag automatically confirms the installation.

#### **Step 3:Verify the Installation:**

Confirm that R is installed successfully by checking its version:

```bash
R --version
```

### **Install R from a Newer Source (CRAN)**

This method installs the latest version of R directly from CRAN. It involves adding the CRAN repository to your system and setting up its signing key for secure installation.

#### **Step 1:Add the CRAN Repository to Your System:**

- Open the `/etc/apt/sources.list` file for editing:

```bash
sudo nano /etc/apt/sources.list
```

- Append the following line at the end of the file, replacing `noble` with your Ubuntu version codename (e.g., `focal` for 20.04, `jammy` for 22.04):

```bash
deb https://cloud.r-project.org/bin/linux/ubuntu noble-cran40/
```

- Save the changes and exit the editor (`Ctrl+O`, `Enter`, `Ctrl+X`).

#### **Step 2:Add the CRAN Signing Key:**

To ensure package integrity, add the CRAN GPG signing key:

```bash
sudo apt install --no-install-recommends dirmngr
gpg --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
gpg --export E084DAB9 | sudo tee /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc
```

#### **Step 3:Update the Package List:**

Refresh your package list to include the CRAN repository:

```bash
sudo apt update
```

#### **Step 4:Install R:**

   Install the latest version of R from CRAN:

   ```bash
   sudo apt install r-base -y
   ```

#### **Step 5:Verify the Installation:**

Confirm that the latest version of R is installed by checking its version:

   ```bash
   R --version
   ```

#### **Step 6:Check Installed Libraries:**

To view the libraries available in your R environment, open R and run:

   ```R
   library()
   ```

## Installing RStudio

### Windows Installation

Installing RStudio on Windows is a straightforward process. Follow the steps below to set up RStudio on your computer:

#### **Step :Download RStudio:** Visit the official RStudio download page at [posit.co/download/rstudio-desktop/](https://posit.co/download/rstudio-desktop/) and select the free Desktop version compatible with your system

{% include figure.html  
    caption="CRAN Windows download page"  
    url="/assets/img/appendix01/Install-Windows-Rstudio00.png"  
%}

#### **Step 1:Run the Installer:** Locate the `.exe` file you just downloaded—usually found in your Downloads folder. Double-click the file to initiate the installation process.

{% include figure.html  
    caption="Starting the RStudio installation on Windows"  
    url="/assets/img/appendix01/Install-Windows-Rstudio01.png"  
%}

#### **Step 2:Welcome Screen:** Upon starting the installer, you will be greeted with a welcome screen. Click **Next** to proceed with the installation

{% include figure.html  
    caption="Welcome screen for installation"  
    url="/assets/img/appendix01/Install-Windows-Rstudio02.png"  
%}

#### **Step 3:Choose Installation Location:** The installer will prompt you to select an installation location. By default, RStudio will be installed in the recommended directory. If you have a specific preference, you can customize the location. Once ready, click **Next** to continue

{% include figure.html  
    caption="Choosing the installation location"  
    url="/assets/img/appendix01/Install-Windows-Rstudio03.png"  
%}

#### **Step 4:Installation in Progress:** The installation process will begin. This may take a few minutes. Wait for the installer to complete its task

{% include figure.html  
    caption="Installing RStudio"  
    url="/assets/img/appendix01/Install-Windows-Rstudio04.png"  
%}

#### **Step 5:Complete the Installation:** Once the installation is complete, the installer will notify you. Click **Finish** to exit the setup wizard. RStudio is now ready to use

{% include figure.html  
    caption="Finishing the installation process"  
    url="/assets/img/appendix01/Install-Windows-Rstudio05.png"  
%}

#### **Step 6:Open RStudio:** Click Start Menu or search for RStudio on your computer. Launch the application to start using RStudio for data analysis and statistical programming.

{% include figure.html  
    caption="Finishing the installation process"  
    url="/assets/img/appendix01/Install-Windows-Rstudio06.png"  
%}

#### **Step 7:RStudio Interface:** Once RStudio is open, you will see a window with four panes: Console, Environment, Files, and Plots. You are now ready to start working with R and RStudio

{% include figure.html  
    caption="Finishing the installation process"  
    url="/assets/img/appendix01/Install-Windows-Rstudio07.png"  
%}

### macOS Installation

Installing RStudio on macOS is a straightforward process. Follow the steps below to set up RStudio on your computer:

#### **Step 1: Download RStudio**

Visit the official RStudio download page at [posit.co/download/rstudio-desktop/](https://posit.co/download/rstudio-desktop/) and select the free Desktop version compatible with macOS.

{% include figure.html  
    caption="RStudio macOS download page"  
    url="/assets/img/appendix01/Install-Mac-Rstudio01.png"  
%}

#### **Step 2: Locate the Downloaded File**

Once the download is complete, locate the `.dmg` file in your Downloads folder or the location where your browser saves downloaded files.

{% include figure.html  
    caption="Opening the RStudio installer on macOS"  
    url="/assets/img/appendix01/Install-Mac-Rstudio02.png"  
%}

#### **Step 3: Move RStudio to Applications**

Double-click the `.dmg` file to open it. Drag and drop the RStudio icon into the **Applications** folder to install it.

{% include figure.html  
    caption="Moving RStudio to the Applications folder"  
    url="/assets/img/appendix01/Install-Mac-Rstudio03.png"  
%}

#### **Step 4: Launch RStudio from Launchpad**

Open **Launchpad**, locate RStudio, and click on the icon to start the application.

{% include figure.html  
    caption="Launching RStudio from Launchpad"  
    url="/assets/img/appendix01/Install-Mac-Rstudio04.png"  
%}

#### **Step 5: Explore the RStudio Interface**

RStudio will open, displaying its clean and user-friendly interface. You are now ready to start using RStudio for data analysis and statistical programming.

{% include figure.html  
    caption="The RStudio interface on macOS"  
    url="/assets/img/appendix01/Install-Mac-Rstudio05.png"  
%}


### Linux Ubuntu Installation

Installing RStudio on Linux Ubuntu is a straightforward process. Follow the steps below to set up RStudio on your system:

#### **Step 1: Download RStudio for Linux**

Visit the official RStudio download page at [posit.co/download/rstudio-desktop/](https://posit.co/download/rstudio-desktop/) and select the free Desktop version for Linux. Download the `.deb` package suitable for your system.

{% include figure.html  
    caption="RStudio Linux download page"  
    url="/assets/img/appendix01/Install-Linux-Rstudio01.png"  
%}

#### **Step 2: Locate the Downloaded File**

Once the download is complete, locate the `.deb` file in your Downloads folder or the directory where your browser saves downloaded files.

#### **Step 3: Open Terminal and Install Dependencies**

Before installing RStudio, ensure you have the required dependencies. Open a terminal and run the following command to update your system and install the necessary packages:

```bash
    sudo apt update
```

#### **Step 4: Install the RStudio `.deb` Package**

Navigate to the directory containing the downloaded `.deb` file (e.g., `~/Downloads`). Run the following command to install RStudio:

```bash
    sudo dpkg -i rstudio-x.yy.zz-amd64.deb
```

Replace `rstudio-x.yy.zz-amd64.deb` with the actual filename of the downloaded RStudio package.

#### **Step 5: Launch RStudio**

Once the installation is complete, you can launch RStudio from the application menu or by typing the following command in the terminal:

```bash
    rstudio
```

#### **Step 6: Explore the RStudio Interface**

RStudio will open, displaying its clean and user-friendly interface. You are now ready to start using RStudio for data analysis and statistical programming.

{% include figure.html  
    caption="The RStudio interface on Ubuntu"  
    url="/assets/img/appendix01/Install-Linux-Rstudio02.png"  
%}
