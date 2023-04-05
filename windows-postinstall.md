# Windows Post-Install Setup

*Last updated: 2023-04-04*

After Windows is installed, it needs a couple hours of maintenance to make it comfortable and usable. These setup instructions do not include the full list of apps that I often install, but they include all of the steps to get the machine to my baseline state. Included in the baseline are:

1. Removing Windows bloatware and reducing Start/Taskbar noise
2. Getting OneDrive to sync my "Everywhere" apps and settings
3. Setting up Edge profiles and removing all of its clutter
4. Installing 1Password with the desired configuration
5. Preparing the fundamentals: Terminal, PowerShell, Sublime Text, and Sublime Merge

It's a bit of a circuitous route to get to the desired state, but here we go...

## OneDrive

I use OneDrive to store some portable app installations and some app settings/scripts. That content is stored in my personal OneDrive account, which means every machine I set up needs to have OneDrive set up to sync my "Everywhere" folder from that account. Unfortunately, OneDrive doesn't let you choose the folders to sync _during_ the account setup, which means it has to fully sync the account once before we undo a bunch of its efforts. The initial sync is time-consuming, and we need those "Everywhere" files soon, so we'll start with this step.

To fire it off, simply add the personal Microsoft Account to OneDrive and let it get going. We'll come back to it later.

## Removing Windows Bloatware and Reducing Start/Taskbar noise

### Taskbar Settings

- **Search: _Hide_**
- **Task View: _Off_**
- **Widgets: _Off_**
- **Chat: _Off_**

### Unpin from Taskbar

- Microsoft Office
- Microsoft Store

### Notification Settings

- **Do not disturb: _Off_**
- **Notifications: _Off_**

### Uninstall Bloatware from Start

- Solitaire _(this is a real shame)_
- WhatsApp
- Spotify
- TikTok
- Xbox
- ClipChamp
- Prime Video
- ESPN
- Instagram
- Messenger
- Movies & TV
- Tips

### Start Settings

- **Layout: _More pins_**
- **Show recently opened items in Start, Jump Lists, and File Explorer: _Off_**

### Notification Area

- Move all hidden notification area icons into the notification area

### Uninstall Bloatware from Installed Apps

- Mail and Calendar
- Microsoft News
- Microsoft To Do
- Notepad
- Paint
- Sticky Notes
- Weather
- Xbox Live

The following apps may also be preinstalled and can be uninstalled from a work machine:

- Epic Games Launcher
- Epic Online Services

## File Explorer Creature Comforts

We'll first set online file folders to have ideal column widths.

1. Navigate to the OneDrive root folder
1. Right-click on a column header and choose _More..._
1. Set the following column widths:
    - **Name: _400_**
    - **Status: _60_**
    - **Date modified: _160_**
    - **Type: _160_**
    - **Size: _120_**
1. Apply these settings and close the dialog
1. Resize the window so these columns fit
1. Open the **Options** dialog **View** tab
1. Click _Apply to Folders_ and confirm

Then we'll configure local file folders to have their ideal column widths.

1. Navigate to the local _Downloads_ folder
1. Right-click on a column header and choose _More..._
1. Set the following column widths:
    - **Name: _460_**
    - **Date modified: _160_**
    - **Type: _160_**
    - **Size: _120_**
1. Apply these settings and close the dialog
1. Open the **Options** dialog **View** tab
1. Click _Apply to Folders_ and confirm

With the **Options** dialog **View** tab still open, we'll configure the remainder of the desired view settings that apply globally.

- **Display file icon on thumbnails: _On_**
- **Display file size information in folder tips: _On_**
- **Display the full path in the title bar: _On_**
- **Hide extensions for known file types: _Off_**
- **Show drive letters: _On_**
- **Show sync provider notifications: _On_**
- **Use check boxes to select items: _On_**
- **Use Sharing Wizard: _Off_**
- **Navigation pane**
    - **Always show availability status: _On_**
    - **Expand to open folder: _On_**
    - **Show all folders: _On_**
    - **Show libraries: _On_**
    - **Show Network: _On_**
    - **Show This PC: _On_**

Apply these settings. Then on the **General** tab, apply these **Privacy** settings and click OK:

- **Show recently used files: _Off_**
- **Show frequently used folders: _Off_**
- **Show files from Office.com: _Off_**

## OneDrive - Step 2

By this point, the initial sync should have completed and the folders selected for sync can be updated. On a baseline setup, only two items need to be selected

