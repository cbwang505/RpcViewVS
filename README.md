#### 软件介绍

RpcView是一款DcomRpc协议接口反编译工具,可以反编译运行中程序的所有DcomRpc协议接口定义.
已移植至Visual Studio 2013项目,去除rpcrt4.dll文件版本验证,支持win7x64和2008r2x64操作系统,采用qt5.6版本,已发布64位release版本

#### 运行环境

1.编译平台Visual Studio 2013

2.操作系统默认win7x64和2008r2x64,其他版本请自行编译

#### 编译教程

1. 下载qt安装包 http://iso.mirrors.ustc.edu.cn/qtproject/archive/qt/5.6/5.6.0/qt-opensource-windows-x86-msvc2013_64-5.6.0.exe
2. 下载qtvs插件 http://mirrors.ustc.edu.cn/qtproject/archive/vsaddin/qt-vsaddin-msvc2013-2.2.2.vsix
2. 打开vs菜单栏QTVSTool->QTOption添加变量msvc2013_64值C:\Qt\Qt5.6.0\5.6\msvc2013_64
2. 添加环境变量C:\Qt\Qt5.6.0\5.6\msvc2013_64\bin和C:\Qt\Qt5.6.0\Tools\QtCreator\bin
3. 编译MyRpcView项目
4. 运行Build\MyRpcView.exe

#### 使用说明

根据不同操作操作系统版本,替换项目RpcCore和RpcCoreNative的RpcInternals.h为以下文件,分别为64和32版本,并更新引用路径

```
MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore1_32bits\RpcInternals.h for Windows XP

MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore2_32bits\RpcInternals.h for Windows 7 x86

MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore2_64bits\RpcInternals.h for Windows 7 x64

MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore3_32bits\RpcInternals.h for Windows 8 x86

MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore3_64bits\RpcInternals.h for Windows 8 x64

MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore4_32bits\RpcInternals.h for Windows 8.1 and 10 x86

MyRpcView\MyRpcView\RpcViewMain\RpcCore\RpcCore4_64bits\RpcInternals.h for Windows 8.1 and 10 x64
```

#### 高级用法

1.安装windbg,添加windbg目录至环境变量

2.symchk /s srv*c:\symbol*https://msdl.microsoft.com/download/symbols c:\windows\System32\*.dll

3.symchk /s srv*c:\symbol*https://msdl.microsoft.com/download/symbols c:\windows\SysWOW64\*.dll

4.在MyRpcView菜单中选择Option->Config Symbol->输入srv*c:\symbol

5.点击任意Interface->Decompile可在反编译结果中看到可以显示正确的函数名称


![](https://i.imgur.com/ldEfgUg.png)


> 引用

[下载地址,项目里面有release发布欢迎fork](https://gitee.com/cbwang505/RpcViewMSVS)

[原git项目,作者silverf0x](https://github.com/silverf0x/RpcView)