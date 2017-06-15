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

## 路由

文件：

```
modules/custom/ninghao/ninghao.routing.yml
```

内容：

```
hello:
  path: /ninghao/hello
  defaults:
    _controller: Drupal\ninghao\Controller\NinghaoController::hello
  requirements:
    _permission: 'access content'
```

## 控制器

文件：

```
modules/custom/ninghao/src/Controller/NinghaoController.php
```

内容：

```php
<?php

namespace Drupal\ninghao\Controller;
use Symfony\Component\HttpFoundation\Response;

class NinghaoController {
  public function hello() {
    return new Response('hello ~');
  }
}
```

## 服务

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



