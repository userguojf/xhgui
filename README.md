### 安装项目相关的第三方包（MongoDB）
```bash
composer install --ignore-platform-reqs

```

### 通过Composer安装&更新

````bash
composer require laynefyc/xhgui-chinese
````

### MongoDB 配置

```bash
mongo
use xhprof
//按照请求时间-设置过期
db.results.ensureIndex( { 'meta.request_ts' : 1 }, {expireAfterSeconds: 36000} )
db.results.ensureIndex( { 'meta.SERVER.REQUEST_TIME' : -1 } )
db.results.ensureIndex( { 'profile.main().wt' : -1 } )
db.results.ensureIndex( { 'profile.main().mu' : -1 } )
db.results.ensureIndex( { 'profile.main().cpu' : -1 } )
db.results.ensureIndex( { 'meta.url' : 1 } )
```