---
title: Command-line Interface
localeTitle: Интерфейс командной строки
---
## Интерфейс командной строки

#### мотивация

Угловой тесно связан с интерфейсом командной строки (CLI). CLI упрощает создание угловой файловой системы. Он касается большей части конфигурации за кулисами, поэтому разработчики могут начать кодирование. CLI также имеет низкую кривую обучения, рекомендуемую для любого новичка, желающего прыгнуть. Черт, даже опытные разработчики Angular полагаются на CLI!

#### Монтаж

Угловой CLI требуется [Node.js и Node Packet Manager (NPM)](https://nodejs.org/en/) . Вы можете проверить эти программы с помощью команды терминала: `node -v; npm -v` . После установки откройте терминал и установите Угловой CLI с помощью этой команды: `npm install -g @angular/cli` . Это можно выполнить из любой точки вашей системы. CLI настроен для глобального использования с флагом `-g` .

Проверьте, есть ли CLI с командой: `ng -v` . Это выводит несколько строк информации. В одной из этих строк указывается версия установленного CLI.

Признайте, что `ng` является основным строительным блоком CLI. Все ваши команды начинаются с `ng` . Пора взглянуть на четыре из наиболее распространенных команд с префиксом `ng` .

#### Ключевые команды

*   новый
    
*   ng служить
    
*   ng генерировать
    
*   ng build
    
*   Обновление ng
    

Основные термины для каждого из них довольно ясны. Вместе они составляют то, что вам нужно, чтобы попасть в землю, работающую с помощью Angular. Конечно, их гораздо больше. Все команды описаны в [документации GitHub CLI 1](https://github.com/angular/angular-cli/wiki#additional-commands) . Вероятно, вы обнаружите, что перечисленные выше команды будут охватывать необходимые базы.

#### новый

`ng new` создает _новую_ угловую файловую систему. Это сюрреалистический процесс. Пожалуйста, перейдите к местоположению файла, желательному для _нового_ поколения приложений. Введите эту команду следующим образом, заменив `[name-of-app]` на все, что вы хотите: `ng new [name-of-app]` .

Должна появиться файловая система под папкой `[name-of-app]` . Не стесняйтесь исследовать то, что находится внутри. Старайтесь не делать никаких изменений. Все то, что вам нужно для запуска вашего первого приложения с угловым расположением, поставляется вместе в этой сгенерированной файловой системе.

#### ng служить

Чтобы запустить приложение, команда `ng serve` должна выполняться в папке `[name-of-app]` . Везде внутри папки будет делать. Угловой CLI должен признать, что он находится в среде, созданной с помощью `ng new` . Это будет работать при условии, что это условие. Идите и попробуйте: `ng serve` .

Приложение работает по порту 4200 по умолчанию. Вы можете просмотреть приложение «Угловое», перейдя на `localhost:4200` в любом веб-браузере. Угловые работы во всех браузерах. Если вы не используете старую версию Internet Explorer, приложение появится. Он отображает официальный логотип Angular вместе со списком полезных ссылок.

Хорошо, приложение запускается. Он, надеюсь, функционирует, но вам нужно знать, что происходит под капотом. Обратитесь к файловой системе `[name-of-app]` . Перейдите в `[name-of-app] -> src -> app` . В нем хранятся файлы, отвечающие за то, что вы видели на `localhost:4200` .

#### ng генерировать

Файлы `.component` определяют компонент Angular, включая его логику ( `.ts` ), стиль ( `.css` ), layout ( `.html` ) и тестирование ( `.spec.ts` ). В `app.module.ts` особенно выделяется. Вместе эти две группы файлов работают вместе как `component` и `module` . Оба `component` и `module` являются двумя отдельными примерами угловых схем. Схемы классифицируют различные целевые блоки кода, _генерируемые_ с помощью `ng generate` .

Ради этой статьи следует понимать, что `module` экспортирует и импортирует активы в и из основного дерева компонентов. `component` относится к одному разделу пользовательского интерфейса. Логика, стиль, макет и тестирование этой единицы заключаются в различные файлы `.component` .

Что касается `ng generate` , эта команда может генерировать скелеты для каждой из доступных [угловых схем 2](https://github.com/angular/angular-cli/wiki/generate#available-schematics) . Перейдите в `[name-of-app -> src -> app]` . Попробуйте создать новый `component` , выполнив: `ng generate component [name-of-component]` . Замените `[name-of-component]` на все, что захотите. Появится новый файл `[name-of-component]` вместе с необходимыми файлами- `component` .

Вы можете видеть, что `ng generate` ускоряет [шаблонный код](https://en.wikipedia.org/wiki/Boilerplate_code) Углового. `ng generate` также прокладывает вещи вверх. Схемы, созданные в контексте Угловой файловой системы, соединяются с корневым модулем системы. В этом случае это будет файл `app.module.ts` внутри `[name-of-app -> src -> app]` .

#### ng build

Угловой - это передний инструмент. CLI выполняет свою деятельность от лица переднего конца. `ng serve` настройку сервера. Это ведет к тому, что развитие целиком сосредоточено на лицевой части. Тем не менее, необходимо также подключить ваш собственный задний конец к угловому приложению.

`ng build` удовлетворяет эту потребность. Перед тем, как попробовать его в файловой системе. Перейдите к `[name-of-app] -> angular.json` . Посмотрите на эту единственную строку кода: `"outputPath": "dist/my-app"` .

Эта одна строка конфигурации определяет, где `ng build` выдает свои результаты. Результатами являются все угловые приложения, скомпилированные в одну папку `dist/my-app` . Внутри этой папки существует `index.html` . Все Угловое приложение может работать с `index.html` . Нет `ng serve` не надо здесь. С помощью этого файла вы можете легко подключить свой задний конец.

Дайте ему идти: `ng build` . Опять же, это должно выполняться в пределах угловой файловой системы. Основываясь на ключевом значении `“outputPath:”` в `angular.json` . Будет создан файл, в котором исходное приложение полностью скомпилировано. Если вы сохранили `“outputPath:”` то же самое, скомпилированное приложение будет находиться в: `[name-of-app] -> dist -> [name-of-app]` .

#### Обновление ng

В угловом обновлении обновляется автоматическое обновление всех угловых и npm-пакетов до последних версий.

Вот синтаксис и опции, которые можно использовать с `ng update` .

`ng update [package]`

**Опции**

*   пробный прогон `--dry-run (alias: -d)`
    
    Пройдите без внесения каких-либо изменений.
    
*   сила `--force`
    
    Если false, произойдет ошибка, если установленные пакеты несовместимы с обновлением.
    
*   все `--all`
    
    Обновлять ли все пакеты в package.json.
    
*   следующий `--next`
    
    Используйте самую большую версию, включая бета-версии и RC.
    
*   мигрировать только `--migrate-only`
    
    Выполняйте миграцию, не обновляйте установленную версию.
    
*   из `--from`
    
    Версия, из которой можно перейти. Доступно только при обновлении одного пакета и только при миграции.
    
*   в `--to`
    
    Версия, до которой применяются миграции. Доступно только при обновлении одного пакета и только при переходе. Требуется указать. По умолчанию установлена ​​установленная версия.
    
*   реестр `--registry`
    
    Реестр NPM для использования.
    

#### Вывод

Эти команды выполняют основы. Угловой CLI - невероятное удобство, которое ускоряет создание, настройку и расширение приложений. Он делает все это при сохранении гибкости, позволяя разработчику вносить необходимые изменения.

Пожалуйста, проверьте эти ссылки на `localhost:4200` если вы еще этого не сделали. Не забудьте запустить `ng serve` прежде чем открывать его. Благодаря лучшему пониманию CLI, вы теперь готовы узнать больше о том, что генерируется его наиболее важными командами.

### источники

1.  [Google. «Угловые / угловые-cli / wiki # дополнительные команды». GitHub.](https://github.com/angular/angular-cli/wiki#additional-commands)
    
2.  [Google. «Угловые / угловые-cli / wiki / генерировать # доступные-схемы». GitHub.](https://github.com/angular/angular-cli/wiki/generate#available-schematics)
    

### Ресурсы

*   [Угловой сайт CLI](https://cli.angular.io)
    
*   [Угловой CLI README](https://github.com/angular/angular-cli#angular-cli)
    
*   [Угловая документация CLI](https://github.com/angular/angular-cli/wiki)