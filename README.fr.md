# tg-search-bot

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->

[![All Contributors](https://img.shields.io/badge/all_contributors-4-orange.svg?style=flat-square)](#contributors-)

<!-- ALL-CONTRIBUTORS-BADGE:END -->

**Un bot Telegram qui peut être utilisé pour rechercher divers liens magnétiques vidéo. Il prend en charge des opérations telles que la collecte, l'exportation d'enregistrements et l'enregistrement automatique des liens magnétiques. Il peut être configuré manuellement pour bloquer le contenu NSFW et l'accès Internet proxy.**

Le bot est construit sur la base de Python3, prend en charge le déploiement en un clic avec Docker et implémente des fonctions de mise en cache via Redis.

Documentation README dans d'autres langues (générée automatiquement par[traduire-lisez-moi](https://github.com/dephraiim/translate-readme)):[arabe](./README.ar.md),[Non](./README.hi.md),[Français](./README.fr.md),[Chinois simplifié](./README.zh-CN.md),[chinois traditionnel](./README.zh-TW.md).

## Les fonctions

Les fonctions suivantes sont triées par heure d'achèvement du développement et de nouvelles fonctions seront continuellement ajoutées à l'avenir.

-   Prend en charge l'obtention d'informations vidéo de base et de liens magnétiques - 2022/11/25
-   Prise en charge du proxy de configuration - 26/11/2022
-   Prise en charge des liens magnétiques de filtrage (non censuré => hd => sous-titre) - 26/11/2022
-   Support permettant au bot d'enregistrer automatiquement les liens magnétiques optimaux vers Pikpak - 2022/12/29
-   Prise en charge de l'obtention d'un aperçu de la vidéo et de la vidéo complète - 2022/12/31
-   Prise en charge de l'obtention de captures d'écran vidéo - 01/01/2023
-   Collecte de soutien d'acteurs et de vidéos - 04/01/2023
-   Support déploiement via docker - 08/01/2023
-   Prend en charge l'obtention de classements d'acteurs et de classements de films - 20/01/2023
-   Prend en charge l'accès aléatoire aux vidéos les plus performantes et aux dernières vidéos - 2023/01/25
-   Aide à l'obtention des noms chinois des acteurs via Wikipédia - 2023/02/18
-   Support traduction des titres japonais - 18/02/2023
-   Accompagnement à la recherche d'acteurs - 18/02/2023
-   Prise en charge de la mise en cache via Redis - 2023/03/17

## Didacticiel

Tout d'abord, vous devez télécharger le code du projet localement, puis configurer le bot et le modifier`~/.tg_search_bot/config.yaml`：

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

PS : Si vous souhaitez utiliser la fonction d’envoi automatique de Pikpak, vous devez d’abord l’autoriser manuellement :[Bot officiel Pikpak](https://t.me/PikPak6_Bot), puis connectez-vous lors de la première exécution du bot. (Mon code d'invitation Pikpak : 99492001, entrez pour devenir membre)

Enfin, exécutez le bot : (les fichiers tels que les enregistrements et les journaux se trouvent dans`~/.tg_search_bot`)

```sh
# op1. docker-compose
docker-compose up -d
# op2. simple way (Python >=3.9)
pip install -r requirements.txt && python3 bot.py
```

## Development

J'utilise python-3.9.13 pour le développement. Veuillez utiliser python &lt;= 3.9 pour le développement. De plus, il est recommandé d'utiliser le développement d'un environnement virtuel Python pour éviter des problèmes inutiles. Voici mes étapes de développement à titre de référence uniquement :

```shell
git clone https://github.com/akynazh/tg-search-bot.git
cd tg-search-bot
~/.pyenv/versions/3.9.13/bin/python -m venv .venv
source ./.venv/bin/activate
pip3 install -r requirements.txt
```

Ensuite, vous pouvez commencer à écrire du code. Lorsque vous avez terminé, n'oubliez pas d'écrire ou d'exécuter une instance de test (dans`tests/test.py`). Veuillez vous assurer qu'il n'y a aucun problème avec le test avant de soumettre le code.

## Tous

-   version anglaise
-   La recherche vidéo prend en charge davantage de sites Web magnétiques (actuellement, seul The Pirate Bay est pris en charge)
-   D'autres fonctionnalités que vous aimeriez voir apparaître...

## Remerciements

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

Si vous souhaitez également contribuer à la communauté, veuillez consulter[tout liste](https://github.com/akynazh/tg-search-bot#TODO)et lis[étapes de développement](https://github.com/akynazh/tg-search-bot#Development), les problèmes et les prs sont les bienvenus.
