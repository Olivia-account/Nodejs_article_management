# 文章管理后台+个人中心
该项目代码整合了前端和后端，前端代码在/web目录下，其他目录代码都是后端代码.
代码中有详细的注释。

后端代码没有提交node_modules文件夹，需要：npm install

后端关于mysql连接的配置在 /db/index.js中，默认连接数据库名称my_db_01, 数据库用户root,数据库密码111111
后端关于jwt字符串有效期配置在 /config.js中，默认8h有效期
后端服务器启动在本地3007端口上

前端： http://localhost:3007
前端在login后将后端的jwt字符串存储在了localStorage中，退出登录时，会自动清除localStorage中的token
前端监听了ajax请求，在/web/assets/js/ajaxPre.js中，对于/my请求默认填充Authorization请求头字段，保证身份认证，若身份认证失败自动跳转到登录页面
                                                  对于所有的ajax请求url参数都自动拼接了http://127.0.0.1:3007前缀
                                                  
数据库是mysql，三张表，en_user、en_articles、en_article_cates

Postman后端接口调测工程：api_server.postman_collection.json
