# tg 搜索机器人

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->

[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)

<!-- ALL-CONTRIBUTORS-BADGE:END -->

**一个 Telegram 机器人，可用于搜索各种视频磁力链接。支持收藏、导出记录、自动保存磁力链接等操作。它可以手动配置为阻止 NSFW 内容和代理 Internet 访问。**

该机器人基于Python3构建，支持使用Docker一键部署，并通过Redis实现缓存功能。

其他语言的自述文件（由自动生成[翻译自述文件](https://github.com/dephraiim/translate-readme)):[阿拉伯](./README.ar.md),[没有](./README.hi.md),[法语](./README.fr.md),[简体中文](./README.zh-CN.md),[繁体中文](./README.zh-TW.md).

## 功能

以下功能按开发完成时间排序，后续会不断添加新功能。

-   Supports obtaining basic video information and magnet links - 2022/11/25
-   支持配置代理 - 2022/11/26
-   支持过滤磁力链接（无码=>高清=>字幕）- 2022/11/26
-   支持让机器人自动保存最佳磁力链接到 Pikpak - 2022/12/29
-   支持获取预览视频和完整视频 - 2022/12/31
-   支持获取视频截图 - 2023/01/01
-   支持演员及视频采集 - 2023/01/04
-   支持通过docker部署 - 2023/01/08
-   支持获取演员排名和电影评分 - 2023/01/20
-   支持随机访问高分视频和最新视频 - 2023/01/25
-   支持通过维基百科获取演员中文名字 - 2023/02/18
-   支持日文标题翻译 - 2023/02/18
-   支持寻找演员 - 2023/02/18
-   通过redis支持缓存 - 2023/03/17

## 教程

首先需要将项目代码下载到本地，然后配置bot并编辑`~/.tg_search_bot/config.yaml`：

```yaml
# required, your telegram chat id
tg_chat_id:
# required, your telegram bot token
tg_bot_token:
# required, global proxy, 1 yes | 0 no
use_proxy:
# required, dmm proxy, 1 yes | 0 no
use_proxy_dmm:
# optional, proxy server address (required if use_proxy == 1 or use_proxy_dmm == 1)
proxy_addr:
# required, pikpak’s automatic sending function, 1 yes | 0 no
use_pikpak:
# optional, your telegram api id (required if use_pikpak == 1)
tg_api_id:
# optional, your telegram api hash (required if use_pikpak == 1)
tg_api_hash:
# required, enable cache or not, 1 yes | 0 no
use_cache:
# optional, your redis host (required if use_cache == 1)
redis_host:
# optional, your redis port (required if use_cache == 1)
redis_port:
# optional, your redis password
redis_password:
# required, enable nsfw or not, 1 yes | 0 no
enable_nsfw: 0
```

PS：如果要使用Pikpak的自动发送功能，需要先手动授权：[Pikpak 官方机器人](https://t.me/PikPak6_Bot)，然后在第一次运行机器人时登录。 （我的Pikpak邀请码：99492001，输入即可获得会员资格）

最后运行bot：（记录、日志等文件位于`~/.tg_search_bot`)

```sh
# op1. docker-compose
docker-compose up -d
# op2. simple way (Python >=3.9)
pip install -r requirements.txt && python3 bot.py
```

## 发展

我使用 python-3.9.13 进行开发。请使用 python &lt;= 3.9 进行开发。另外，建议使用python虚拟环境开发，以避免出现不必要的问题。以下是我的开发步骤，仅供参考：

```shell
git clone https://github.com/akynazh/tg-search-bot.git
cd tg-search-bot
~/.pyenv/versions/3.9.13/bin/python -m venv .venv
source ./.venv/bin/activate
pip3 install -r requirements.txt
```

然后就可以开始编写代码了。完成后，请记住编写或运行一个测试实例（在`tests/test.py`）。提交代码前请确保测试没有问题。

## 全部

-   英文版
-   视频搜索支持更多磁力网站（目前仅支持海盗湾）
-   您希望看到的其他功能出现...

## 致谢

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

<!-- prettier-ignore-start -->

<!-- markdownlint-disable -->

<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://akynazh.site"><img src="https://avatars.githubusercontent.com/u/78672905?v=4?s=100" width="100px;" alt="Jack Bryant"/><br /><sub><b>Jack Bryant</b></sub></a><br /><a href="#maintenance-akynazh" title="Maintenance">🚧</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/z-hhh"><img src="https://avatars.githubusercontent.com/u/8455958?v=4?s=100" width="100px;" alt="zhhh"/><br /><sub><b>zhhh</b></sub></a><br /><a href="https://github.com/akynazh/tg-search-bot/commits?author=z-hhh" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://allcontributors.org"><img src="https://avatars.githubusercontent.com/u/46410174?v=4?s=100" width="100px;" alt="All Contributors"/><br /><sub><b>All Contributors</b></sub></a><br /><a href="https://github.com/akynazh/tg-search-bot/commits?author=all-contributors" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/JackBryant286"><img src="https://avatars.githubusercontent.com/u/113345781?v=4?s=100" width="100px;" alt="Jack Bryant"/><br /><sub><b>Julia</b></sub></a><br /><a href="https://github.com/akynazh/tg-search-bot/commits?author=JackBryant286" title="Code">💻</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->

<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

如果您也想为社区做出贡献，请查看[一切清单](https://github.com/akynazh/tg-search-bot#TODO)并阅读[开发步骤](https://github.com/akynazh/tg-search-bot#Development)欢迎提出问题和 PR。
