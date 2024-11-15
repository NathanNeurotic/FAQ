### A Simple Guide to .PSU Files for PS2 Homebrew Beginners

#### What is a .PSU?
A `.psu` file is like a **.zip file**, but instead of extracting to your computer, it extracts a folder and its files directly to a PS2 memory card using the **"psupaste"** function in wLaunchELF/uLaunchELF.

#### Why Use .PSU Files?
- **Convenience**: Packages applications with their settings, icons, and other required files, ready to go with minimal effort.
- **Easy Installation**: A one-step process to get your apps fully set up and running.
- **Built-in Management**: Manage your applications straight from the PS2 Memory Card Browser, including copying and deleting.
---
### How to Install .PSU Files

1. **Save the `.psu` files you want to install onto a USB storage device.**

2. **Prepare Your PS2**
   - Plug the USB into your PS2.
   - Launch **wLaunchELF** or **uLaunchELF** (any version works).

3. **Copy the .PSU Files**
   - Open the **File Manager** in wLaunchELF.
   - Navigate to `mass:/` (this is your USB device).
   - Find the `.psu` files you downloaded.
   - Highlight the one(s) you want to install and press **R1**, then select **Copy**.

4. **Paste with PSUPaste**
   - Press **Triangle** to navigate back until you can access `mc0:/` or `mc1:/` (memory card in slot 1 or 2).
   - Go into `mc0:/` or `mc1:/` and press **R1**, then select **PSUPaste**.
   - Ensure you are pasting to the root of the memory card (not inside another folder).
   - Once the process finishes, the application is installed!
---
### After Installation

#### For OPL Users:
- On recent OPL versions, your apps will automatically show up in the **Apps** section.
- To save space on your memory card, move the apps to `mass:/APPS/` (on USB) after extraction.  
  Example: `mass:/APPS/APP_OPL/OPL.ELF` and its related files.

#### For FMCB Users:
1. Open the **FMCB Configurator**:
   - From the FMCB menu, choose **FMCB Configurator**.
   - Alternatively, launch `FMCB_CFG.ELF` from `mc0:/SYS-CONF/` or `mc1:/SYS-CONF/` in wLaunchELF.

2. Map the Application:
   - Choose your button layout.
   - Scroll down to **Configure OSDSYS Settings...**.
   - Go to Configure Item 1, and scroll to the right with the d-pad.
   - Find an empty slot (e.g., Configure Item 1 -> 2 -> 3 etc) and name it/them (e.g., `OPL`).
   - Highlight **Path1**, press **Square**, and navigate to the `.ELF` file of your app (e.g., `mc0:/APP_OPL/OPL.ELF`).

3. Save and Exit:
   - Select Return, then Select Return Again.
   - Save changes to **MC0**, **MC1**, or **MASS**. (or all 3) dependent upon your setup.
   - Exit the Configurator and enjoy your new application!
---
### Special Instructions for Certain .PSU Files

#### Subfolder Warning:
The following `.psu` files require subfolders that require extra care during installation. Do not proceed with them on memory card if you do not know what you are doing, or do not understand the process.
- `!RTE_ATHENAENV.PSU`
- `!RTE_ENCELADUS.PSU`
- `!RTE_NEUTRINO.PSU`

**How to Install Subfolder Dependent .PSU Files:**
1. **Initial Installation**: Copy and PSUPaste the `.psu` file as usual (e.g., `RTE_ATHENAENV.PSU`).
   - This creates `mc0:/RTE_ATHENAENV/` with its base contents.
2. **Install Additional Files**:
   - Download the remaining  `.psu` files from the matching folder on the downloads page. (e.g., `RTE_ATHENAENV/store.psu`).
   - PSUPaste these additional files **one by one** into a matching parent folder. (e.g., `mc0:/RTE_ATHENAENV/store/` and its contents is created by psupasting `store.psu` inside `mc0:/RTE_ATHENAENV/`).

**Important**: Installing subfolders or multiple subfolder `.psu` files can corrupt your memory card. They also must be deleted one by one to prevent corruption if deleting. (`mc0:/RTE_ATHENAENV/store/icons/` would be first, `mc0:/RTE_ATHENAENV` would be last)

#### SMS and APP_SMS:
- These two apps work best together.  
  - **APP_SMS**: The application itself.
  - **SMS**: Stores settings for APP_SMS (this location is hard-coded)