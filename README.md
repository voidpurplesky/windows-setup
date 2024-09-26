# windows-setup
개발자를 위한 윈도우 셋업 Windows Setup for Developers

## 테스트pc
lg gram : windows 11 home
### other 보유pcs
- asus : windows 10 home
- etc

### 에디터 선택
#### (JS계열) vscode 다운로드/설치
##### 참고
https://code.visualstudio.com/docs

commant : 약간 자바스프링쪽보단 자바스크립트, nodejs, python(얘는 파이참이 더??) 등등 프론트쪽 느낌

## Chocolatey
https://chocolatey.org/install

### Requirements: (거진패스)

- .NET Framework 4.8 : 윈도우업데이트 완료니까 되있다고 생각하고 패스하려다 확인

참고 : https://learn.microsoft.com/ko-kr/dotnet/framework/migration-guide/how-to-determine-which-versions-are-installed

##### .NET Framework 4.8 설치 확인방법
- PowerShell을 사용하여 최소 버전 확인
- 설치된 경우 True 코드 반환, 설치되지 않은 경우 False 코드 반환.
###### PowerShell
```
(Get-ItemPropertyValue -LiteralPath 'HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full' -Name Release) -ge 528040
```

#### Install Chocolatey for Individual Use:
```
([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).isInRole([Security.Principal.WindowsBuiltinRole]::Administrator)
```
터미널 관리자 권한으로 실행하기 관리자:Windows PowerShell로 


```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

설치로그전체
```
Forcing web requests to allow TLS v1.2 (Required for requests to Chocolatey.org)
Getting latest version of the Chocolatey package for download.
Not using proxy.
Getting Chocolatey from https://community.chocolatey.org/api/v2/package/chocolatey/2.3.0.
Downloading https://community.chocolatey.org/api/v2/package/chocolatey/2.3.0 to C:\Users\purpl\AppData\Local\Temp\chocolatey\chocoInstall\chocolatey.zip
Not using proxy.
Extracting C:\Users\purpl\AppData\Local\Temp\chocolatey\chocoInstall\chocolatey.zip to C:\Users\purpl\AppData\Local\Temp\chocolatey\chocoInstall
Installing Chocolatey on the local machine
Creating ChocolateyInstall as an environment variable (targeting 'Machine')
  Setting ChocolateyInstall to 'C:\ProgramData\chocolatey'
WARNING: It's very likely you will need to close and reopen your shell
  before you can use choco.
Restricting write permissions to Administrators
We are setting up the Chocolatey package repository.
The packages themselves go to 'C:\ProgramData\chocolatey\lib'
  (i.e. C:\ProgramData\chocolatey\lib\yourPackageName).
A shim file for the command line goes to 'C:\ProgramData\chocolatey\bin'
  and points to an executable in 'C:\ProgramData\chocolatey\lib\yourPackageName'.

Creating Chocolatey CLI folders if they do not already exist.

chocolatey.nupkg file not installed in lib.
 Attempting to locate it from bootstrapper.
PATH environment variable does not have C:\ProgramData\chocolatey\bin in it. Adding...
WARNING: Not setting tab completion: Profile file does not exist at 'C:\Users\purpl\OneDrive\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1'.
Chocolatey CLI (choco.exe) is now ready.
You can call choco from anywhere, command line or powershell by typing choco.
Run choco /? for a list of functions.
You may need to shut down and restart powershell and/or consoles
 first prior to using choco.
Ensuring Chocolatey commands are on the path
Ensuring chocolatey.nupkg is in the lib folder
```

일부
```
WARNING: It's very likely you will need to close and reopen your shell
  before you can use choco.
