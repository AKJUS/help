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

- 1. Choose SFTP.
- 2. Enter the servers hostname or IP address.
- 3. Default port number is both 22 for SSH or SFTP.
- 4. Enter your username.
- 5. Don't enter any password, leave it empty.
- 6. Finally click **Advanced...**.

![session1](https://user-images.githubusercontent.com/40885610/134816867-3d7af16a-28a1-4f62-b43a-1ac6720508f6.png)

Now, make sure the setting *Sending of null SSH packets* is enabled:

![advanced1](https://user-images.githubusercontent.com/40885610/134816996-8e9db7aa-2823-47ca-b2df-28f51ce53585.png)

Set your private key which is used *instead of a password* for authentication:

![advanced2](https://user-images.githubusercontent.com/40885610/134817021-f80a9094-e4b9-408f-a37b-f8aac84d9b59.png)

You can now finally save your session and will be never asked again for any credentials:

![session2](https://user-images.githubusercontent.com/40885610/134817083-4b82ce5d-59bd-4a09-b49e-e28dea2935ff.png)


