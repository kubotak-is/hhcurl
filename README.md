# php-curl-class

PHP Curl Class is an object-oriented wrapper of the PHP cURL extension.

### Quick Start and Examples

```php

$curl = new Curl\Curl();
$curl->get('http://www.example.com/');
```

```php
$curl = new Curl\Curl();
$curl->get('http://www.example.com/search', array(
    'q' => 'keyword',
));
```

```php
$curl = new Curl\Curl();
$curl->post('http://www.example.com/login/', array(
    'username' => 'myusername',
    'password' => 'mypassword',
));
// Or for json APIs
$curl->post('http://www.example.com/login/', json_encode(array(
    'username' => 'myusername',
    'password' => 'mypassword',
)));
```

```php
$curl = new Curl\Curl();
$curl->setBasicAuthentication('username', 'password');
$curl->setUserAgent('');
$curl->setReferrer('');
$curl->setHeader('X-Requested-With', 'XMLHttpRequest');
$curl->setCookie('key', 'value');
$curl->get('http://www.example.com/');

if ($curl->error) {
    echo $curl->error_code;
}
else {
    echo $curl->response;
}

var_dump($curl->request_headers);
var_dump($curl->response_headers);
```

```php
$curl = new Curl\Curl();
$curl->setopt(CURLOPT_RETURNTRANSFER, TRUE);
$curl->setopt(CURLOPT_SSL_VERIFYPEER, FALSE);
$curl->get('https://encrypted.example.com/');
```

```php
$curl = new Curl\Curl();
$curl->put('http://api.example.com/user/', array(
    'first_name' => 'Zach',
    'last_name' => 'Borboa',
));
// Or for json APIs
$curl->put('http://api.example.com/user/', json_encode(array(
    'first_name' => 'Zach',
    'last_name' => 'Borboa',
)));
```

```php
$curl = new Curl\Curl();
$curl->patch('http://api.example.com/profile/', array(
    'image' => '@path/to/file.jpg',
));
// Or for json APIs
$curl->patch('http://api.example.com/profile/', json_encode(array(
    'image' => '@path/to/file.jpg',
)));
```

```php
$curl = new Curl\Curl();
$curl->delete('http://api.example.com/user/', array(
    'id' => '1234',
));
```

```php
$curl->close();
```

```php
// Example access to curl object.
curl_set_opt($curl->curl, CURLOPT_USERAGENT, 'Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1');
curl_close($curl->curl);
```
