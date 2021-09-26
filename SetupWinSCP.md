# Setup WinSCP

WinSCP can be used for live editing, uploading and downloading files using an encrypted SSH/SFTP connection. SFTP is part of OpenSSH and easy to setup. Don't use FTP or SCP – both is either insecure or outdated.

You can download WinSCP [here](https://winscp.net/eng/download.php).

## Settings

Before you can work with WinSCP, there are many important settings you need to change.

After installation, choose **Options > Preferences** and make sure, that you use **English** as language and restart WinSCP:

![language](https://user-images.githubusercontent.com/40885610/134816417-81087135-9160-436c-b5eb-3be32d3b27af.png)

Now, make sure all of these settings are applied:

![commander](https://user-images.githubusercontent.com/40885610/134816482-6d40878b-8a10-4f3b-b6f4-6f7a1587761e.png)

Add an editor, usually Notepad++ (can be downloaded [here](https://notepad-plus-plus.org/downloads/)):

![editor](https://user-images.githubusercontent.com/40885610/134816529-3d649062-efa5-4806-8c6c-0ffb85c09ed4.png)

## Add SSH or SFTP session using Public Key Authentication

