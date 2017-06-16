# 事件

```
modules/custom/ninghao/src/Service/NinghaoListener.php
```

```php
namespace Drupal\ninghao\Service;
use Symfony\Component\EventDispatcher\EventSubscriberInterface;

class NinghaoListener implements EventSubscriberInterface {
  public function onKernelRequest($event) {

  }
  
  public static function getSubscribeEvents() {
    return [
      KernelEvents::REQUEST => 'onKernelRequest'
    ];
  }
}
```

```
modules/custom/ninghao/ninghao.services.yml
```

```
parameters:
  ninghao.hello.use_key_value_cache: true
services:
  ninghao.hello:
    class: Drupal\ninghao\Service\Greeting
    arguments:
      - '@keyvalue'
      - %ninghao.hello.use_key_value_cache%
  ninghao.listener:
    class: Drupal\ninghao\Service\NinghaoListener
    arguments: []
    tags:
      - { name: event_subscriber }
```



