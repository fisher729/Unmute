# NVDA Unmute (Автовключение звука Windows)

* Автор: Олександр Грищенко
* Версия: 1.2
* Загрузить [стабільную версию][1]
* Загрузить [версию в разработке][2]

Это дополнение проверяет состояние аудиосистемы Windows при запуске NVDA. И, если оказывается, что звук выключен или очень приглушенный, - приложение принудительно включает его.
Также дополнение проверяет состояние синтезатора речи. Если возникли проблемы с его инициализацией, выполняются попытки запуска синтезатора, который указан в настройках NVDA.

## Диалоговое окно настроек дополнения
В диалоговом окне настроек дополнения доступны следующие параметры:
1. Опция, которая позволяет включить системный звук Windows на максимальную громкость при запуске NVDA.
2. Если предыдущий флажок не установлен, то с помощью следующего слайдера можно отрегулировать уровень громкости системного звука, который будет установлен при запуске NVDA.
3. Слайдер для настройки значения минимальной громкости звука, при котором первые два пункта не будут применяться.

Примечание: Опции 1 и 2 применяются в следующих случаях:
* если звук системы Windows был выключен перед запуском NVDA;
* если уровень системного звука ниже, чем значение заданное с помощью слайдера 3.

4. Следующий флажок позволяет включить повторную инициализацию драйвера голосового синтезатора.
Эта процедура будет запускаться только в том случае, когда при старте NVDA будет обнаружено, что драйвер синтезатора голоса не был инициализирован.
5. В этом поле можно указать количество попыток повторной инициализации драйвера. Попытки выполняются циклически с интервалом в 1 секунду. Значение 0 означает, что попытки будут выполняться бесконечно аж до успешного завершения процедуры.

6. Следующий флажок включает или выключает воспроизведение стартового звука при успешном выполнении операции.

## Журнал изменений

### Версия 1.2
* переведено на использование модуля **pycaw** вместо **Windows Sound Manager**;
* добавлено воспроизведения звука при запуске, когда аудио успешно включено дополнением.

### Версия 1.1
* добавлено диалоговое окно с настройками приложения;
* обновленный перевод на Украинский язык.

### Версия 1.0.1
* выполняет неоднократные попытки повторно запустить драйвер синтезатора речи в случае его неудачной инициализации;
* добавлен перевод на вьетнамский язык (спасибо Dang Manh Cuong);
* добавлен перевод на Украинский язык.

### Версия 1.0: особенности реализации
В работе дополнение использует сторонний модуль Windows Sound Manager.

## Внесение изменений в NVDA Unmute
Вы можете клонировать этот репозиторий, чтобы внести изменения в NVDA Unmute.

### Дополнительные зависимости
Следующие модули можно установить с помощью pip:
- markdown
- scons
- python-gettext

### Построение дополнения из репозитория
1. Откройте командную строку, перейдите в корневой каталог этого репозитория.
2. Запустите на выполнение команду ** scons **. Если не возникло ошибок, сгенерированное дополнение будет помещено в текущий каталог.

[1]: https://github.com/grisov/Unmute/releases/download/v1.2/unmute-1.2.nvda-addon
[2]: https://github.com/grisov/Unmute/releases/download/v1.2/unmute-1.2.nvda-addon
