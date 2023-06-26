OmnideskAPI + TelegramBotApi

ТЗ: создать скрипт, который обрабатывает, отправленные на телеграм-аккаунт (важно - не бот) сообщения, и формирует новое обращение в панеле сотрудника CRM-системы Omnidesk.
Технологический стек:  - OmnideskAPI
                       - Telethon
                       - request (aiohttp)
                       - asyncio


Работа скрипта базируется на выстраивании взаимодействия между OmnideskAPI и TelegramBotAPI.

Для работы с API Telegram нам потребуется библиотека Telethon. Методы аутентификации и обработки сообщений непосредственно в телеграм-аккаунте реализованы именно в этой библиотеке, в отличие от Aiogram, который работает, в первую очередь, с ТГ-ботами.

OmnideskAPI - веб API. Работает путем отправки сформированных GET и POST запросов. Поэтому в обязательном порядке предстоит использовать библиотеку requests, либо aiohttp, если требуется асинхронность.

Для реализации даннного функционала, нет нужды настраивать работу с вебхуком. Создание тиккета создается посредством отправки одного url запроса и получать и обрабатывать какие-либо данные для последующей работы, от серверов омнидеск нам не нужно. Однако очевидно, что для того, чтобы в полной мере использовать функциональные возможности API, в будущем нам потребуется настройка кастомных каналов (нет возможности подключить телеграм-аккаунт в качестве стандартного канала связи) через OmnideskAPI и вебхук-сервера. В конечном счете, мы будем обрабатывать Json объект, выделять нужные поля с даннынми и использовать их.

В данном репозитории представлен пример реализации базового функционала с возможностью последующего расширения возможностей.

Ссылкки на документацию:

OmnideskAPI - https://omnidesk.ru/api/introduction#intro

Telethon - https://docs.telethon.dev/en/stable/

requests - https://requests.readthedocs.io/en/latest/

TelegramBotApi - https://core.telegram.org/bots/api

asyncio - https://docs.python.org/3/library/asyncio.html

Flask - https://flask.palletsprojects.com/en/2.3.x/
