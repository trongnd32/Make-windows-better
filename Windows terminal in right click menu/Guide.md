### Chạy các lệnh sau trong cmd:

```
echo %USERPROFILE%
echo %LOCALAPPDATA%
```

trong đó:
%USERPROFILE% → C:\Users\[userName]
%LOCALAPPDATA% → C:\Users\[userName]\AppData\Local

```
mkdir "%USERPROFILE%\AppData\Local\terminal"
```

Copy icon vào thư mục

```
%USERPROFILE%\AppData\Local\terminal
```

Lưu và chạy đoạn reg sau:

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt]
@="Windows terminal here"
"Icon"="%USERPROFILE%\\AppData\\Local\\terminal\\wt_32.ico"

[HKEY_CLASSES_ROOT\Directory\Background\shell\wt\command]
@="%LOCALAPPDATA%\\Microsoft\\WindowsApps\\wt.exe"
```

Nếu mở windows terminal trong right click menu không được, sửa trong Registry Editor:
Computer\HKEY_CLASSES_ROOT\Directory\Background\shell\wt\command

thành 
C:\Users\username\AppData\Local\Microsoft\WindowsApps\wt.exe