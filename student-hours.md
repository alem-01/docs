# О считывании часов студента
На данный момент студент должен набирать минимум **20 часов** в неделю в школе `alem`.

## Быстрый переход
- [Как работает программа считывания часов](#как-работает-программа-считывания-часов)
- [Как понять что твои часы считываются](#как-понять-что-твои-часы-считываются)
- [Как начать считывать часы?](#как-начать-считывать-часы)
  - [Eсли программа не считывает часы](#eсли-программа-не-считывает-часы)

## Как работает программа считывания часов
Время студента считывается только в учебных компьютерах alem.
Программа начнет считывать часы с того момента как найдет активную сессию студента на платформе `01.alem.school` через один из браузеров:
1. [`Firefox`](https://www.mozilla.org/en-US/firefox/)
2. [`Chrome`](https://www.google.kz/intl/en/chrome/)
> Тут и написан порядок браузеров по которому программа проверяет на наличие сессии студента.


## Как понять что твои часы считываются
На дискорд сервере `alem`-а у вас должна быть присвоена роль `in-campus`. Присваивается оно в течении 10 минут после того как вы начали сессию в `01.alem.school`


## Как начать считывать часы?
1. Садимся за любой из учебных компьютеров алема.
2. Через один из браузеров (желательно `firefox`) перейдите в платформу [01.alem.school](https://01.alem.school) и залогиньтесь.
3. Проверьте считываются ли часы одним из способов:
- **1-ый способ:**
3. 1. Запустить текущую команду в терминале.
```
tail -f /var/log/syslog | grep --color=always -E "alem-student-logger.+"
```
3. 2. В течении 3х минут в терминале должно вывестись примерно подобное:
```console
Dec 11 12:56:50 ALEM-F4-R02-09 alem-student-logger[1437]: 2022/12/11 12:56:50.398581 start task for browser firefox
Dec 11 12:56:51 ALEM-F4-R02-09 alem-student-logger[1437]: 2022/12/11 12:56:51.085895 finish task for browser firefox
```

- **2-ой способ:**
3. 1. Подождать 10 минут пока на дискорд сервере у вас не появится роль `in-campus`.

<img alt="image-discord-in-campus" src="./img/student-hours/student-with-role-in-campus.jpeg" style="max-width:420px"/>


### Eсли программа не считывает часы
Перезагрузите компьютер и выполните все по инструкции выше `Как начать считывать часы?`. Если даже это не поможет, попросите помощи `teamalem`.