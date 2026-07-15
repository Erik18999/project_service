# Project Service

## Описание

Микросервис для управления проектами в веб-приложении **CorporationX**. Отвечает за создание и организацию проектов, сбор команды для их реализации, открытие стажировок (чтобы начинающие специалисты могли поработать над реальными проектами под руководством ментора), а также размещение вакансий для поиска специалистов.

## Реализованные фичи

### Jacoco для project_service
В сервис подключён и настроен JaCoCo (Java Code Coverage) — инструмент для измерения покрытия кода тестами. Генерирует отчёты о покрытии (общий процент, покрытие по классам, методам и строкам кода), которые помогают оценить эффективность тестирования и выявить непокрытые участки кода.

- [`build.gradle.kts`](build.gradle.kts) — подключён плагин `jacoco`, настроена генерация отчёта (`jacocoTestReport`) в форматах XML и HTML, автоматически запускается после тестов

**Технологии:** JaCoCo (Java Code Coverage)

## CI

Настроен GitHub Actions пайплайн для проверки Pull Request'ов в ветку `werewolf-master-stream8`: сборка проекта, прогон тестов, автоматический комментарий в PR при падении сборки.

- [`.github/workflows/ci.yml`](.github/workflows/ci.yml)

## Стек

- Java 17
- Spring Boot 3
- Spring Data JPA
- PostgreSQL
- Redis
- Liquibase
- MapStruct
- Feign Client
- Amazon S3 SDK
- Testcontainers (PostgreSQL, Redis)
- Checkstyle
- JaCoCo
- JUnit 5, AssertJ

## Запуск

### Предварительные требования
- Docker и Docker Compose
- JDK 17

### Шаги

1. Поднять инфраструктуру (Postgres, Redis, MinIO, Kafka):
```bash
git clone https://github.com/Erik18999/infra.git
cd infra
./run.sh
```
2. Склонировать и запустить сам сервис (порт 8082):
```bash
git clone https://github.com/Erik18999/project_service.git
cd project_service
```
Открыть проект в IntelliJ IDEA и запустить [`ProjectServiceApplication`](src/main/java/faang/school/projectservice/ProjectServiceApplication.java).

## Swagger UI

http://localhost:8082/swagger-ui.html
