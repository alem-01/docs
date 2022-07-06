# Как установить приложение на файловую систему в флешке

## Установка
Установка будет происходить на примере установки [`discord`](https://discord.com/)

1. Скачивание `deb` пакета приложения.

Допустим мы скачали установщик discord в папке `/home/student/Downloads`. У нас **скаченный `deb` пакет называется `discord-0.0.18.deb`**.

2. Установка скаченного `deb` пакета.

Для этого создадим папку `applications` в домашнем каталоге.
```bash
mkdir ~/applications
```

Теперь установим дискорд в созданную папку `applications`
```bash
dpkg-deb -x /home/student/Downloads/discord-0.0.18.deb /home/student/applications/discord
```
> В вашем случае нужно заменить `discord-0.0.18.deb` на ваш установщик. И название `discord` на название вашего приложения.

> На самом деле вы можете установить приложение в любое место, главное в конце правильно написать пути в конфиг файле.

3. Создать конфиг файл в `/home/student/.local/share/applications`

Создаем конфиг файл:
```bash
nano /home/student/.local/share/applications/discord.desktop
```
> Конфиг файл обязательно должен называться с суффиксом `.desktop`. Например: `НАЗВАНИЕ_ПРИЛОЖЕНИЯ.desktop`.

Содержимое `discord.desktop`:
```cs
[Desktop Entry]
Encoding=UTF-8
Name=Discord
Exec=/home/student/applications/Discord/usr/bin/discord
Icon=/home/student/applications/Discord/usr/share/discord/discord.png
Terminal=false
Type=Application
Categories=Development;
```
> В вашем случае в конфиг файле надо менять значения 3-х полей (`Name`, `Exec`, `Icon`)<br>
> `Name` - Отображаемое название приложения. Название по которому будете искать ваше приложение.
> `Exec` - Абсолютный путь к исполняемому файлу(бинарнику)
> `Icon` - Абсолютный путь к иконке программы. Иконка должна быть в формате `.png` и размер `256x256` px
> `Terminal` - показывать ли терминал с программой. Можно поставить значение `true` чтобы узнать почему не запускается бинарник.

> **ВАЖНО:** Самое важное тут это конфиг файл. Вы можете любое приложение, бинарник и создать соответсвующий конфиг файл `НАЗВАНИЕ.desktop` с расширением `desktop` и поставить правильные поля. 
