# google-url-shortner-codeigniter
This is based on the repository (https://github.com/sebi/googl-php/blob/master/Googl.class.php) but tweaked as model to work with codeigniter (just to have url shortening /expand from goo.gl)

Functions
---------
Theis model currently supports 2 methods:
  * *Shorten* a URL
  * *Expand* (look up) an already shortened URL

Usage
-----
Place this model inside your models folder and consume like below in your controller

```
function urlshort()
 {
  $this->load->model('Urlshortner_model');
  $url = "https://retainly.co";
  $shorten = $this->Urlshortner_model->shorten($url);
  echo $shorten;
 }

 function urlexpand()
 {
    $this->load->model('Urlshortner_model');
    $url = "https://goo.gl/YNwrbp";
    $expand = $this->Urlshortner_model->expand($url);
    echo $expand;
 }
```

API key
-------
You will need an API key to use the the shortening service.

Learn more at https://developers.google.com/url-shortener/v1/getting_started#auth.

OAuth is not supported by this library. Please use the authentication via application key.

Further info
------------
For further information about Goo.gl and its API, please visit: https://developers.google.com/url-shortener/.
