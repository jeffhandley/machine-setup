# Windows Dev Box

*Last updated: 2023-04-04*

After spinning up a Windows Dev Box, we will get it configured to the desired state.

First, everything within the [Windows Post-Install Setup](windows-postinstall.md) applies. After finishing those instructions, the following extra steps can be taken.

1. Delete all Desktop shortcuts
1. Remove unused Visual Studio Workloads using the Visual Studio Installer
    - Workloads to remove:
        - Game development with Unity
        - Game development with C++
        - Office/SharePoint development
    - Individual Components to remove:
        - Incredibuild - Build Acceleration
        - Google Android Emulator
1. Pin Visual Studio to Start
1. Pin Visual Studio to the Taskbar
