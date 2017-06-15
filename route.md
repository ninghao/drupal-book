# 路由

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

## 



