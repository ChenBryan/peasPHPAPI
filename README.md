peasPHPAPI
====
简介:
一个简单 快捷 小巧 实用 的 PHPAPI [rest] 框架


---
 * 目前该API支持：
 *  
 *   跨域GET请求 JSONP ok 
 *   REST 方式请求  ok
 *   非跨域常规请求  ok
 *   验证请求，可以路由类Router的accessRBAC中接入第三方验证,也可以自己实行基于RBAC的用户机制
 *
 *   提供一个请求验证机制,适合请求一次有效，忽略相同1次以上的请求 :
 *       为第三方提供一个帐号和私钥【私钥也可以变相是用户的密码】  每次请求传递一个参数作为验证 md5（每次请求的url+请求类型【post,get等】+私钥） url理论是唯一,当然也可以多次md5,或者md5(sha1(data))等
 *   peasPHPAPI 做下相应的调整，每次验证，这个值与自己构建的是不是一样的。
 *   当然，这种验证，只能验证请求合法，但别人可以复制重复发请求，而造成麻烦.
 *
 *   只有接入网站的用户权限，验证网站的用户才能使用,这样才能满足需求.
 *
 *   配置文件里，可以配置那些目录需要权限验证，待实现.  
 *   todo : 缓存 
 * 结构：
 *   peasPHPAPI
 *   -index.php
 *   -config.php
 *   +lib
 *   +project  [PHP API 支持目录包文件夹,命名空间]
 *    -按照模块功能自己建立文件夹
 *    -
 *    -
 * 返回数据：
 *    json 与 xml 两种方式 amf还没有完善


eg:
---
   http://127.0.0.1/peasPHPAPI/index.php?r=json/icom.qti/Qti/getQti&info={"a":1,"b":2,"c":3,"d":4,"e":5}
   http://127.0.0.1/peasPHPAPI/index.php?r=json/icom.qti/Qti/testDB&info={"name":"cwh"}
   http://127.0.0.1/peasPHPAPI/index.php?r=json/icom.qti/Qti/testupdatedb&info={"age":20,"id":8}
   http://127.0.0.1/peasPHPAPI/index.php?r=json/icom.qti/Qti/testpredb&info={"name":"cwh"}
   http://127.0.0.1/peasPHPAPI/index.php?r=json/icom.qti/Qti/testpreupdatedb&info={"age":21,"id":8}
   http://127.0.0.1/peasPHPAPI/index.php?r=json/rest.site/User/rest&info={"id":8}
 
