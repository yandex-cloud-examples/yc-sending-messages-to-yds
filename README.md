# Примеры отправки сообщений в Yandex Data Stream по HTTP без использования сторонних SDK

Данный пример демонстрирует как отправлять сообщения в [Yandex Data Stream](https://yandex.cloud/ru/docs/data-streams/) по HTTP на python3, без использования сторонних SDK. Сделан на основе <https://stackoverflow.com/questions/51991401/how-to-implement-amazon-kinesis-putmedia-method-using-python>.


## Перед началом работы

1. [Создайте](https://yandex.cloud/ru/docs/data-streams/operations/manage-streams#create-data-stream) поток данных Yandex Data Stream и сохраните его полное имя. Имя содержит название потока и идентификатор базы данных.
1. [Создайте](https://yandex.cloud/ru/docs/iam/operations/sa/create) сервисный аккаунт и [назначьте](https://yandex.cloud/ru/docs/iam/operations/sa/assign-role-for-sa) ему роль `yds.write`.
1. Для сервисного аккаунта [создайте](https://yandex.cloud/ru/docs/iam/operations/authentication/manage-access-keys#create-access-key) статические ключи доступа.


## Отправка сообщений

1. Задайте для переменных окружения `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY` соответствующие значения идентификатора статического ключа и его секретное значение.
1. Укажите пользовательские значения в скрипте `putrecord-http-example.py`:
    * `--full-stream-name` — полное имя потока данных, например `/ru-central1/b2g6ad43m6he********/etn01eh5rn07********/<имя_потока>`
    * `--message` — сообщение для отправки в Yandex Data Stream.
1. Выполните скрипт `putrecord-http-example.py`.

