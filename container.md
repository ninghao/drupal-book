# 容器

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

创建的控制器，Drupal 会自动去创建一个控制器对象。这次我们让自己的控制器继承了 ControllerBase 类，并且在控制器里实施了 create 方法，在这个方法里可以让我们自己去创建控制器对象，方法有个参数就是 $container，这是 Drupal 的容器对象，在这个对象里我们用 get 方法得到了指定的服务：ninghao.hello，在创建控制器对象的时候，我们把这个服务对象交给了控制器。

在控制器里添加 \_\_construct 函数，它接收一个参数，就是传递给它的服务对象，这里就是 Greeting 对象。在类里添加一个属性叫 $greeting，把创建控制器对象的时候传递过来的 $greeting 服务对象交给这个控制器的 $greeting 属性里面。这样我们就可以在控制器里使用这个服务对象里的方法了。比如 sayHello\(\) 就是 Greeting 服务里的一个方法。