```
파워쉘 재시작하라하네

초코라떼 설치 확인
```
PS C:\Users\purpl> choco
Chocolatey v2.3.0
Please run 'choco -?' or 'choco <command> -?' for help menu.
```
#### 초코라떼홈에서 패키지 검색 후 설치
https://community.chocolatey.org/packages
- jdk
여말고 java 설치에 설명 이어감
- git : chocolatey로 설치하면 마우스 오른쪽 메뉴에 추가가 안되는게 불편해서 윈도우로 받기로
추가 : 앗 윈도우로 깔아도 윈11은 마우스 오른쪽 안되는구나...ㅜ


```
choco install git.install
```
git 설치로그전체
```
PS C:\Users\purpl> choco install git.install
Chocolatey v2.3.0
Installing the following packages:
git.install
By installing, you accept licenses for the packages.
Downloading package from source 'https://community.chocolatey.org/api/v2/'
Progress: Downloading chocolatey-compatibility.extension 1.0.0... 100%

chocolatey-compatibility.extension v1.0.0 [Approved]
chocolatey-compatibility.extension package files install completed. Performing other installation steps.
 Installed/updated chocolatey-compatibility extensions.
 The install of chocolatey-compatibility.extension was successful.
  Deployed to 'C:\ProgramData\chocolatey\extensions\chocolatey-compatibility'
Downloading package from source 'https://community.chocolatey.org/api/v2/'
Progress: Downloading chocolatey-core.extension 1.4.0... 100%

chocolatey-core.extension v1.4.0 [Approved]
chocolatey-core.extension package files install completed. Performing other installation steps.
 Installed/updated chocolatey-core extensions.
 The install of chocolatey-core.extension was successful.
  Deployed to 'C:\ProgramData\chocolatey\extensions\chocolatey-core'
Downloading package from source 'https://community.chocolatey.org/api/v2/'
Progress: Downloading git.install 2.46.2... 100%

git.install v2.46.2 [Approved]
git.install package files install completed. Performing other installation steps.
The package git.install wants to run 'chocolateyInstall.ps1'.
Note: If you don't run this script, the installation will fail.
Note: To confirm automatically next time, use '-y' or consider:
choco feature enable -n allowGlobalConfirmation
Do you want to run the script?([Y]es/[A]ll - yes to all/[N]o/[P]rint): a

Using Git LFS
Installing 64-bit git.install...
git.install has been installed.
git.install installed to 'C:\Program Files\Git'
  git.install can be automatically uninstalled.
Environment Vars (like PATH) have changed. Close/reopen your shell to
 see the changes (or in powershell/cmd.exe just type `refreshenv`).
 The install of git.install was successful.
  Deployed to 'C:\Program Files\Git\'

Chocolatey installed 3/3 packages.
 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).
```
#### git
https://git-scm.com/downloads/win

###### 1. 터미널 상태확인
- Windows PowerShell (기본)
리눅스 명령어인 ls 명령어가 됨?! 

- 명령 프롬프트
ls 안됨

```
> wsl -l -o
다음은 설치할 수 있는 유효한 배포 목록입니다.
기본 배포는 ‘*’로 표시됩니다.
'wsl --install -d <Distro>'을(를) 사용하여 설치하세요.

  NAME                            FRIENDLY NAME
* Ubuntu                          Ubuntu
  Debian                          Debian GNU/Linux
  kali-linux                      Kali Linux Rolling
  Ubuntu-18.04                    Ubuntu 18.04 LTS
  Ubuntu-20.04                    Ubuntu 20.04 LTS
  Ubuntu-22.04                    Ubuntu 22.04 LTS
  Ubuntu-24.04                    Ubuntu 24.04 LTS
  OracleLinux_7_9                 Oracle Linux 7.9
  OracleLinux_8_7                 Oracle Linux 8.7
  OracleLinux_9_1                 Oracle Linux 9.1
  openSUSE-Leap-15.6              openSUSE Leap 15.6
  SUSE-Linux-Enterprise-15-SP5    SUSE Linux Enterprise 15 SP5
  SUSE-Linux-Enterprise-15-SP6    SUSE Linux Enterprise 15 SP6
  openSUSE-Tumbleweed             openSUSE Tumbleweed
```

commant : 딱히 wsl 설치 이유를 모르겠어서 보류중

##### 참고
https://nomadcoders.co/windows-setup-for-developers
https://code.visualstudio.com/docs
