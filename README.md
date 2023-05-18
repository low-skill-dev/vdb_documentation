## This repo contains russian description for the next projects (clickable):
[![ico](https://img.shields.io/badge/rest2wireguard-yellow?style=for-the-badge)](https://github.com/LuminoDiode/rest2wireguard)
[![ico](https://img.shields.io/badge/vdb_main_server-yellow?style=for-the-badge)](https://github.com/LuminoDiode/vdb_main_server)
[![ico](https://img.shields.io/badge/vdb_web_client-yellow?style=for-the-badge)](https://github.com/LuminoDiode/vdb_web_client)
[![ico](https://img.shields.io/badge/vdb_desktop_client-yellow?style=for-the-badge)](https://github.com/LuminoDiode/vdb_desktop_client)

## Stack
[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/repository/docker/luminodiode/rest2wireguard)
[![Alpine Linux](https://img.shields.io/badge/Alpine_Linux-%230D597F.svg?style=for-the-badge&logo=alpine-linux&logoColor=white)](https://www.alpinelinux.org)
[![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)](https://nginx.org)

[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)
[![TS](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

[![.Net](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)](https://dotnet.microsoft.com/en-us/apps/aspnet)
[![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.npgsql.org/)

[![Wireguard](https://img.shields.io/badge/wireguard-%2388171A.svg?style=for-the-badge&logo=wireguard&logoColor=white)](https://www.wireguard.com)

## Introduction (in russian)
В современном мире российские пользователи сети «интернет» сталкиваются со значительными ограничениями – блокировками различных ресурсов. Причем исходить они могут как от властей РФ, так и от самих зарубежных сервисов («между молотом и наковальней»). В таких условиях актуальной становится разработка VPN-сервиса, обеспечивающего туннелирование траффика до серверов в иных юрисдикциях, обеспечивающих отсутствие ограничений.
В настоящем проекте выделяется несколько логических частей, которые можно выделить как по технологиям, так и по «бизнес-задачам». На текущем этапе они включают: VPN-сервера (т.н. ноды), главный сервер, сайт с информацией о проекте, клиентские приложения. Предполагаемой к использованию процедурой установления VPN-соединения предлагается следующее: клиент, после авторизации и получения JWT-токенов, регистрирует свой девайс на главном сервере, сообщая ему свой главный ключ, а также запрашивает список доступных нод; клиент запрашивает у главного сервера подключение к выбранной ноде; главный сервер, сначала удостоверившись, что клиент отключен от предыдущей ноды, проведя валидацию: проверив лимиты, соответствие уровня доступа пользователя запрашиваемой ноде и удостоверившись в доступности последней, передаёт ей публичный ключ пользователя; нода, после валидации ключа (с целью защиты от инъекций), выполняет его добавление, выделяет ему адрес в приватной сети, после чего возвращает главному серверу свой публичный ключ и выделенный адрес; главный сервер добавляет к полученному от ноды ответу IP-адрес ноды и порт, прослушиваемый сервером Wireguard, после чего возвращает всю полученную модель данных клиенту; клиент устанавливает Wireguard-туннель.
