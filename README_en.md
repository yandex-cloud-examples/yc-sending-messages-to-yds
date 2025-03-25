# Examples of sending messages to Yandex Data Stream via HTTP without using third-party SDKs

The example demonstrates how to send messages to [Yandex Data Stream](https://yandex.cloud/ru/docs/data-streams/) via HTTP using Python 3 without using third-party SDK. It is based on <https://stackoverflow.com/questions/51991401/how-to-implement-amazon-kinesis-putmedia-method-using-python>.

## Before you begin

1. [Create](https://yandex.cloud/ru/docs/data-streams/operations/manage-streams#create-data-stream) a Yandex Data Stream data stream and save its full name. The name includes the stream name and the database identifier.
2. [Create](https://yandex.cloud/ru/docs/iam/operations/sa/create) a service account and assign (https://yandex.cloud/ru/docs/iam/operations/sa/assign-role-for-sa) it the yds.write role.
3. [Create](https://yandex.cloud/ru/docs/iam/operations/authentication/manage-access-keys#create-access-key) static access keys for the service account.

## Sending messages

1. Set the appropriate values for the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables to the static key identifier and its secret value.
2. Specify custom values in the `putrecord-http-example.py` script:
   * `--full-stream-name`: The full name of the data stream, for example, `/ru-central1/b2g6ad43m6he********/etn01eh5rn07********/<stream_name>`
   * `--message`: The message to send to Yandex Data Streams
3. Run the `putrecord-http-example.py` script.