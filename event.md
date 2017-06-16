# 事件

```
modules/custom/ninghao/src/Service/NinghaoListener.php
```

```php
namespace Drupal\ninghao\Service;
use Symfony\Component\EventDispatcher\EventSubscriberInterface;
use Symfony\Component\HttpKernel\Event\GetResponseEvent;
use Symfony\Component\HttpKernel\KernelEvents;
use Drupal\Core\Logger\LoggerChannelFactoryInterface;

class NinghaoListener implements EventSubscriberInterface {
  public function __construct(LoggerChannelFactoryInterface $loggerFactory) {
    $this->loggerFactory = $loggerFactory;
  }

  public function onKernelRequest(GetResponseEvent $event) {
    $request = $event->getRequest();
    $shouldHello = $request->query->get('hello');

    if ($shouldHello) {
      $this->loggerFactory->get('default')
        ->debug('hello');
    }
  }

  public static function getSubscribedEvents() {
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
    arguments: ['@logger.factory']
    tags:
      - { name: event_subscriber }
```



