# Omnigram
Код из Кворка.
 
Тз: создать скрипт, который бы обрабатывал сообщение, отправленное на телеграм аккаунт (важно - не бот) и создавал новый тиккет. Необходимо объяснить основную идею создания.

Работа скрипта ,базируется на выстраивании взаимодействия между OmnideskAPI и TelegramBotApi. Для взаимодействия с АПИ телеграма нам потребуется Telethon. Методы аутентификации и обработки сообщений непосредственно в телеграм аккаунте реализованы именно в этой библиотеке в отличии от Aiogram, который работает, в первую очередь с ТГ ботами. OmnideskAPI - веб апи. Работает путем отправки сформированных GET и POST запросов. Поэтому в обязательном порядке предстоит использовать библиотеку request либо aiohttp если требуется асинхронность. В Api омнидеска, нет возможности подключить телеграм аккаунт в качестве стандартного канала связи, поэтому потребуется настройка работы через использование webhook. Поэтому настраиваем хост на прием и последующую обработку Json объектов. 