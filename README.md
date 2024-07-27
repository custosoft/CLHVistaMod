# ConsoleLogonHook VISTA MOD
Welcome!

This project hooks onto and provides a graphical user interface for the console logon screen in Windows 10. Also, this is a Windows Vista Mod which initially release as Windows 7 style.

> [!WARNING]
> **THIS PROJECT IS IN EARLY DEVELOPMENT AND MIGHT BE UNSTABLE**
>
> You may encounter issues using a Microsoft account, however, this will work perfectly fine on local accounts.
>
> Disabling the lockscreen and the <kbd>CTRL</kbd> <kbd>Alt</kbd> <kbd>Del</kbd> logon keybinds is recommended as they're not fully implemented yet.
>
> **Knowing this, You might use this at your own risk.**
>

## How to contribute ConsoleLogonHook
The following steps explain how you can contribute to the project
1. Fork the Original ConsoleLogonHook [repository](https://github.com/wiktorwiktor12/ConsoleLogonHook)
2. Pull using git commandline, or any Git UI manager (such as Github Desktop, etc.)
3. Enjoy.
 
## Installation
> [!WARNING]
> **This will require administrator privileges to be installed.**
>

1. Copy the 2 DLL files (ConsoleLogonHook.dll and ConsoleLogonUI.dll) from [Releases](https://github.com/wiktorwiktor12/ConsoleLogonHook/releases) into %SYSTEMROOT%\System32

2. Open a CMD window as TrustedInstaller via PsExec64 or ExecTI and copy and paste the following commands:

```cmd
reg add HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsRuntime\ActivatableClassId\Windows.Internal.UI.Logon.Controller.ConsoleBlockedShutdownResolver /v DllPath /t REG_SZ /d %systemroot%\System32\ConsoleLogonHook.dll /f

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsRuntime\ActivatableClassId\Windows.Internal.UI.Logon.Controller.ConsoleLockScreen /v DllPath /t REG_SZ /d %systemroot%\System32\ConsoleLogonHook.dll /f

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsRuntime\ActivatableClassId\Windows.Internal.UI.Logon.Controller.ConsoleLogonUX /v DllPath /t REG_SZ /d %systemroot%\System32\ConsoleLogonHook.dll /f

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsRuntime\ActivatableClassId\Windows.Internal.Shell.PlatformExtensions.ConsoleCredUX /v DllPath /t REG_SZ /d %systemroot%\System32\ConsoleLogonHook.dll /f
```
or merge the regkey in the release zip as trusted installer.


3. Take ownership of the file `Windows.UI.Logon.dll` and rename it to something else. Example: `Windows.UI.Logon.dll.bak`, this is required as it will force the use of the console logon screen.


Thanks to **@wiktorwiktor12** for creating this project. 
