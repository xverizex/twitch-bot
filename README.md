# twitch-bot 0.3
twitch бот, который ничего не делает. Не содержит команд, но можно дополнить функционал по вашему желанию. Выводит в область уведомления сообщения.

Зависимости:
* glib-2.0
* gio-2.0

Наберите @nickname help, чтобы посмотреть допустимые команды.

Получите токен с сайта https://twitchapps.com/tmi/ .Нужно заполнить файл /home/%nick/.twitch-bot/conf. Чтобы создать эти файлы запустите первый раз бота. Он создаст и каталоги и файлы. Далее заполните файл конфигурации.
* token = токен вместе со словом oauth.
* nickname = ваше имя пользователя 
* channel = название вашего канала
* audacious = если задано true, то можно управлять музыкальным плеером audacious, если false, то нельзя управлять.
![](http://s1.uploadpics.ru/images/Wylq3uVVHS.png)
