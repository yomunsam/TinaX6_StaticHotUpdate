# TinaX6_StaticHotUpdate
Tina X6 Framework静态热更新 服务端模板

## Json配置说明


### version

| key | type  | desc |
|-----|-----|-----|
| version | `int` | 版本号 | 
| name | `string` | 版本名 |
| type | `string` | 更新类型|
| url | `string` | 更新url |
| force | `bool` | 是否强制更新 |

**type** type的值约定如下：
    - "pkg" : 增量更新
        - 增量更新时，url填写TinaX增量更新包下载路径，如以"http/https"开头，则直接访问该路径下载，否则系统将尝试访问相对路径 `/pkg/xxx`进行下载
    - "page"：调用浏览器打开网页，而非直接下载
    - "full": 整包更新，即直接下载平台安装包或跳转应用商店