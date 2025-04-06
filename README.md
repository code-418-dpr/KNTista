# KNTista

[![license](https://img.shields.io/github/license/code-418-dpr/KNTista)](https://opensource.org/licenses/MIT)
[![release](https://img.shields.io/github/v/release/code-418-dpr/KNTista?include_prereleases)](https://github.com/code-418-dpr/KNTista/releases)
[![downloads](https://img.shields.io/github/downloads/code-418-dpr/KNTista/total)](https://github.com/code-418-dpr/KNTista/releases)
[![code size](https://img.shields.io/github/languages/code-size/code-418-dpr/KNTista.svg)](https://github.com/code-418-dpr/KNTista)

Проект для автоматизации нужд [профбюро ИКНТ](https://vk.com/iknt_donntu)

## Особенности реализации

- [x] микросервисная архитектура
- [x] единая среда развёртывания
- [x] интегрирован CI/CD
- [x] веб-приложение с поддержкой технологии PWA
- [x] полностью рабочий функционал отслеживания активности на факультете и составления отчётов о ней
- [ ] Telegram-бот поддерживает часть клиентского функционала веб-приложения

## Архитектура

Проект состоит из микросервисов, предназначенных для развёртывания в Docker:

- [фронтенд](https://github.com/code-418-dpr/KNTista-frontend)
- [бэкенд](https://github.com/code-418-dpr/KNTista-api)
- Telegram-бот...

## Установка

> [!NOTE]
> Мы отказались от использования `git submodules` и `git subtree` из-за периодически возникающей путаницы при
> отслеживании изменений в монорепозиториях. Данный репозиторий представляет собой единую точку для работы с проектом,
> лишённую этих недостатков.

0. Клонируйте репозиторий и перейдите в его папку.
1. Клонируйте репозитории сервисов, входящих в состав проекта по SSH (рекомендуется):

```shell
git clone git@github.com:code-418-dpr/KNTista-frontend.git services/KNTista-frontend
git clone git@github.com:code-418-dpr/KNTista-api.git services/KNTista-api
```

или по HTTPS:

```shell
git clone https://github.com/code-418-dpr/KNTista-frontend.git services/KNTista-frontend
git clone https://github.com/code-418-dpr/KNTista-backend.git services/KNTista-api
```

После этого вы можете вносить изменения в каждый из сервисов по-отдельности (в соответствии с инструкциями, описанными в
соответствующих README).

## Запуск

0. Установите проект по инструкции выше.
1. Создайте файл `.env` на основе [.env.template](.env.template) и настройте все описанные там параметры.
2. Установите Docker.
3. Ознакомьтесь с инструкциями к сервисам проекта. Некоторые из них могут требовать дополнительной конфигурации
   (например, применение миграций к БД)
4. Теперь запускать проект можно командой:

```shell
docker compose up -d --build
```
