# Simple
Simple examples of how to work with SMS-IO.RU API

## Send message examples

### PHP
- [composer.json](http://github.com/smsioru/simple-php-example/composer.json)
```json
{
  "require": {
    "rmccue/requests": ">=1.0"
  }
}
```
- [simple-example.php](http://github.com/smsioru/simple-php-example/simple-example.php)
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
- [requirements.txt](http://github.com/smsioru/simple-python-example/requirements.txt)
```
requests
```
- [simple-example.py](http://github.com/smsioru/simple-python-example/simple-example.py)
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
