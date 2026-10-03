# ksd-test-framework

![tests](https://github.com/g-alex/ksd-test-framework/actions/workflows/tests.yml/badge.svg)

UI-тестовый фреймворк для интернет-магазина [ksd.ua](https://ksd.ua/) — финальный проект курса AQA (Dan.It Education).

**Стек:** Java 26 · Maven · Selenide (Selenium WebDriver) · TestNG · Allure · REST Assured (клиент TestRail API)

## Структура

| Пакет | Что |
|---|---|
| `ksd.pages` | Page Object: HomePage, SearchResultPage, ProductPage, CartPage, CategoryPage |
| `ksd.tests` | BaseTest + тестовые классы: Search (6), Category (5), Cart (5) |
| `ksd.testrail` | Клиент TestRail API, отправка результатов в @AfterMethod |

## Запуск

Требуется JDK 26, Maven и установленный Chrome/Chromium (драйвер скачивается Selenide автоматически).

```bash
mvn test                      # все 16 тестов
mvn test -Dtest=CartTests     # один класс
allure serve target/allure-results   # отчёт Allure
```

TestRail-интеграция опциональна, включается переменными окружения:
`TESTRAIL_URL`, `TESTRAIL_EMAIL`, `TESTRAIL_API_KEY`.
Без них тесты выполняются, отправка результатов пропускается.

## Учебный репозиторий

Полный курс (домашние задания по Java, API- и UI-тестированию, Cucumber BDD):
[aqa-java-danit](https://github.com/g-alex/aqa-java-danit)
