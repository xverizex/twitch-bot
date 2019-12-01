# twitch-bot 0.6
twitch бот. Выводит в область уведомления сообщения.

Зависимости:
* glib-2.0
* gio-2.0

Дополнительные зависимости, если захотите использовать webhook.
* json-c
* libssl


Чтобы установить, первым делом выполните ./configure, если хотите установить дополнительные опции, то выполните ./configure --help

Наберите @nickname help, чтобы посмотреть допустимые команды.

Получите токен с сайта https://twitchapps.com/tmi/ .Нужно заполнить файл /home/%nick/.twitch-bot/conf. Чтобы создать эти файлы запустите первый раз бота. Он создаст и каталоги и файлы. Далее заполните файл конфигурации.
* token = токен вместе со словом oauth.
* nickname = ваше имя пользователя 
* channel = название вашего канала
* audacious = если задано true, то можно управлять музыкальным плеером audacious, если false, то нельзя управлять.
* rhythmbox = если задано true, то можно управлять музыкальным плеером rhythmbox, если false, то нельзя управлять.
* user-id = установите свой uid, чтобы посмотреть свой uid, выполните в терминале команду `id`. Это нужно для того, что если вы укажите порт меньше 1024, в таком случае, чтобы бот запустился, его надо запустить с правами root, как только выполняться необходимые действия, права будут понижены до уровня пользователя. Лучше указывайте порт больше 1024, но если вы напрямую подключены к интернету, то обязательно укажите порт 80 в опции port_event. Понижение прав до уровня пользователя включён только в webhook модуле, потому что только там нужно выполнить привилигерованные функции, если указан порт меньше 1024.

Дополнительные опции, описание.
* --enable-webhook включает вебхук сервер. Нужно в настройках указать порт. Лучше указывать порт больше 1024, чтобы не требовало root прав. Чтобы правильно использовать, нужно на вашем маршрутизаторе включить перенаправление портов. Например в программе указан порт 8000. В маршрутизаторе указываете с api.twitch.tv с 80 порта транслировать на ваш компьютер на 8000 порт. Если я смогу, то реализую websockets, но пока придётся пользоваться таким. Данные вебхук позволяет видеть уведомления о новых подписчиках.


Дополнительные настройки
* client_id - Чтобы получить client_id, нужно зарегестрировать своего бота на этой странице https://dev.twitch.tv/console/apps/create .
* port_event - укажите порт для webhook сервера, чтобы получать уведомления о новых подписчиках.
* callback - укажите ваш ip ( если вы находитесь за nat ( то есть подключены к маршрутизатору ), то укажите ip маршрутизатора. Указывать надо адрес начиная с http вот так http://173.259.12.13. Вожно указать именно http, и открыть 80 порт на роутере, потому что webhook не принимает другие порты. Можно было сделать и 443 порт ( это https ), но это лишнее.

Возможности по управлению плеером audacious или rhythmbox
* next - включить следующий трек
* prev - включить предыдущий трек
* track - узнать альбом и песню, которая проигрывается в данный момент
![](http://s1.uploadpics.ru/images/Wylq3uVVHS.png)
