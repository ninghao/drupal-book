# 服务中的服务

```
modules/custom/ninghao/src/Service/Greeting.php
```

```php
namespace Drupal\ninghao\Service;
use Drupal\Core\KeyValueStore\KeyValueFactoryInterface;

class Greeting {
  private $keyValueFactory;

  public function __construct(KeyValueFactoryInterface $keyValueFactory) {
    $this->keyValueFactory = $keyValueFactory;
  }

  public function sayHello() {
    $key = 'ninghao_greeting_1';
    $store = $this->keyValueFactory->get('ninghao');
    if ($store->has($key)) {
      return $store->get($key);
    }
    sleep(2);
    $string = 'hello';
    $store->set($key, $string);
    return $string;
  }
}
```

```
modules/custom/ninghao/src/Controller/NinghaoController.php
```

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
    // $keyValueStore = $this->keyValue('ninghao');

    $hello = $this->greeting->sayHello();
    // $keyValueStore->set('greeting', $hello);
    // $hello = $keyValueStore->get('greeting');
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

services

```
modules/custom/ninghao/ninghao.services.yml
```

```
services:
  ninghao.hello:
    class: Drupal\ninghao\Service\Greeting
    arguments:
      - '@keyvalue'
```

## 配置

```
sites/development.services.yml
```

```
parameters:
  http.response.debug_cacheability_headers: true
  twig.config:
    debug: true
    cache: false
  ninghao.hello.use_key_value_cache: false
services:
  cache.backend.null:
    class: Drupal\Core\Cache\NullBackendFactory

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
```

```
modules/custom/ninghao/src/Service/Greeting.php
```

```
namespace Drupal\ninghao\Service;
use Drupal\Core\KeyValueStore\KeyValueFactoryInterface;

class Greeting {
  private $keyValueFactory;
  private $useCache;

  public function __construct(KeyValueFactoryInterface $keyValueFactory, $useCache) {
    $this->keyValueFactory = $keyValueFactory;
    $this->useCache = $useCache;
  }

  public function sayHello() {
    $key = 'ninghao_greeting_1';
    $store = $this->keyValueFactory->get('ninghao');
    if ($this->useCache && $store->has($key)) {
      return $store->get($key);
    }
    sleep(2);
    $string = 'hello';
    $store->set($key, $string);
    return $string;
  }
}
```



