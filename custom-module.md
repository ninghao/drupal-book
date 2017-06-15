# 自定义模块

文件：

```
modules/custom/ninghao/ninghao.info.yml
```

内容：

```
name: ninghao
type: module
description: 'ninghao'
package: Sample
core: 8.x
```

启用：

```
drupal module:install ninghao
```

## 

## 容器

把服务放到容器里，需要服务的时候从容器那里要。

```
drupal container:debug
```

文件：

```
modules/custom/ninghao/ninghao.services.yml
```

内容：

```
services:
  ninghao.hello:
    class: Drupal\ninghao\Service\Greeting
```

Controller：

```php
namespace Drupal\ninghao\Controller;

use Symfony\Component\HttpFoundation\Response;
use Drupal\ninghao\Service\Greeting;
use Drupal\Core\Controller\ControllerBase;
use Symfony\Component\DependencyInjection\ContainerInterface;

class NinghaoController extends ControllerBase {
  private $greeting;

  public function __construct(Greeting $greeting) {
    $this->greeting = $greeting;
  }

  public function hello() {
    $hello = $this->greeting->sayHello();

    return new Response($hello);
  }

  public static function create(ContainerInterface $container) {
    $greeting = $container->get('ninghao.hello');
    return new static($greeting);
  }
}
```



