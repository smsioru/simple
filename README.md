# Simple
Simple examples of how to work with SMS-IO.RU API

## Send message examples

### PHP
- [composer.json](https://github.com/smsioru/simple-php-example/blob/master/composer.json)
```json
{
  "require": {
    "rmccue/requests": ">=1.0"
  }
}
```
- [simple-example.php](https://github.com/smsioru/simple-php-example/blob/master/simple-example.php)
```php
<?php
require __DIR__ . '/vendor/autoload.php';

$API_BASE = 'https://api.sms-io.ru/sms-api/v1/message/';
$API_TOKEN = '_YOUR_TOKEN_HERE_';

$headers = array(
    'Authorization' => 'Token ' . $API_TOKEN,
);
$message = array(
    'external_id' => 'client_generated_id',
    'to_number' => '+71111111111',
    'text' => 'Hello!',
);

$response = Requests::post($API_BASE, $headers, $message);
```

### Python
- [requirements.txt](https://github.com/smsioru/simple-python-example/blob/master/requirements.txt)
```
requests
```
- [simple-example.py](https://github.com/smsioru/simple-python-example/blob/master/simple-example.py)
```python
import requests

API_BASE = 'https://api.sms-io.ru/sms-api/v1/message/'
API_TOKEN = '_YOUR_TOKEN_HERE_'

headers = {
    'Authorization': 'Token {}'.format(API_TOKEN)
}
message = {
    'external_id': 'client_generated_id',
    'to_number': '+71111111111',
    'text': 'Hello!',
}

response = requests.post(API_BASE, message, headers=headers)
```
