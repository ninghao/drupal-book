# 控制器

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



