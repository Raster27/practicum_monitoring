# practicum_monitoring
Ansible Monitoring & Logging Roles

Этот репозиторий содержит Ansible-роли для автоматического развертывания и настройки системы мониторинга и логирования на Ubuntu (ARM).

📌 Описание ролей

1️⃣ prometheus

Роль для установки и настройки Prometheus для сбора метрик.

Устанавливает Prometheus из официальных бинарников.

Создаёт и настраивает конфигурационные файлы.

Запускает сервис и добавляет его в автозагрузку.

2️⃣ node_exporter

Роль для установки Node Exporter, который собирает метрики о системе.

Устанавливает Node Exporter из официальных бинарников.

Запускает сервис и настраивает его автозапуск.

3️⃣ elasticsearch

Роль для установки и настройки Elasticsearch.

Загружает и устанавливает Elasticsearch.

Настраивает конфигурационные файлы.

Обеспечивает автозапуск службы.

4️⃣ kibana

Роль для установки и настройки Kibana.

Устанавливает Kibana.

Конфигурирует подключение к Elasticsearch.

Запускает сервис.

5️⃣ fluentbit

Роль для установки Fluent Bit и настройки логов в ELK.

Устанавливает Fluent Bit.

Конфигурирует ввод логов (systemd, файлы и т. д.).

Настраивает отправку логов в Elasticsearch.

⚙️ Требования

Ubuntu (ARM)

Ansible 2.10+

Открытые порты для Prometheus, Elasticsearch, Kibana

🚀 Установка и запуск

Клонируем репозиторий:

git clone https://github.com/your-repo.git
cd your-repo

Заполняем inventory.ini:

[monitoring]
192.168.1.100 ansible_user=ubuntu

Запускаем плейбук:

ansible-playbook -i inventory.ini site.yml

🔧 Переменные по умолчанию

Настройки можно изменить в defaults/main.yml каждой роли. Пример для Fluent Bit:

elasticsearch_host: "192.168.1.100"
elasticsearch_port: 9200
fluentbit_log_level: "info"

🛠️ Проверка работы

После успешного развертывания убедитесь, что сервисы работают:

Prometheus: http://<IP>:9090

Elasticsearch: http://<IP>:9200

Kibana: http://<IP>:5601
