# tg 搜索機器人

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->

[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)

<!-- ALL-CONTRIBUTORS-BADGE:END -->

**一個 Telegram 機器人，可用於搜尋各種視訊磁力連結。支援收藏、匯出記錄、自動儲存磁力連結等操作。它可以手動設定為阻止 NSFW 內容和代理 Internet 存取。**

該機器人基於Python3構建，支援使用Docker一鍵部署，並透過Redis實現快取功能。

其他語言的自述文件（由自動生成[翻譯自述文件](https://github.com/dephraiim/translate-readme)):[阿拉伯](./README.ar.md),[沒有](./README.hi.md),[法語](./README.fr.md),[簡體中文](./README.zh-CN.md),[繁體中文](./README.zh-TW.md).

## 功能

以下功能依開發完成時間排序，後續將持續新增功能。

-   支援獲取基本視訊資訊和磁力連結 - 2022/11/25
-   支援配置代理 - 2022/11/26
-   支援過濾磁力連結（無碼=>高清=>字幕）- 2022/11/26
-   支援讓機器人自動保存最佳磁力連結到 Pikpak - 2022/12/29
-   支援取得預覽影片和完整影片 - 2022/12/31
-   支援獲取視頻截圖 - 2023/01/01
-   支援演員及視訊採集 - 2023/01/04
-   支援透過docker部署 - 2023/01/08
-   支援獲取演員排名和電影評分 - 2023/01/20
-   支援隨機存取高分影片和最新影片 - 2023/01/25
-   支持透過維基百科獲取演員中文名字 - 2023/02/18
-   支援日文標題翻譯 - 2023/02/18
-   支持尋找演員 - 2023/02/18
-   透過redis支援緩存 - 2023/03/17

## 教學

首先需要將專案程式碼下載到本機，然後設定bot並編輯`~/.tg_search_bot/config.yaml`：

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

PS：如果要使用Pikpak的自動傳送功能，需要先手動授權：[Pikpak 官方機器人](https://t.me/PikPak6_Bot)，然後在第一次運行機器人時登入。 （我的Pikpak邀請碼：99492001，輸入即可獲得會員資格）

最後執行bot：（記錄、日誌等文件位於`~/.tg_search_bot`)

```sh
# op1. docker-compose
docker-compose up -d
# op2. simple way (Python >=3.9)
pip install -r requirements.txt && python3 bot.py
```

## 發展

我使用 python-3.9.13 進行開發。請使用 python &lt;= 3.9 進行開發。另外，建議使用python虛擬環境開發，以避免不必要的問題。以下是我的開發步驟，僅供參考：

```shell
git clone https://github.com/akynazh/tg-search-bot.git
cd tg-search-bot
~/.pyenv/versions/3.9.13/bin/python -m venv .venv
source ./.venv/bin/activate
pip3 install -r requirements.txt
```

然後就可以開始寫程式碼了。完成後，請記住編寫或運行一個測試實例（在`tests/test.py`）。提交程式碼前請確保測試沒有問題。

## 全部

-   英文版
-   影片搜尋支援更多磁力網站（目前僅支援海盜灣）
-   您希望看到的其他功能出現...

## 致謝

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

如果您也想為社區做出貢獻，請查看[一切清單](https://github.com/akynazh/tg-search-bot#TODO)並閱讀[開發步驟](https://github.com/akynazh/tg-search-bot#Development)歡迎提出問題和 PR。
