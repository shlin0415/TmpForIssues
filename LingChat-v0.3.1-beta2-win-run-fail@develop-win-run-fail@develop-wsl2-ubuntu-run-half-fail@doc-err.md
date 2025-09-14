# v0.3.1-beta2-win-run-fail@develop-win-run-fail@develop-wsl2-ubuntu-run-half-fail@doc-err
大概是以上四个情况。
先贴一下电脑情况。

## develop-wsl2-ubuntu-20250913-morning
<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-091657.jpg" style="width:30%;" alt="description" />

按时间顺序。
先是准备尝试一下在win-wsl2-ubuntu上行不行。
2025年9月13号早上七八点左右，git下LingChat develop分支，按照教程安装。
那天上午的完整历史记录
https://github.com/shlin0415/TmpForIssues/blob/main/lingchat.wsl2.history.20250913.txt
.env
https://github.com/shlin0415/TmpForIssues/blob/main/lingchat.wsl2.env
```shell
uv pip install qtpy PyQt5
sudo apt-get install python3-gi python3-gi-cairo gir1.2-gtk-3.0
uv pip install PyGObject
sudo apt update
sudo apt install -y     pkg-config     libcairo2-dev     libgirepository1.0-dev     libpango1.0-dev     libatk1.0-dev     libgtk-3-dev
uv pip install PyGObject
```
ui相关的几个包安装一直有点问题。
后面让OPEN_FRONTEND_APP=false。
可以启动，提示旧版人物，启动后无人物有背景。
想起好像有新版了，去把release的LingChat-v0.3.1-beta2.7z下载了。

## v0.3.1-beta2-win-20250913-morning-to-night
解压之后运行exe。

<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-101258.jpg" style="width:50%;" alt="description" />

<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-101303.jpg" style="width:50%;" alt="description" />

<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-101325.jpg" style="width:50%;" alt="description" />

总之就是卡在那儿了。
重启之后只开lingchat也是一样的情况，也没有报毒。
log
https://github.com/shlin0415/TmpForIssues/blob/main/Exe.LingChat-main_2025-09-13_15-10-33.log
.env
https://github.com/shlin0415/TmpForIssues/blob/main/lingchat.exe.env

后面让OPEN_FRONTEND_APP=false，但打开localhost8765时仍然是白茫茫的，没有wsl2那时的界面（此时电脑上没有其他东西显式地开着）。
其他.env项目调了调，没什么变化。

