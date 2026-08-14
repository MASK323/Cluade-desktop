# Cluade-desktop
解决工作区，沙箱，虚拟机问题
<img width="918" height="211" alt="image" src="https://github.com/user-attachments/assets/1a30f804-991f-4974-8387-381b291029e9" />
Model discovery — Gateway /v1/models returned an unexpected body. The connection test needs at least one model — add entries under Models to skip discovery, or fix the provider's model list endpoint.
200 http://127.0.0.1:10048/v1/models
想必大家使用3p的时候都遇到过这种问题
这个我今天刚解决好 在linuxdo上我看到3p模式下就会出现这个问题 
后面我用别人打包好的工作区还是会有这个问题 而且ccswitch也不会补全api  
我安装了新版为了让ccswitch补全api 让codex安装链接里版本 再清除残留 
然后导入claude-code， claude-code-vm，vm_bundles，再开启coworkvm就可以使用沙箱了
具体替换流程：
准备工作：安装cc switch 并配置供应商，配置好路由和apikey
1.先打开ClaudeDesktop-Installer.exe，安装最新版本的CluadeDesktop,当然这只是一种安装方法你也可以用官方和其他的
2.打开claude，选择打开开发者模式<img width="1080" height="720" alt="image" src="https://github.com/user-attachments/assets/aee815f6-b904-4db8-a6b1-202f86045f16" />
3.打开开发者模式，选择3p<img width="604" height="616" alt="image" src="https://github.com/user-attachments/assets/b61110d5-6b6d-4cc4-b0fd-e1831d729ed1" />
4.输入本地代理，<img width="886" height="713" alt="image" src="https://github.com/user-attachments/assets/e578b810-ee11-4657-99d6-8c576515effa" />
5.保存，退出，卸载claude
6. 双击打开Claude.msix，会提示你：安装此程序包需要管理员权限。在管理员 PowerShell 提示符窗口中，运行以下命令: Add-AppxPackage------Claude.msix
   自行复制自己显示的命令，然后管理员权限打开PowerShell，右键粘贴，运行命令，完成安装
7.让coedx检查版本，删除卸载的版本残留，这点非常重要，6,7两步骤不分先后，因为我忘了。。。只要保留了网盘里的版本和3p配置文件就没问题
7. 将网盘里的claude-code、claude-code-vm、vm_bundles拷贝到C:\Users\<用户名>\AppData\Local\Claude-3p目录中，请注意替换为你自己的用户名
管理员基本上都是这个路径C:\Users\Administrator\AppData\Local\Claude-3p
8.启动coworkvm 打开claude desktop测试沙箱，没问题即可使用
备注：
1. 遇到错误让codex查看C:\Users\<用户名>\AppData\Local\Packages\Claude_pzs8sxrjxfjjc\LocalCache\Local\Claude-3p\logs中的日志
2. 按照我的步骤，中间有问题codex会帮你完美解决的
3. 网盘链接：
https://pan.baidu.com/s/1VntkNOGr_eMsBmps8rhvlQ?pwd=txyc 
提取码：txyc 
分卷压缩包可以不用下载，只是一个压缩整体包，我没下载
