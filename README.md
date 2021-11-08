# TestTask
Тестовое задание.

Задача:
Подготовить docker-compose проект в котором должны быть развернуты контейнеры: Jbpm, Nginx, Postgres, Prometheus, Grafana, Node-exporter

Проверка правильности выполнения задания:

Для выполненного задания все запросы поступают на 80 порт через Nginx контейнер (запросы проксируются в Jbpmn и Grafana на разные endpoint-ы). Остальные порты должны быть закрыты.

Jbpmn настроен на работу с СУБД postgres

Grafana настроена на работу с Prometheus. Внутри Grafana настроен dashboard для отображение метрик из Prometheus. Prometheus забирает метрики с host машины (node-exporter)

///

В качествет host-машины использован сервер Ubuntu 20.04

Docker версии 20.10.8

Docker-compose версии 2.0.1

Для запуска проекта необходимо выполнить "docker-compose up -d" в каталоге проекта.

Общее время запуска ~5-6 минут, не считая загрузку образов.

///

Для входа в grafana используйте логин/пароль:admin/admin.
В настройках Grafana необходимо указать ссылку на Prometheus
(configuration -> data source -> add data source),
в качестве сервера выбрать Prometheus и установить URL "http://prometheus_testtask:9090/".
Настройка "dashboard по умолчанию" в работе...

Prometheus по умолчанию подключается к node-exporter, 
это можно проверить в настройках (status -> targets).

Для входа в jBPM используйте логин/пароль:wbadmin/wbadmin

web-страница Grafana http://localhost/grafana.

web-страница Prometheus http://localhost/prometheus.

web-страница jBPM-движка http://localhost/jbpm/business-central.

Спасибо за внимание!
