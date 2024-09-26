https://git-scm.com/downloads/win
https://bangul2.tistory.com/21
https://operavps.com/docs/install-git-on-windows/

설치버전 2.46.2
### 설치옵션
- Select Components : (변동있음) daily update 뺴고 다선택함
- Choosing the default editor used by Git : (변동있음) Use Visual Studio Code
- Adjusting your PATH environment : (그대로) Recommended - 3rd party software
- Chossing HTTPS transport backend : (그대로) OpenSSL library
- Configuring the line ending conversins : (그대로) 1. Windows-style
- Configuring the terminal emulator to use with Git Bash : (그대로) 1. MinTTY
- Choosing the default behavior of `git pull` : (그대로) fast-forward
- credential helper : (그대로) 1. Credential Manager
- extra options : (그대로) V Enable file system caching
- experimental options : (그대로) 2020년 블로그에 이기능에 버그있다고 하지말랬는데 지금은 2024년..

  
```
git config --global user.name "Your Name"
git config --global user.email your@email.com
```

```
git config --global --list
```

