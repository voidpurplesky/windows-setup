관리자로 (관리자 권한없으면 권한이 없다고 설치안됨)
###### openjdk
```
choco install correttojdk
```

설치로그
```
Chocolatey v2.3.0
Installing the following packages:
correttojdk
By installing, you accept licenses for the packages.
Downloading package from source 'https://community.chocolatey.org/api/v2/'

correttojdk v21.0.4.71 [Approved]
correttojdk package files install completed. Performing other installation steps.
The package correttojdk wants to run 'chocolateyinstall.ps1'.
Note: If you don't run this script, the installation will fail.
Note: To confirm automatically next time, use '-y' or consider:
choco feature enable -n allowGlobalConfirmation
Do you want to run the script?([Y]es/[A]ll - yes to all/[N]o/[P]rint): a

Downloading correttojdk 64 bit
  from 'https://corretto.aws/downloads/resources/21.0.4.7.1/amazon-corretto-21.0.4.7.1-windows-x64.msi'
Progress: 26% - Saving 45.69 MB of 170.7 MB                                                                                                                                                                                                     Progress: 100% - Completed download of C:\Users\purpl\AppData\Local\Temp\chocolatey\correttojdk\21.0.4.71\amazon-corretto-21.0.4.7.1-windows-x64.msi (170.7 MB).
Download of amazon-corretto-21.0.4.7.1-windows-x64.msi (170.7 MB) completed.
Hashes match.
Installing correttojdk...
correttojdk has been installed.
  correttojdk may be able to be automatically uninstalled.
Environment Vars (like PATH) have changed. Close/reopen your shell to
 see the changes (or in powershell/cmd.exe just type `refreshenv`).
 The install of correttojdk was successful.
  Software installed as 'msi', install location is likely default.

Chocolatey installed 1/1 packages.
 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).
```

관리자권한없이 기본으로 들어가면 에러발생하고 ProgramData 폴더는 안보이는 폴더다.
```
System.UnauthorizedAccessException: 'C:\ProgramData\chocolatey\.chocolatey' 경로에 대한 액세스가 거부되었습니다.
```
