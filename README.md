cool-captcha
============

It is refined [cool-php-captcha](https://code.google.com/p/cool-php-captcha/) library rehosted on GitHub.

### Example of use
```php
<?php
require __DIR__.'/vendor/autoload.php';

session_start();
use CoolCaptcha\Captcha;
$captcha = new Captcha();

/** OPTIONAL configuration
$captcha->wordsFile = 'words/es.php';
$captcha->session_var = 'secretword';
$captcha->imageFormat = 'png';
$captcha->lineWidth = 3;
$captcha->scale = 3;
$captcha->blur = true;
$captcha->resourcesPath = "/var/cool-php-captcha/resources";
**/

/** OPTIONAL Simple autodetect language example
if (!empty($_SERVER['HTTP_ACCEPT_LANGUAGE'])) {
    $langs = array('en', 'es');
    $lang  = substr($_SERVER['HTTP_ACCEPT_LANGUAGE'], 0, 2);
    if (in_array($lang, $langs)) {
        $captcha->wordsFile = "words/$lang.php";
    }
}
**/

// Image generation
$text = $captcha->createImage();
$_SESSION['text'] = $text;
```

### Generated captchas

![alt](examples/1.png?raw=true)
![alt](examples/2.png?raw=true)

![alt](examples/3.png?raw=true)
![alt](examples/4.png?raw=true)

![alt](examples/5.png?raw=true)
