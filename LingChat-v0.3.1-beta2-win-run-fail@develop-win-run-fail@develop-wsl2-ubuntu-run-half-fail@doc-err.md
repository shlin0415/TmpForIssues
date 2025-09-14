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

本来以为是不是ok了，虽然wsl2很卡。
没想到新的问题出现了。
第一个是测试角色音量wav和气泡音量wav没声音，但播放背景音乐mp3，音响拉到最大是有声音的。
第二个是通用网络大模型流式请求失败，测试输入hello之后没后续了。
```wsl2-shell
[INFO]: 127.0.0.1:41860 - "GET / HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET / HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /assets/index-Dn8qAaVr.js HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /assets/index-Dn8qAaVr.js HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /assets/index-CvUGl3Rf.css HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /assets/index-CvUGl3Rf.css HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /%40/assets/images/default_bg.jpg HTTP/1.1" 404
[INFO]: 127.0.0.1:41860 - "GET /%40/assets/images/default_bg.jpg HTTP/1.1" 404
[INFO]: 127.0.0.1:41860 - "GET /api/settings/config HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /api/settings/config HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /assets/LingChatLogo-DrtNjGh5.png HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /assets/LingChatLogo-DrtNjGh5.png HTTP/1.1" 200
[INFO]: 当前RAG窗口大小是：5
[INFO]: 正在初始化RAG系统...
[INFO]: 正在为新角色 (ID: 0) 初始化RAG记忆库...
[ERROR]: 切换RAG角色 (ID: 0) 时出错: RAGSystem必须使用一个有效的character_id进行初始化。
[WARNING]: RAG系统初始化失败或禁用
[INFO]: 初始化LLM webllm 提供商中...
[INFO]: 创建通用联网大模型服务提供商
[INFO]: 通用网络大模型初始化完毕！
[INFO]: 初始化翻译模型 webllm 提供商中...
[INFO]: 创建通用联网大模型服务提供商
[INFO]: 通用网络大模型初始化完毕！
[INFO]: 【视觉识别】你没有改过VD_API_KEY，无法进行图像识别哦！
[WARNING]: 你的环境变量中未设置TTS类型（或是设置错误），将使用角色卡的默认语音合成器！
[INFO]: 检测到角色切换，正在为角色 (ID: 2) 准备长期记忆...
[INFO]: 正在为新角色 (ID: 2) 初始化RAG记忆库...
[INFO]: RAG: 准备从本地路径加载嵌入模型: /root/lingchat-dev/ling_chat/third_party/memory_rag_models/all-MiniLM-L6-v2
[ERROR]: 本地模型路径不存在或不是文件夹: /root/lingchat-dev/ling_chat/third_party/memory_rag_models/all-MiniLM-L6-v2
[ERROR]: 请确保模型已下载。
[ERROR]: 您可以运行 '/root/lingchat-dev/ling_chat/third_party/downloading_RAG_model' 脚本来下载模型。
[ERROR]: 为角色 (ID: 2) 初始化RAG记忆库失败。
[INFO]: 日程功能已通过环境变量禁用
[INFO]: 正在/root/lingchat-dev/ling_chat/data/game_data/scripts中寻找剧本
[INFO]: 找到剧本文件一只简简单单的剧情
[INFO]: 🧠🧠🧠 ai_service 初始化
[INFO]: 127.0.0.1:41860 - "GET /api/v1/chat/info/init?user_id=1 HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /api/v1/chat/info/init?user_id=1 HTTP/1.1" 200
[INFO]: 127.0.0.1:41874 - "GET /api/v1/chat/history/list?user_id=1&page=1&page_size=10 HTTP/1.1" 200
[INFO]: 127.0.0.1:41874 - "GET /api/v1/chat/history/list?user_id=1&page=1&page_size=10 HTTP/1.1" 200
[INFO]: 127.0.0.1:41884 - "GET /api/v1/chat/back-music/list HTTP/1.1" 200
[INFO]: 127.0.0.1:41884 - "GET /api/v1/chat/back-music/list HTTP/1.1" 200
[INFO]: 127.0.0.1:41900 - "GET /api/v1/chat/character/get_all_characters HTTP/1.1" 200
[INFO]: 127.0.0.1:41900 - "GET /api/v1/chat/character/get_all_characters HTTP/1.1" 200
[INFO]: 127.0.0.1:41912 - "GET /api/v1/chat/background/list HTTP/1.1" 200
[INFO]: 127.0.0.1:41912 - "GET /api/v1/chat/background/list HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /api/v1/chat/info/init?user_id=1 HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /api/v1/chat/info/init?user_id=1 HTTP/1.1" 200
[INFO]: 127.0.0.1:41920 - "GET /api/v1/chat/character/get_avatar/%E6%AD%A3%E5%B8%B8.png?t=1757817663678 HTTP/1.1" 200
[INFO]: 127.0.0.1:41920 - "GET /api/v1/chat/character/get_avatar/%E6%AD%A3%E5%B8%B8.png?t=1757817663678 HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /api/v1/chat/character/character_file/%E8%AF%BA%E4%B8%80%E9%92%A6%E7%81%B5/avatar/%E5%A4%B4%E5%83%8F.png HTTP/1.1" 200
[INFO]: 127.0.0.1:41860 - "GET /api/v1/chat/character/character_file/%E8%AF%BA%E4%B8%80%E9%92%A6%E7%81%B5/avatar/%E5%A4%B4%E5%83%8F.png HTTP/1.1" 200
[INFO]: 127.0.0.1:41912 - "GET /api/v1/chat/background/background_file/%E5%A4%9C%E6%99%9A.jpg HTTP/1.1" 200
[INFO]: 127.0.0.1:41912 - "GET /api/v1/chat/background/background_file/%E5%A4%9C%E6%99%9A.jpg HTTP/1.1" 200
[INFO]: 127.0.0.1:41900 - "GET /api/v1/chat/background/background_file/%E7%99%BD%E5%A4%A9.jpeg HTTP/1.1" 200
[INFO]: 127.0.0.1:41900 - "GET /api/v1/chat/background/background_file/%E7%99%BD%E5%A4%A9.jpeg HTTP/1.1" 200
[INFO]: 127.0.0.1:41884 - "GET /api/v1/chat/character/get_avatar/%E6%AD%A3%E5%B8%B8.png?t=1757817663690 HTTP/1.1" 200
[INFO]: 127.0.0.1:41884 - "GET /api/v1/chat/character/get_avatar/%E6%AD%A3%E5%B8%B8.png?t=1757817663690 HTTP/1.1" 200
[INFO]: 127.0.0.1:56614 - "WebSocket /ws" [accepted]
[INFO]: connection open
[INFO]: 127.0.0.1:44156 - "GET /audio_effects/%E8%A7%92%E8%89%B2%E9%9F%B3%E9%87%8F%E6%B5%8B%E8%AF%95.wav HTTP/1.1" 206
[INFO]: 127.0.0.1:44156 - "GET /audio_effects/%E8%A7%92%E8%89%B2%E9%9F%B3%E9%87%8F%E6%B5%8B%E8%AF%95.wav HTTP/1.1" 206
[INFO]: 127.0.0.1:44172 - "GET /audio_effects/%E7%96%91%E9%97%AE.wav HTTP/1.1" 206
[INFO]: 127.0.0.1:44172 - "GET /audio_effects/%E7%96%91%E9%97%AE.wav HTTP/1.1" 206
[INFO]: 127.0.0.1:33976 - "GET /api/v1/chat/back-music/music_file/%E5%A4%9C%E6%99%9A%E9%9F%B3%E6%95%88.mp3 HTTP/1.1" 206
[INFO]: 127.0.0.1:33976 - "GET /api/v1/chat/back-music/music_file/%E5%A4%9C%E6%99%9A%E9%9F%B3%E6%95%88.mp3 HTTP/1.1" 206
[INFO]: 127.0.0.1:33976 - "GET /vite.svg HTTP/1.1" 200
[INFO]: 127.0.0.1:33976 - "GET /vite.svg HTTP/1.1" 200
[INFO]: 来自客户端的消息：{'type': 'message', 'content': 'hello.'}

=== AI回复流式输出 ===
[INFO]: 127.0.0.1:42814 - "GET /audio_effects/%E6%97%A0%E8%AF%AD.wav HTTP/1.1" 206
[INFO]: 127.0.0.1:42814 - "GET /audio_effects/%E6%97%A0%E8%AF%AD.wav HTTP/1.1" 206
[INFO]: 127.0.0.1:42812 - "GET /pictures/animation/AI%E6%80%9D%E8%80%83.webp?t=1757818074571 HTTP/1.1" 200
[INFO]: 127.0.0.1:42812 - "GET /pictures/animation/AI%E6%80%9D%E8%80%83.webp?t=1757818074571 HTTP/1.1" 200
【惊讶】啊！莱姆你醒啦？【[INFO]: 开始处理句子: 【惊讶】啊！莱姆你醒啦？
[ERROR]: 通用网络大模型流式请求失败: Error code: 401 - {'error': {'message': "You didn't provide an API key. You need to provide your API key in an Authorization header using Bearer auth (i.e. Authorization: Bearer YOUR_KEY). ", 'type': 'invalid_request_error', 'param': None, 'code': None}, 'request_id': 'fe0975ab-9ac4-4003-b87f-ebf57c919344'}
害羞】我刚才还在想你是不是要睡到中午呢...【害羞】我刚才还在想你是不是要睡到中午呢...
=== 流式输出结束 ===
[INFO]: 开始处理句子: 【害羞】我刚才还在想你是不是要睡到中午呢...
[ERROR]: 通用网络大模型流式请求失败: Error code: 401 - {'error': {'message': "You didn't provide an API key. You need to provide your API key in an Authorization header using Bearer auth (i.e. Authorization: Bearer YOUR_KEY). ", 'type': 'invalid_request_error', 'param': None, 'code': None}, 'request_id': '4cfa9e0a-6290-4050-8db2-c59b37930a99'}
```
更改.env，比如开关rag或者时间感知等，没有影响到这个情况。
输入hello后，控制台显示上述情况后，网页显示“灵灵正在思考中”，无法再输入。
是否开启科学魔法代理不影响。
用python main.py情况一样。

## doc-err
其他小情况。
“你可以参考源代码使用教程来使用LingChat的源代码，并随时获取最新的develop开发版更新。”
源代码使用教程已经404 - page not found了。

### 其他
话说，self能不能申请加个技术开发交流群啥的，学习大佬技术期望.jpg，虽然开发技能不太行，也许可以作为免费劳动力，帮忙测试测试啥的。
虽然目前成功运行还有问题，泪目。
是藏在lingchat git仓库中的，查了一下目前101人的群吗。人还蛮多的。
另外以防万一去重新运行了一下稳定版exe，还好还好还能使（）。
