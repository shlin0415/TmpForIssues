# v0.3.1-beta2-win-run-fail*develop-win-run-fail*develop-wsl2-ubuntu-run-half-fail*doc-err
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
<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-101258.jpg" style="width:35%;" alt="description" />
<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-101303.jpg" style="width:35%;" alt="description" />
<img src="https://github.com/shlin0415/TmpForIssues/blob/main/20250914-101325.jpg" style="width:35%;" alt="description" />
