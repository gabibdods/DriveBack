# Uninstall OneDrive & Restore Personal Folders on Windows

### Description

- This guide explains how to safely uninstall Microsoft OneDrive and restore personal folder locations (e.g., Desktop, Documents, Pictures) to their original local paths on Windows systems.
- It includes registry edits and optional removal steps for users who no longer use OneDrive and want to cleanly revert to personal storage locations.

---

## Problem Statement

- OneDrive can alter default user folder paths to cloud-based directories, even after it’s no longer used.
- This can lead to misfiled documents, broken shortcuts, and undesired cloud syncing behavior.
- Manual correction is necessary to restore the original local folder structure.

---

## Project Goals

### Restore Default Folder Mappings

- Reconfigure key user folders (Documents, Desktop, Pictures) to point to local directories under the user's profile, eliminating OneDrive redirection.

### Remove OneDrive Application

- Provide a clean and optional method for uninstalling OneDrive from the system using native Windows tools.

---

## Tools, Materials & Resources

### Registry Editor

- Access the `HKEY_CURRENT_USER` hive to change `User Shell Folders` mappings and eliminate OneDrive folder dependencies.

### Windows Explorer / Task Manager

- Restart necessary services to apply changes immediately without rebooting.

### Command Prompt (Admin)

- Used to execute the uninstall command for OneDrive via its system-level setup binary.

---

## Design Decision

### Manual Registry Modification

- Changing folder mappings through the registry ensures persistent and precise control without relying on GUI or third-party software.

### Safe Process Sequencing

- Changes are applied incrementally, with restarts in between, to avoid system instability or data loss.

### Optional Uninstallation

- Uninstalling OneDrive is made optional to support users who may want to maintain OneDrive functionality but correct folder mappings.

---

## Features

### Targeted Folder Restoration

- Focused editing of `User Shell Folders` keys in the registry to point folders like Documents and Pictures back to local directories.

### Immediate Effect via Restart

- Restarting `Windows Explorer` ensures real-time application of the updated folder paths without a full reboot.

### One-Line OneDrive Removal

- Provides a single-line uninstall command that removes OneDrive with minimal user input.

---

## Procedure

### Steps to Remove GRUB

1. Press `Win + R` to open the Run dialog.

2. Type:
```plaintext
regedit
```
and press Enter to open the Registry Editor.

3. Navigate to:
```plaintext
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders
```

4. In the User Shell Folders key, look for entries with paths that end in:
```plaintext
\OneDrive
```
For example:
```plaintext
C:\Users\<username>\OneDrive\Documents -> C:\Users\<username>\Documents
```

5. Click OK to save each change.

6. Open Task Manager (`Ctrl + Shift + Esc`). Find and select Windows Explorer. Click Restart.

7. Open Command Prompt as an administrator. 2️ Run the following command to uninstall OneDrive:
```plaintext
%SystemRoot%\System32\OneDriveSetup.exe /uninstall
```

---

## Functional Overview

- Modify registry entries to decouple default user folders from OneDrive.
- Restart Windows Explorer to apply changes.
- Optionally uninstall OneDrive using its built-in removal command.

---

## Challenges & Solutions

### Registry Editing Risks

- Solved by clearly instructing users to back up the registry and change only specific paths under `User Shell Folders`.

### OneDrive Persistence

- Addressed by providing a full uninstall method that does not require third-party tools or OS reinstall.

---

## Lessons Learned

### Manual Overrides Improve Control

- Windows defaults can be modified safely when following structured procedures.

### Cloud Redirection Isn’t Always Ideal

- For local-first users, removing OneDrive improves performance and reduces confusion over file locations.

---

## Future Enhancements

- Add a PowerShell script to automate folder restoration and OneDrive removal.
- Include pre-checks for OneDrive paths before offering modifications.
- Add recovery instructions for mistakenly deleted or altered registry keys.
