# Uninstall OneDrive & Restore Personal Folders on Windows

🖥️ If you no longer use OneDrive and want to uninstall it and revert your default folders (like Desktop, Documents, Pictures) back to personal locations, follow this simple guide.

> ⚠️ **Important:**  
> - Modifying the Windows Registry can have unintended consequences if done incorrectly.  
> - Always back up your registry or create a system restore point first.

---

## 🔧 Step 1: Change Default Folder Paths

By default, some user folders might be pointed to OneDrive. Let’s update them to point to local folders:

1️⃣ Press `Win + R` to open the **Run** dialog.  
2️⃣ Type:

```bash
regedit
````

and press **Enter** to open the Registry Editor.

3️⃣ Navigate to:

```
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders
```

4️⃣ In the **User Shell Folders** key, look for entries with paths that end in:

```
\OneDrive
```

5️⃣ For each entry that includes `\OneDrive`, double-click it to edit the value, and **remove** `\OneDrive` from the path.

For example:

* Before: `C:\Users\<username>\OneDrive\Documents`
* After: `C:\Users\<username>\Documents`

6️⃣ Click **OK** to save each change.

---

## 🔄 Step 2: Restart Windows Explorer

For the changes to take effect immediately:

1️⃣ Open **Task Manager** (`Ctrl + Shift + Esc`).
2️⃣ Find and select **Windows Explorer**.
3️⃣ Click **Restart**.

---

## 🗑️ Step 3: Uninstall OneDrive (Optional)

If you want to completely remove OneDrive:

1️⃣ Open **Command Prompt** as an administrator.
2️⃣ Run the following command to uninstall OneDrive:

```bash
%SystemRoot%\System32\OneDriveSetup.exe /uninstall
```

---

## 💡 Additional Tips

✅ **Backup Your Data:** Before uninstalling or changing folder paths, back up any important files stored in OneDrive.

✅ **Reverting Changes:** If needed, you can re-add OneDrive by downloading it from [OneDrive’s official site](https://onedrive.live.com/about/en-us/download/).

---

## 📚 Resources

* Microsoft Docs: [OneDrive Setup Commands](https://learn.microsoft.com/en-us/onedrive/deploy-and-configure-onedrive)
* How to Backup & Restore Registry: [Windows Registry Backup](https://support.microsoft.com/en-us/windows/how-to-back-up-and-restore-the-registry-in-windows-3e5a35f7-5f3f-1f89-e1c5-cd1e81f1f8e5)

---

## 🎉 Conclusion

You’ve successfully unlinked your default folders from OneDrive and (optionally) uninstalled OneDrive itself.
If you have questions or need help restoring your files, feel free to ask!

```
Let me know if you’d like me to prepare this as a downloadable `.md` file or tweak the structure further! 🚀
```