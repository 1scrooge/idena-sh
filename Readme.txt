Скрипт создает в текущем каталоге каталоги idena, idena-scripts и открывает порты 40403 и 40404.
В каталоге idena находится блокчейн ноды и демон idena-node.
В каталоге idena-scripts находится скрипт автообновления ноды, который запускается посредством crontab один раз в час.
Сюда же загружаются и проверяются версии исходников с https://github.com/idena-network/idena-go.git
Скрипт автообновления сверяет версию исходников с версией бинарника idena-node, если они отличаются, то скачивает новый релиз.
Запуск ноды осуществляется через сервис systemd.
Изенить параметры запуска можно через редактирование файла /etc/systemd/system/idena.service
Порты по умолчанию:
IPFS port (default 40403)
Node tcp port (default 40404)
Нода запускается с параметром --profile=lowpower

Start idena node:     sudo systemctl start idena.service
Stop idena node:      sudo systemctl stop idena.service
Enabe idena service:  sudo systemctl enable idena.service
Disable idena service:  sudo systemctl disable idena.service
Status idena node:      sudo systemctl status idena.service

For idena.service file editing:   sudo nano /etc/systemd/system/idena.service
After editing idena.service file: sudo systemctl daemon-reload
The log is available on command:  tail -f ~/idena/datadir/logs/output.log