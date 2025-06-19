## 📦 PHP + Nginx + Redis + Postgres + Monitoring Stack

### ⚙️ Требования
Для запуска проекта на локальной машине необходимо установить:

* `git`
* `docker`
* `docker compose`

---

## 🚀 Инструкция по запуску проекта

### 1. Склонируйте проект из репозитория:

```bash
git clone https://github.com/E1ites/Test-project
```

### 2. Запустите сборку и запуск контейнеров:

```bash
docker compose up -d --build
```

Флаг `--build` необходим, чтобы собрать контейнер с установленным `composer` и автоматически установить зависимости PHP (директория `vendor` создаётся внутри контейнера и в директории /app).

---

## 📂 Структура проекта

```text
.
├── app               # PHP-приложение
│   ├── composer.json
│   ├── composer.lock
│   ├── index.php
│   └── vendor/       # Генерируется автоматически после composer install
├── docker-compose.yml
├── Dockerfile
├── nginx.conf
├── prometheus.yml
└── .gitignore
```

---

## 📊 Мониторинг

В проект встроены:

* Prometheus
* Grafana
* Node Exporter
* cAdvisor
* nginx-exporter

### Порты:

* Приложение: http://ваш ip-aдрес:8000
* Prometheus: http://ваш ip-aдрес:9090
* Grafana: http://ваш ip-aдрес:3000
* Nginx Exporter: http://ваш ip-aдрес:9113/metrics
* Node Exporter: http://localhost:9100/metrics
* cAdvisor: http://localhost:8080/metrics

---

## 🔑 Доступ в Grafana:

* **Логин:** admin
* **Пароль:** pass

После входа можно подключить Prometheus как Data Source (обычно автоматически определяется по адресу `http://prometheus:9090`).

---

## 🛠️ Основные команды

### Просмотр логов:

```bash
docker compose logs -f
```

### Остановка контейнеров:

```bash
docker compose down
```

### Перезапуск проекта:

```bash
docker compose up -d --build
```

---
