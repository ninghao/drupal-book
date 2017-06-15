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



