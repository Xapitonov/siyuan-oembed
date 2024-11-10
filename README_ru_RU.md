<p align="center">
<img alt="SiYuan" src="https://raw.githubusercontent.com/anarion80/siyuan-oembed/refs/heads/main/icon.png">
<br>
<em>SiYuan Oembed и закладки в стиле Ghost</em>
<br><br>
<a title="Релизы" target="_blank" href="https://github.com/anarion80/siyuan-oembed/releases"><img src="https://img.shields.io/github/v/release/anarion80/siyuan-oembed?style=flat-square&color=9CF"></a>
<a title="Скачивания" target="_blank" href="https://github.com/anarion80/siyuan-oembed/releases"><img src="https://img.shields.io/github/downloads/anarion80/siyuan-oembed/total.svg?style=flat-square&color=blueviolet"></a>
<br>
<a title="AGPLv3" target="_blank" href="https://www.gnu.org/licenses/agpl-3.0.txt"><img src="https://img.shields.io/github/license/anarion80/siyuan-oembed"></a>
<a title="Размер кода" target="_blank" href="https://github.com/anarion80/siyuan-oembed"><img src="https://img.shields.io/github/languages/code-size/anarion80/siyuan-oembed.svg?style=flat-square&color=yellow"></a>
<a title="Pull Requests на GitHub" target="_blank" href="https://github.com/anarion80/siyuan-oembed/pulls"><img src="https://img.shields.io/github/issues-pr-closed/anarion80/siyuan-oembed.svg?style=flat-square&color=FF9966"></a>
<br>
<a title="Коммиты на GitHub" target="_blank" href="https://github.com/anarion80/siyuan-oembed/commits/main"><img src="https://img.shields.io/github/commit-activity/m/anarion80/siyuan-oembed.svg?style=flat-square"></a>
<a title="Последний коммит" target="_blank" href="https://github.com/anarion80/siyuan-oembed/commits/main"><img src="https://img.shields.io/github/last-commit/anarion80/siyuan-oembed.svg?style=flat-square&color=FF9900"></a>
<br>
<a href="https://buymeacoffee.com/anarion" target="_blank"><img src="https://raw.githubusercontent.com/pachadotdev/buymeacoffee-badges/main/bmc-yellow.svg" alt="Купите мне кофе"/></a>
</p>

<p align="center">
<a href="README.md">English</a> | <a href="README_pl_PL.md">Polish</a> | <a href="README_zh_CN.md">简体中文</a> | <a href="README_ru_RU.md">Русский</a>
</p>

## ✨ Описание плагина

Это плагин с двумя основными функциональными возможностями:

