# TODO API using Serverless framework + Python


based on https://github.com/serverless/examples/tree/master/aws-python-rest-api-with-dynamodb

# Serverless Deploy
```sh
$ sls deploy
Serverless: Packaging service...
Serverless: Excluding development dependencies...
Serverless: Creating Stack...
Serverless: Checking Stack create progress...
.....
Serverless: Stack create finished...
Serverless: Uploading CloudFormation file to S3...
Serverless: Uploading artifacts...
Serverless: Uploading service .zip file to S3 (3.34 KB)...
Serverless: Validating template...
Serverless: Updating Stack...
Serverless: Checking Stack update progress...
......................................................................................................
Serverless: Stack update finished...
Service Information
service: awesome-todo-api
stage: dev
region: us-east-1
stack: awesome-todo-api-dev
api keys:
  None
endpoints:
  POST - https://1vik4uugi9.execute-api.us-east-1.amazonaws.com/dev/todos
  GET - https://1vik4uugi9.execute-api.us-east-1.amazonaws.com/dev/todos
  GET - https://1vik4uugi9.execute-api.us-east-1.amazonaws.com/dev/todos/{id}
  PUT - https://1vik4uugi9.execute-api.us-east-1.amazonaws.com/dev/todos/{id}
  DELETE - https://1vik4uugi9.execute-api.us-east-1.amazonaws.com/dev/todos/{id}
functions:
  create: awesome-todo-api-dev-create
  list: awesome-todo-api-dev-list
  get: awesome-todo-api-dev-get
  update: awesome-todo-api-dev-update
  delete: awesome-todo-api-dev-delete
layers:
  None
```

## Usage

You can create, retrieve, update, or delete todos with the following commands:

### Create a Todo

```bash
curl -X POST https://XXXXXXX.execute-api.us-east-1.amazonaws.com/dev/todos --data '{ "text": "DevOps Your Serverless" }'
```

No output

### List all Todos

```bash
curl https://XXXXXXX.execute-api.us-east-1.amazonaws.com/dev/todos
```

Example output:
```bash
[{"text":"Deploy my first service","id":"ac90feaa11e6-9ede-afdfa051af86","checked":true,"updatedAt":1479139961304},{"text":"Learn Serverless","id":"206793aa11e6-9ede-afdfa051af86","createdAt":1479139943241,"checked":false,"updatedAt":1479139943241}]%
```

### Get one Todo

```bash
# Replace the <id> part with a real id from your todos table
curl https://XXXXXXX.execute-api.us-east-1.amazonaws.com/dev/todos/<id>
```

Example Result:
```bash
{"text":"Learn Serverless","id":"ee6490d0-aa11e6-9ede-afdfa051af86","createdAt":1479138570824,"checked":false,"updatedAt":1479138570824}%
```

### Update a Todo

```bash
# Replace the <id> part with a real id from your todos table
curl -X PUT https://XXXXXXX.execute-api.us-east-1.amazonaws.com/dev/todos/<id> --data '{ "text": "Learn Serverless", "checked": true }'
```

Example Result:
```bash
{"text":"Learn Serverless","id":"ee6490d0-aa11e6-9ede-afdfa051af86","createdAt":1479138570824,"checked":true,"updatedAt":1479138570824}%
```

### Delete a Todo

```bash
# Replace the <id> part with a real id from your todos table
curl -X DELETE https://XXXXXXX.execute-api.us-east-1.amazonaws.com/dev/todos/<id>
```

