# Описание
  Бот для телеграм для просмотра активности компьютера.Уведомляет пользователя о запуске ПК, отслеживает процессы, скриншотит рабочий стол, выключает ПК, выводит фейковые ошибки, выключает клавиатуру и мышь.
    Настоятельно рекомендую добавить в автозапуск, для более лучшего опыта.
      Перед использованием добавьте в ```config.py``` свой токен и ```telegram id```.

# Использование
Использую этого бота для личных целей, к примеру, не включается ли «самопроизвольно» пк, пока меня нет дома.

Чтобы начать его использовать правильно (по моему мнению), нужно добавить .bat файл в автозапуск:

```
@echo off
start /B pythonw.exe C:/(путь до main.py)
exit
```

# Команды
Для вывода команд бота используйте /start.

Команды:
```
📌 /start - выводит данный текст
❌ /error {текст} - выводит фейковую ошибку
🖼️ /screenshot - делает скриншот рабочего стола
💤 /off - выключает пк
🚷 /off_devices - выключает клавиатуру и мышь до перезагрузки пк
```

# Много импортов

```
import ctypes
import telebot
import time
import atexit
import threading
import pythoncom
import wmi
import pyautogui
import os
import pygetwindow as gw
import config
from io import BytesIO
from config import TOKEN, AUTHORIZED_ID, IGNORED_PROCESSES
from datetime import datetime
from telebot import types
