# 服务

控制器里别装太多逻辑，可以把逻辑单独拿出来，放到一个服务类里面。

文件：

```
modules/custom/ninghao/src/Service/Greeting.php
```

内容：

```php
<?php

namespace Drupal\ninghao\Service;

class Greeting {
  public function sayHello() {
    return 'hello';
  }
}
```

Controller：

```php
namespace Drupal\ninghao\Controller;

use Symfony\Component\HttpFoundation\Response;
use Drupal\ninghao\Service\Greeting;

class NinghaoController {
  public function hello() {
    $greeting = new Greeting();
    $hello = $greeting->sayHello();

    return new Response($hello);
  }
}
```



