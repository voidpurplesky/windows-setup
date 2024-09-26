# windows-setup
개발자를 위한 윈도우 셋업 Windows Setup for Developers

테스트pc
- lg gram : windows 11 home
- asus : windows 10 home
- etc

lg gram - windows 11 home

#### 에디터 선택
##### (JS계열) vscode 다운로드/설치
###### 참고
https://code.visualstudio.com/docs

commant : 약간 자바스프링쪽보단 자바스크립트, nodejs, python(얘는 파이참이 더??) 등등 프론트쪽 느낌

Chocolatey
https://chocolatey.org/install

Requirements: 

- .NET Framework 4.8 : 윈도우업데이트 완료니까 되있다고 생각하고 패스하려다 확인

참고 : https://learn.microsoft.com/ko-kr/dotnet/framework/migration-guide/how-to-determine-which-versions-are-installed

##### .NET Framework 4.8 설치 확인방법
- PowerShell을 사용하여 최소 버전 확인
- 설치된 경우 True 코드 반환, 설치되지 않은 경우 False 코드 반환.
###### PowerShell
```
(Get-ItemPropertyValue -LiteralPath 'HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full' -Name Release) -ge 528040
```

##### Install Chocolatey for Individual Use:
```
([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).isInRole([Security.Principal.WindowsBuiltinRole]::Administrator)
```
터미널 관리자 권한으로 실행하기 관리자:Windows PowerShell로 


```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```



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
