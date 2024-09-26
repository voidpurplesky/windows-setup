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

자바설치확인
- 터미널 재실행한다.
- `java` 쳤을때 자바헬프 나오면 성공, java란 명령어가 없다는 내용의 에러가 나오면 실패
자바설치성공시
```
PS C:\Users\purpl> java
사용법: java [옵션] <기본 클래스> [args...]
           (클래스 실행)
   또는  java [옵션] -jar <jar 파일> [args...]
           (jar 파일 실행)
   또는  java [옵션] -m <모듈>[/<기본 클래스>] [args...]
       java [옵션] --module <모듈>[/<기본 클래스>] [args...]
           (모듈의 기본 클래스 실행)
```
설치위치는
C:\Program Files\Amazon Corretto\jdk21.0.4_7

commant : 폴더명이 java로 시작을 안해서 한참 찾았다. 초코라떼말고 그냥 윈도우로 깔걸하고 후회했음

시스템 변수 새로 만들기
JAVA_HOME  C:\Program Files\Amazon Corretto\jdk21.0.4_7

