# 核心服务

Drupal 本身提供了很多服务可以用。

使用 Drupal Console 检查一下容器里的服务：

```
drupal container:debug
```

用一下核心的 logger.factory 服务：

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
    $hello = $this->greeting->sayHello();
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

访问 ninghao/hello，然后在 admin/reports/dblog 查看日志，应该会出现一个 hello 。