- Everywhere
- Personal Vault (OneDrive requires this, even if it's not used)

Beyond these, include other folders appropriate for the device. After updating these settings, restart the machine; otherwise OneDrive doesn't seem to start removing the deselected folders as rapidly. After the reboot, we can proceed with some other steps while OneDrive progresses.

## Edge - Default Profile

On the first launch of Edge, it'll confirm the connection for the Microsoft account used to sign in to Windows. It'll ask about importing data from Chrome, which can be skipped. After the initial sync from Microsoft Account settings, extensions will be installed and their related tabs will be launched--including Adblock Plus and 1Password. Those tabs can be closed and the following steps can be taken to configure Edge to be as free of clutter as possible.

In each of these categories, there are some settings listed out of order. That's because other settings will disable them, so we move them up to be able to turn them off before they get disabled.

### New Tab Page Settings

- **Layout: _Focused_ (work) or _Inspirational_ (personal)**
- **Show sponsored links: _Off_**
- **Quick links: _Off_**
- **Show greeting: _Off_**
- **Content: _Content off_**

### Sidebar Settings

- **Personalize my top sites in customize sidebar: _Off_**
- **Allow sidebar apps to show notifications: _Off_**
- **Always show sidebar: _Off_**
- **App specific settings: Discover**
    - **Automatically show related content in Discover: _Off_**
    - **Page context: _Off_**
    - **Show Discover: _Off_**

### Other Settings

All other settings that need to be updated show up under the search results for **"show"**. Some of these settings might not show up under a work profile, and some might not show up until Edge completes its first update. It's generally a good idea to check all of these settings after a notable Edge update (and add any new annoyances to the list of features to disable).

- **Use a web service to help resolve navigation errors: _Off_**
- **Suggest similar sites when a website can't be found: _Off_**
- **Save time and money with Shopping in Microsoft Edge: _Off_**
- **Show Collections and follow content creators in Microsoft Edge: _Off_**
- **Get notified when creators you follow post new content: _Off_**
- **Show suggestions to follow creators in Microsoft Edge: _Off_**
- **Show opportunities to support causes and nonprofits you care about: _Off_**
- **Get notifications of related things you can explore with Discover: _Off_**
- **Enhance images in Microsoft Edge: _Off_**
- **Suggest group names when creating a new tab group: _Off_**
- **Address Bar and Search**
    - **Show me search and site suggestions using my typed characters: _Off_**
    - **Show me suggestions from history, favorites and other data on this device using my typed characters: _Off_**
    - **Search engine used in the address bar: _DuckDuckGo_**
    - **Search on new tabs uses search box or address bar: Address _bar_**
- **Show tab actions menu: _Off_**
- **Show tab preview on hover: _On_**
- **Show Workspaces: _Off_**
- **Show favorites bar: Only on new _tabs_**
- **Home Button: _On_**
- **Forward button: Always _show_**
- **Extensions button: Never _show_**
- **Favorites, Collections, History, Downloads, Performance, Math Solver, Citations: _Off_**
- **Web capture, Share, Feedback: _Off_**
- **Show smart actions: _Off_**
- **Hover _menu_:**
    - **Show hover menu on image hover: _Off_**
    - **Show visual Search in context menu: _Off_**
- **Show mini menu when selecting text: _Off_**

Within the _All Permissions_ section:

- **Location: _Ask first_ or _Off_**, depending on the device
- **Camera: _Ask first_ or _Off_**, depending on the device
- **Microphone: _Ask first_ or _Off_**, depending on the device
- **Motion or light sensors: _Off_**
- **Notifications: _Off_**
- **Protocol handlers: _Off_**
- **MIDI devices: _Off_**
- **USB devices: _Off_**
- **Serial ports: _Off_**
- **File editing: _Off_**
- **Payment handlers: _Off_**
- **Virtual reality: _Off_**
- **Augmented reality: _Off_**

And the final set of settings:

- **Open Office files in the browser: _Off_**
- **Show downloads menu when a download starts: _On_**
- **Show a high visibility outline around the area of focus on the page: _On_**

## Edge - Secondary Profile

Use the profile menu to add another profile to Edge, adding either the work or personal profile by signing in to sync this profile's data.

Once the profile is added and its initial sync completes, all of the above settings will need to be configured into the secondary profile as well.

## 1Password

With Edge now in a working state, it's time to download and configure 1Password. Edge will have launched a 1Password extension tab requesting a sign-in, but that was skipped. Instead, the desktop app will get installed and configured to integrate with the browser extension.

### Desktop App Installation

1. Visit https://1password.com/downloads to download the installer
1. Click to Sign In
1. In the iOS 1Password app:
    a. From the Home or root Items screen, tap the vaults/accounts icon in the upper-left
    b. Tap 'Set Up Another Device...'
    c. Tap 'Setup Code' at the top
1. Click 'Scan Setup Code'
1. Scan the code using the webcam
1. Enter the master password and click Sign In
1. Tap through the other setup steps (that are geared toward new users)
    - There's no need to install the browser extension, because it's already installed

### Desktop App Settings

- **General**
    - **Keep 1Password in the notification area: _On_**
        - **Move the icon into the notification area**
    - **Format secure notes using Markdown: _On_**
    - **Save new items in: _Personal_**
    - **Keyboard Shortcuts**
        - **Show 1Password: _`Meta + Shift + \`_**
        - **Show Quick Access: _`Alt + Meta + \`_**
        - **Lock 1Password: _None_**
        - **Autofill: _`Ctrl + \`_**
- **Appearance**
    - **Theme: _Match system_**
    - **Use device accent color: _On_**
    - **Density: _Compact_**
    - **Always Show in Sidebar**
        - **Categories: _On_**
        - **Tags: _Off_**
- **Security**
    - **Unlock using Windows Hello: _On (if available)_**
        - **Show Windows Hello prompt automatically: _On_**
        - **Use the Trusted Platform Module with Windows Hello: _Off_**
    - **Lock 1Password when computer locks: _On_**
    - **Lock after the system is idle for: _Choose a setting appropriate for this device_**
    - **Clipboard**
        - **Remove copied information and authentication codes after 90 seconds: _On_**
- **Privacy**
    - **Show app and website icons: _On_**
    - **Watchtower**
        - **Check for compromised websites: _On_**
        - **Check for vulnerable passwords: _Off_**
        - **Check for two-factor authentication: _On_**
- **Browser**
    - **Connect with 1Password in the browser: _On_**
- **Advanced**
    - **Install updates automatically: _On_**

### Browser Extension Settings

Launch the browser, go into **Settings > Extensions**, and make the 1Password icon visible and then click it.

- Click the hamburger menu (it probably has a notification indicator)
    - In the notifications, dismiss the 'Would you like to turn on Watchtower notifications' item
- Click the hamburger menu again and choose _Settings_
    - **Save new items in: _Personal_**
    - **Make 1Password the default password manager: _On_**
    - **Show app and website icons: _On_**
    - **Integrate with 1Password app: _On_**
    - **Autofill**
        - **Offer to fill and save passwords: _On_**
        - **Show autofill menu on field focus: _Off_**
        - **Log in automatically using a "sign in with" provider: _Off_**
        - **Offer to save new provider sign-ins: _Off_**
    - **Allow 1Password to show system notifications: _On_**
    - **Accounts & Vaults**
        - Select the vaults appropriate for this device

Close the tab; the settings were automatically saved.

## OneDrive -- How Ya Doin' Over There?

Check out the OneDrive sync status. Is it progressing? Is it showing conflicts that need to be resolved? At this point, it's probably yelling at us about folders that we tried un-syncing, with some confused state message about how the folders already exist. Ugh. Let's help it out.

### Deleting Un-Synced Folders

Open the OneDrive folder in File Explorer, and _permanently delete_ (`Shift+Delete`) the folders that aren't supposed to be syncing to the machine. The gesture of _permanently deleting_ is important as it's a quicker path than moving the files to the Recycle Bin. Even with the _permanently delete_ gesture though, the process of deleting the files will take 10-30 minutes and there may be some errors that require skipping the operations. The gesture for permanently deleting the folders may need to be done a few times.

Once the syncing is complete and the folders have been deleted, the Recycle Bin will need to be emptied, because OneDrive's own sync process seems to have moved files into the Recycle Bin.

### Making Apps and Settings Always Available

Within the _Everywhere_ folder we are syncing from OneDrive, there are two folders that need to be configured to always be available on the device:

- **_Everywhere\Apps_**
- **_Everywhere\AppSettings_**

This is accomplished by right-clicking on each of those folders and choosing _Always keep on this device_.

## Edge - Profile Icons and Custom Search Engines

There are two categories of settings that we can't or don't use Edge's settings UI to configure: Profile Icons and Custom Search Engines.

### Profile Icons

When Edge is configured with multiple profiles, each profile gets its own Start/Taskbar icon and there's an overlay of the account's profile picture on the icon. When those profiles _have the same profile picture_, they cannot be distinguished from one another. Worse yet, Edge doesn't give access to control the profile picture that it uses without also changing the profile picture associated with the Microsoft Account. But we can sidestep its behavior and just overwrite the image files.

Within the OneDrive _Everywhere\AppSettings\Edge_ folder, there is a sub-folder for _Edge-Work_ and _Edge-Personal_. Each of those contains two files that need to be copied into Edge's user data folder.

- _Edge Profile Picture.png_ (used inside Edge for the Profile picture button)
- _Edge Profile.ico_ (the Edge application icon with the profile picture overlaid on it)

For each of those profiles, copy the image files to the clipboard and navigate to Edge's user data folder using the _Everywhere\AppSettings\Edge-Data_ shortcut. Then paste the images into the right profile folder.

- The initial profile folder for the account used to sign into Windows is _Default_
- The secondary profile is _Profile 1_ (unless any mistakes were made during setup, then perhaps _Profile 2_, etc.)

After these are copied into Edge's user data folder, launch Edge for each profile and pin it to the Taskbar. The icons may be stale for several launches of Edge, or perhaps even for a couple of reboots.

### Custom Search Engines

Edge does not sync configured custom search engines with its settings (even though Chrome does). But the search engines are stored in a SQLite database and we can use some tooling to maintain those settings with SQL statements and wrapper scripts.

In the _Everywhere\AppSettings_ folders for both _Edge-Work_ and _Edge-Personal_, there is an `Import-Search-Engines-*.cmd` file; simply double-click it. This script uses a portable app within the _Everywhere\AppSettings_ folder to:

1. Kill any running Edge processes
1. Find the right Edge user data folder for the profile
1. Connect to the SQLite database for that profile
1. Delete all existing custom search engines
1. Insert the desired custom search engines

## Fundamental Apps

### Terminal

Pin Terminal to Start and the Taskbar, and then launch it. Terminal starts off with the legacy "Windows PowerShell", but we want the modern "PowerShell" instead. Run `winget install --id Microsoft.PowerShell` to install it.

After PowerShell is installed, open Terminal's Settings to configure it for the desired experience.

- **Startup**
    - **Default terminal application: _Windows Terminal_**
    - **Default Profile: _PowerShell_**
    - **Launch size: _140 x 30_**
- **Profiles > PowerShell**
    - **Command line: _Add ` -NoLogo` to the end_**
    - **Starting directory: _`%USERPROFILE%\git`_** (note: go create this folder)
- **Profiles > Windows PowerShell**
    - **Hide profile from dropdown: _On_**

Save the settings and then use the **Open JSON file** button for fine-grained control of some more settings. This gesture will likely require an app selection for how to open the JSON file. Use **Choose an App on your PC** and then navigate to OneDrive's *`Everywhere\Apps\Sublime Text\sublime_text.exe`* file.

Within Terminal's settings JSON file, reorder the profiles to the following:

1. PowerShell
1. Command Prompt
1. Developer PowerShell for VS 2022
1. Developer Command Prompt for VS 2022
1. Azure Cloud Shell
1. Windows PowerShell

Then restart Terminal again, which should launch a PowerShell console. A PowerShell profile is saved in OneDrive such that a profile is used across all machines. After first load, the profile should emit a message that [Starship](https://starship.rs) is not installed; there will be an instruction for how to install it. After installing Starship, close that Terminal tab and open a new one.

### Sublime Text

We've already used Sublime Text above; it's available as a [portable installation](https://www.sublimetext.com/download) from OneDrive's *Everywhere\Apps\Sublime Text* folder. While Sublime Text is open, pin it to the Taskbar and to Start.

With the portable install, all settings and installed packages should sync from OneDrive. It's likely that the first couple of launches will try reopening the previously opened file/session, but this should be temporary. The PowerShell profile loaded from OneDrive also ensures `subl` is available on PATH.

The packages that should be installed are:

- Package Control
- AppendComma
- AppendNewline
- AppendSemiColon
- Chain of Command
- F#
- Indent XML
- MSBuild
- NuGet
- PowerShell
- Pretty JSON
- Razor C# Syntax
- SingleTrailingNewLine (applied to every syntax)
- Surround
- SurroundWith
- TOML
- VBDotNet

### Sublime Merge

Sublime Merge is available as a [portable installation](https://www.sublimemerge.com/download) from OneDrive's *Everywhere\Apps\Sublime Merge* folder. Additionally, the PowerShell profile that is already in place ensures it's on path as `smerge`. Launch if from a Terminal and pin it to Start and the Taskbar.
