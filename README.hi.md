# टीजी-खोज-बॉट

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->

[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)

<!-- ALL-CONTRIBUTORS-BADGE:END -->

**एक टेलीग्राम बॉट जिसका उपयोग विभिन्न वीडियो चुंबक लिंक खोजने के लिए किया जा सकता है। यह संग्रह, निर्यात रिकॉर्ड और स्वचालित रूप से चुंबक लिंक को सहेजने जैसे कार्यों का समर्थन करता है। इसे NSFW सामग्री और प्रॉक्सी इंटरनेट एक्सेस को ब्लॉक करने के लिए मैन्युअल रूप से कॉन्फ़िगर किया जा सकता है।**

बॉट Python3 पर आधारित है, डॉकर के साथ एक-क्लिक परिनियोजन का समर्थन करता है, और Redis के माध्यम से कैशिंग फ़ंक्शन लागू करता है।

अन्य भाषाओं में README दस्तावेज़ (स्वचालित रूप से उत्पन्न)।[अनुवाद-रीडमी](https://github.com/dephraiim/translate-readme)):[अरबी](./README.ar.md),[नहीं](./README.hi.md),[फ़्रेंच](./README.fr.md),[सरलीकृत चीनी](./README.zh-CN.md),[परंपरागत चीनी](./README.zh-TW.md).

## कार्य

निम्नलिखित कार्यों को विकास पूरा होने के समय के अनुसार क्रमबद्ध किया गया है, और भविष्य में लगातार नए कार्य जोड़े जाएंगे।

-   बुनियादी वीडियो जानकारी और चुंबक लिंक प्राप्त करने का समर्थन करता है - 2022/11/25
-   समर्थन कॉन्फ़िगरेशन प्रॉक्सी - 2022/11/26
-   समर्थन फ़िल्टरिंग चुंबक लिंक (बिना सेंसर => एचडी => उपशीर्षक) - 2022/11/26
-   बॉट को पिकपैक में इष्टतम चुंबक लिंक को स्वचालित रूप से सहेजने की अनुमति देने वाला समर्थन - 2022/12/29
-   पूर्वावलोकन वीडियो और पूर्ण वीडियो प्राप्त करने में सहायता - 2022/12/31
-   वीडियो स्क्रीनशॉट प्राप्त करने में सहायता - 2023/01/01
-   अभिनेताओं और वीडियो का समर्थन संग्रह - 2023/01/04
-   डॉकर के माध्यम से समर्थन परिनियोजन - 2023/01/08
-   अभिनेता रैंकिंग और फिल्म रेटिंग प्राप्त करने में सहायता - 2023/01/20
-   उच्च स्कोरिंग वीडियो और नवीनतम वीडियो तक यादृच्छिक पहुंच का समर्थन करता है - 2023/01/25
-   विकिपीडिया के माध्यम से अभिनेताओं के चीनी नाम प्राप्त करने में सहायता - 2023/02/18
-   जापानी शीर्षकों का समर्थन अनुवाद - 2023/02/18
-   अभिनेताओं की खोज में सहायता - 2023/02/18
-   रेडिस के माध्यम से कैशिंग का समर्थन करें - 2023/03/17

## ट्यूटोरियल

सबसे पहले, आपको प्रोजेक्ट कोड को स्थानीय रूप से डाउनलोड करना होगा, फिर बॉट को कॉन्फ़िगर करना होगा और संपादित करना होगा`~/.tg_search_bot/config.yaml`：

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

पुनश्च: यदि आप पिकपैक के स्वचालित भेजने वाले फ़ंक्शन का उपयोग करना चाहते हैं, तो आपको पहले इसे मैन्युअल रूप से अधिकृत करना होगा:[पिकपैक आधिकारिक बॉट](https://t.me/PikPak6_Bot), और फिर पहली बार बॉट चलाते समय लॉग इन करें। (मेरा पिकपैक आमंत्रण कोड: 99492001, सदस्यता प्राप्त करने के लिए दर्ज करें)

Finally, run the bot: (files such as records and logs are located in `~/.tg_search_bot`)

```sh
# op1. docker-compose
docker-compose up -d
# op2. simple way (Python >=3.9)
pip install -r requirements.txt && python3 bot.py
```

## विकास

मैं विकास के लिए पायथन-3.9.13 का उपयोग करता हूं। कृपया विकास के लिए पायथन &lt;= 3.9 का उपयोग करें। इसके अलावा, अनावश्यक समस्याओं से बचने के लिए पायथन वर्चुअल पर्यावरण विकास का उपयोग करने की अनुशंसा की जाती है। केवल संदर्भ के लिए मेरे विकास चरण निम्नलिखित हैं:

```shell
git clone https://github.com/akynazh/tg-search-bot.git
cd tg-search-bot
~/.pyenv/versions/3.9.13/bin/python -m venv .venv
source ./.venv/bin/activate
pip3 install -r requirements.txt
```

फिर आप कोड लिखना शुरू कर सकते हैं। जब आपका काम पूरा हो जाए, तो एक परीक्षण उदाहरण लिखना या चलाना याद रखें (में)।`tests/test.py`). कृपया कोड सबमिट करने से पहले सुनिश्चित कर लें कि परीक्षण में कोई समस्या नहीं है।

## सभी

-   अंग्रेजी संस्करण
-   वीडियो खोज अधिक चुंबकीय वेबसाइटों का समर्थन करती है (वर्तमान में केवल द पाइरेट बे समर्थित है)
-   अन्य सुविधाएँ जिन्हें आप प्रदर्शित होते देखना चाहेंगे...

## स्वीकृतियाँ

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

यदि आप भी समुदाय में योगदान देना चाहते हैं, तो कृपया देखें[सब कुछ सूची](https://github.com/akynazh/tg-search-bot#TODO)और पढ़ें[विकास के चरण](https://github.com/akynazh/tg-search-bot#Development), मुद्दों और पीआरएस का स्वागत है।