1. Он позволяет преобразовывать ссылки (URL) в их встроенное представление согласно формату [Oembed](https://oembed.com/). При поддержке определенного сайта ссылка может быть преобразована непосредственно в фото или видео, или любой другой формат, предоставляемый сайтом.

2. Он позволяет преобразовывать ссылки (URL) в красивое представление карточки закладки на основе карточек закладок [Ghost CMS](https://ghost.org/) [Bookmark cards](https://ghost.org/help/cards/#bookmark). Я использовал реализацию из своей темы [Astro Simply](https://github.com/anarion80/astro-simply).

Обе функциональные возможности независимы друг от друга, поэтому вы можете преобразовать как в oembed, так и в карточку закладки.

Это работает следующим образом:

![preview.png](preview.png)

![пример использования](asset/example_usage.gif)

> :exclamation:
> К сожалению, встраивания X.com (ранее Twitter) основаны на скриптах, и я пока не выяснил, почему скрипт не выполняется, несмотря на включение выполнения скриптов в настройках (см.: [мой пост на Liuyun.io](https://liuyun.io/article/1729866570402)) :exclamation:
>
> Точно так же Facebook/Instagram требует API_KEY для встраивания их контента

В связи с этим, oembed, возможно, имеет ограниченную полезность, и мне может потребоваться добавить явное преобразование для твитов.

## 🖱 Использование

Плагин предоставляет три способа для преобразования ссылок:

1. Команды со слешем с соответствующими горячими клавишами:
   - `/oembed`, `/Oembed`, `/oe`, `Ctrl`+`Shift`+`O` для преобразования Oembed
   - `/card`, `/bookmark`, `/bk`, `Ctrl`+`Shift`+`C` для преобразования карточки закладки
  ![Slash Commands](asset/slashcommands.png)

2. Меню значков блока после выбора одного или нескольких блоков:
  ![Block Icon Menu](asset/blockiconmenu.png)

3. Отдельные значки на приборной панели:
  ![Toolbar icons](asset/toolbar.png)

> :exclamation:
> Оба преобразования поддерживаются в виде переключателя. Первое срабатывание преобразует ссылку в oembed или карточку закладки. Второе срабатывание возвращает к обычной ссылке.

## ⚙ Настройки

Для плагина доступно несколько параметров конфигурации:

| Настройка | Объяснение |
| ---: | ----------- |
|`Улавливать ссылки из буфера обмена`|Автоматически превращать ссылки, вставленные из буфера обмена, в oembed или карточку закладки (:exclamation: Еще не реализовано!)|
|`Выбрать преобразование вставки`|Какое преобразование автоматически применять при вставке ссылки из буфера обмена (:exclamation: Еще не реализовано!)|
|`Включить отладку`|Включить детальную отладку для помощи в решении проблем|
|`Список заблокированных` для oembed|Список доменов, для которых следует пропустить преобразование (по одному на строку) (:exclamation: Еще не реализовано!)|
|`Список заблокированных` для карточек закладок|Список доменов, для которых следует пропустить преобразование (по одному на строку) (:exclamation: Еще не реализовано!)|
|`Пользовательский CSS для карточек закладок`|Возможность ввести личный CSS для стилизации карточек закладок. Все классы `kg-card-*` и `kg-bookmark-*` могут быть стилизованы.|

## ⌛ Проблемы и ограничения

В настоящее время плагин использует [openGraphScraperLite](https://github.com/jshemas/openGraphScraperLite) для получения метаданных Open Graph и Twitter. Это единственный, который я нашел, который корректно интегрируется с плагином. Он также увеличивает размер плагина (более 3 МБ без сжатия). [Metascraper](https://github.com/microlinkhq/metascraper) намного лучше, но, к сожалению, не работает в клиентской среде плагина.

Другой вариант — использовать [Microlink API](https://api.microlink.io) для получения метаданных ссылки, но это ограничено 50 запросами в день в бесплатном плане.

Еще одно ограничение — это уже упомянутая нехватка встраивания Facebook/Instagram через oembed и отсутствие выполнения скриптов для предоставления корректного CSS для X.com (Twitter).

## 🙏 Благодарности

- [SiYuan](https://github.com/siyuan-note/siyuan) за полезный инструмент. Я использовал некоторые их функции напрямую, так как они не были доступны через API.
- [Пример плагина SiYuan с vite и svelte](https://github.com/siyuan-note/plugin-sample-vite-svelte) - очень полезная база для разработки плагинов.
- [Zuoqiu-Yingyi и их монорепозиторий siyuan-packages-monorepo](https://github.com/Zuoqiu-Yingyi/siyuan-packages-monorepo).
- [Руководство по разработке плагинов SiYuan](https://docs.siyuan-note.club/en/guide/plugin/sy-plugin-dev-quick-start.html?utm_source=liuyun.io) - очень полезное введение в разработку плагинов.
- [Zuoez02 и их плагин-card-link](https://github.com/zuoez02/siyuan-plugin-card-link).
- [Frostime и их siyuan-dailynote-today](https://github.com/frostime/siyuan-dailynote-today).
- [Hqweay и их siyuan-hqweay-go](https://github.com/hqweay/siyuan-hqweay-go).