## develop-conda-20250913-afternoon-to-night
尝试了一下win上conda+uv安装lingchat develop，安装跟wsl2那时差不多。
情况跟v0.3.1-beta2-win-20250913-morning-to-night差不多。
也是卡在那儿了，打开网页白茫茫一片。
```conda-shell
(lingchat-env) (lingchat-dev) PS D:\aaa-new\setups\lingchat-dev> python -m ling_chat
[92m[INFO][0m正在加载环境变量文件: .env
[DEBUG]:                                                                             🕙[0m
加载的标签映射关系:
[DEBUG]: 0: 兴奋
......
[DEBUG]: 17: 高兴
[INFO]: √ 情绪分类模型加载正常 - 已成功加载情绪分类模型: emotion_model_18emo
[INFO]: 注册API路由...
[INFO]: 挂载静态文件服务...
[INFO]: 正在启动HTTP服务器...
[INFO]: 已根据环境变量禁用语音检查
[INFO]: ✔ 应用加载成功
█╗       ██╗ ███╗   ██╗  ██████╗      █████╗ ██╗  ██╗  █████╗  ████████╗
██║      ██║ ████╗  ██║ ██╔════╝     ██╔═══╝ ██║  ██║ ██╔══██╗ ╚══██╔══╝
██║      ██║ ██╔██╗ ██║ ██║  ███╗    ██║     ███████║ ███████║    ██║
██║      ██║ ██║╚██╗██║ ██║   ██║    ██║     ██╔══██║ ██╔══██║    ██║
███████╗ ██║ ██║ ╚████║ ╚██████╔╝     █████╗ ██║  ██║ ██║  ██║    ██║
╚══════╝ ╚═╝ ╚═╝  ╚═══╝  ╚═════╝      ╚════╝ ╚═╝  ╚═╝ ╚═╝  ╚═╝    ╚═╝
[WARNING]: [Deprecation]: 请使用 --run webview 启动前端界面
[INFO]: Started server process [3836]
[INFO]: Waiting for application startup.
[INFO]: 正在初始化数据库...
[INFO]: 正在同步游戏角色数据...
已删除不存在的角色: 可爱的小狼娘 (ID: 1)
[INFO]: Application startup complete.
[INFO]: Uvicorn running on http://0.0.0.0:8765 (Press CTRL+C to quit)
[INFO]: 127.0.0.1:7819 - "GET / HTTP/1.1" 200
[INFO]: 127.0.0.1:7819 - "GET / HTTP/1.1" 200
[INFO]: 127.0.0.1:7819 - "GET /assets/index-Dn8qAaVr.js HTTP/1.1" 200
[INFO]: 127.0.0.1:7819 - "GET /assets/index-Dn8qAaVr.js HTTP/1.1" 200
[INFO]: 127.0.0.1:7825 - "GET /assets/index-CvUGl3Rf.css HTTP/1.1" 200
[INFO]: 127.0.0.1:7825 - "GET /assets/index-CvUGl3Rf.css HTTP/1.1" 200
[INFO]: 127.0.0.1:7819 - "GET /vite.svg HTTP/1.1" 200
[INFO]: 127.0.0.1:7819 - "GET /vite.svg HTTP/1.1" 200
[INFO]: 127.0.0.1:7948 - "GET / HTTP/1.1" 200
[INFO]: 127.0.0.1:7948 - "GET / HTTP/1.1" 200
[INFO]: 127.0.0.1:7948 - "GET /assets/index-Dn8qAaVr.js HTTP/1.1" 200
[INFO]: 127.0.0.1:7948 - "GET /assets/index-Dn8qAaVr.js HTTP/1.1" 200
[INFO]: 127.0.0.1:7948 - "GET /assets/index-CvUGl3Rf.css HTTP/1.1" 200
[INFO]: 127.0.0.1:7948 - "GET /assets/index-CvUGl3Rf.css HTTP/1.1" 200
[INFO]: 接收到中断信号，正在关闭程序...
[INFO]: 已删除临时文件
[INFO]: 程序已退出
[INFO]: 接收到中断信号，正在关闭程序...
[INFO]: 已删除临时文件
```

## develop-wsl2-ubuntu-20250913-night
突然想起来新版人物有了，wsl2也许可以了。
接下来出现的问题不知道是不是有wsl2自身的原因。
但wsl2是目前运行进度走的最远的，好怪啊。
把带新版人物的整个data文件夹从v0.3.1-beta2-win粘贴了过去。
依旧是OPEN_FRONTEND_APP=false启动。
```wsl2-shell
(lingchat-dev) (lingchat-env) root@zzz:~/lingchat-dev# python -m ling_chat
[INFO]正在加载环境变量文件: .env
[INFO]: √ 情绪分类模型加载正常 - 已成功加载情绪分类模型: emotion_model_18emo
[INFO]: 注册API路由...
[INFO]: 挂载静态文件服务...
[INFO]: 正在启动HTTP服务器...
[INFO]: 已根据环境变量禁用语音检查
[INFO]: 已根据环境变量禁用前端界面
[INFO]: Started server process [1295]
[INFO]: Waiting for application startup.
[INFO]: 正在初始化数据库...
[INFO]: 正在同步游戏角色数据...
[INFO]: Application startup complete.
[INFO]: Uvicorn running on http://0.0.0.0:8765 (Press CTRL+C to quit)
[INFO]: ✔ 应用加载成功
█╗       ██╗ ███╗   ██╗  ██████╗      █████╗ ██╗  ██╗  █████╗  ████████╗
██║      ██║ ████╗  ██║ ██╔════╝     ██╔═══╝ ██║  ██║ ██╔══██╗ ╚══██╔══╝
██║      ██║ ██╔██╗ ██║ ██║  ███╗    ██║     ███████║ ███████║    ██║
██║      ██║ ██║╚██╗██║ ██║   ██║    ██║     ██╔══██║ ██╔══██║    ██║
███████╗ ██║ ██║ ╚████║ ╚██████╔╝     █████╗ ██║  ██║ ██║  ██║    ██║
╚══════╝ ╚═╝ ╚═╝  ╚═══╝  ╚═════╝      ╚════╝ ╚═╝  ╚═╝ ╚═╝  ╚═╝    ╚═╝
```
这次打开[http://localhost:8765/]可以看到了。

<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-104246.jpg" style="width:30%;" alt="description" />
