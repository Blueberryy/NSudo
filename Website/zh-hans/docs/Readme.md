﻿# 使用方法

## 快速上手

请打开【CPU 架构】目录, 然后双击 NSudo.exe。根据提示操作即可。例如, 如果你想在
你的 Intel 或 AMD 设备上使用 64 位 NSudo, 你首先需要打开的是 x64 目录, 然后双击
NSudoG.exe。

## 命令行选项

``` batch
格式: NSudoL [ 选项与参数 ] 命令行或常用任务名

选项:

-U:[ 选项 ] 以指定用户选项创建进程。
可用选项:
    T TrustedInstaller
    S System
    C 当前用户
    E 当前用户 (提权)
    P 当前进程
    D 当前进程 (降权)
PS: 这是一个必须被包含的参数。

-P:[ 选项 ] 以指定特权选项创建进程。
可用选项:
    E 启用全部特权
    D 禁用所有特权
PS: 如果想以默认特权选项创建进程的话, 请不要包含 "-P" 参数。

-M:[ 选项 ] 以指定完整性选项创建进程。
可用选项:
    S 系统
    H 高
    M 中
    L 低
PS: 如果想以默认完整性选项创建进程的话, 请不要包含 "-M" 参数。

-Priority:[ 选项 ] 以指定进程优先级选项创建进程。
可用选项:
    Idle 低
    BelowNormal 低于正常
    Normal 正常
    AboveNormal 高于正常
    High 高
    RealTime 实时
PS: 如果想以默认进程优先级选项创建进程的话, 请不要包含 "-Priority" 参数。

-ShowWindowMode:[ 选项 ] 以指定窗口模式选项创建进程。
可用选项:
    Show 显示窗口
    Hide 隐藏窗口
    Maximize 最大化
    Minimize 最小化
PS: 如果想以默认窗口模式选项创建进程的话, 请不要包含 "-ShowWindowMode" 参数。

-Wait 令 NSudo Launcher 等待创建的进程结束后再退出。
PS: 如果不想等待, 请不要包含 "-Wait" 参数。

-CurrentDirectory:[ 目录路径 ] 设置进程的的当前目录。
PS: 如果你想用 NSudo Launcher 的当前目录, 请不要包含 "-CurrentDirectory" 参数。

-UseCurrentConsole 使用当前控制台窗口创建进程。
PS: 如果你想在新控制台窗口创建进程, 请不要包含 "-UseCurrentConsole" 参数。

-Version 显示 NSudo Launcher 版本信息。

-? 显示该内容。
-H 显示该内容。
-Help 显示该内容。

上下文菜单管理请使用 https://github.com/Thdub/NSudo_Installer。

PS:
    1. 所有的 NSudo Launcher 命令行参数不区分大小写。
    1. 可以在命令行参数中使用 "/" 或 "--" 代替 "-" 和使用 "=" 代替 ":"。例如
       "/U:T" 和 "-U=T" 是等价的。
    1. 为了保证最佳体验, NSudoLC 不支持上下文菜单。

例子:
    以TrustedInstaller权限, 启用所有特权, 完整性默认运行命令提示符
        NSudoL -U:T -P:E cmd
```

例子: 以 TrustedInstaller 权限, 启用所有特权, 完整性默认运行命令提示符

``` batch
NSudo -U:T -P:E cmd
```

从 NSudo 5.0.1708.16 开始命令行支持嵌套引号, 例如:

``` batch
NSudo -U:T cmd /c "dir "C:\Program Files" & pause"
```

## 常用列表

关于常用列表的自定义,可以使用记事本等工具编辑 NSudo.json。你可以照着示例的做法添
加你的自定义项目:

```json
{
  "ShortCutList_V2": {
    "命令提示符": "cmd",
    "PowerShell": "powershell",
    "PowerShell ISE": "powershell_ise",
    "Hosts编辑": "notepad %windir%\\System32\\Drivers\\etc\\hosts"
  }
}
```
