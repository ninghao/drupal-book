# KeyValue

```php
namespace Drupal\ninghao\Controller;

use Symfony\Component\HttpFoundation\Response;
use Drupal\ninghao\Service\Greeting;
use Drupal\Core\Controller\ControllerBase;
use Drupal\Core\Logger\LoggerChannelFactoryInterface;
use Symfony\Component\DependencyInjection\ContainerInterface;

class NinghaoController extends ControllerBase {
  private $greeting;
  private $loggerFactoryService;

  public function __construct(Greeting $greeting, LoggerChannelFactoryInterface $loggerFactoryService) {
    $this->greeting = $greeting;
    $this->loggerFactoryService = $loggerFactoryService;
  }

  public function hello() {
    $keyValueStore = $this->keyValue('ninghao');

    // $hello = $this->greeting->sayHello();
    // $keyValueStore->set('greeting', $hello);
    $hello = $keyValueStore->get('greeting');
    $this->loggerFactoryService->get('default')
      ->debug($hello);

    return new Response($hello);
  }

  public static function create(ContainerInterface $container) {
    $greeting = $container->get('ninghao.hello');
    $loggerFactoryService = $container->get('logger.factory');
    return new static($greeting, $loggerFactoryService);
  }
}
```

ControllerBase.php

```php
  protected function keyValue($collection) {
    if (!$this->keyValue) {
      $this->keyValue = $this->container()->get('keyvalue')->get($collection);
    }
    return $this->keyValue;
  }
```



