域名配置
- 授权服务器 资源服务器 保持同域
- 后端服务器  前台服务器 保持同域
- 后端服务器 授权服务器保证二级同域

UOS、Deepin
- echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
- sudo sysctl --system

第一次down 停止gradle引入,配置jdk版本 配置gradle 然后 重载gradle
\- 禁止使用JPA动态数据库
  - (原因:1.与webflux框架概念冲突,必须要返回Mono链,如果返回jpa数据是无法被管理的,2.切换逻辑复杂，不可预判性问题)
  - r2dbc路由依赖:
    - org.springbooz.boot:booz-boot-starter-data-r2dbc-router:2.4.1-RELEASE
    - r2dbc路由框架,无兼容性的复杂性问题,所以框架逻辑更加简单
    org.springbooz.boot:spring-boot-starter-data-r2dbc:2.4.1'
- 遵守Reactive反应编程开发规范`
- IDEA开发 setting=> gradle IDEA模式
- IDEA开发 setting=> annotation 开启注解
- IDEA开发 setting=>开启setting=>eslint auto configuration 与fix on save


- VUE 菜单与路由与区域
  - [菜单配置](./web/src/router/menus/index.ts "标题")
    - import modules from 'globby!/@/router/menus/modules/**/*.@(ts)'
    - 改成想要的位置
    - [菜单目录](./web/src/router/menus "标题")
  - [路由配置](./web/src/router/routes/index.ts "标题")
    - import modules from 'globby!/@/router/routes/modules/**/*.@(ts)'
    - 改成想要的位置
    - [路由目录](./web/src/router/routes "标题")
  - [区域配置](./web/src/locales/lang/zh_CN/routes "标题")
- 架构
    - 后端
        - webflux
        - spring cloud alibaba dubbo 微服务 单机运行 
        - 动态数据源 路由(无兼容性的复杂性问题,理论比较稳定)
           方法级
             @R2dbcRouter(databaseName = "public")
           业务级    
               ```
                schemaRouterService.bind("nc", "public1", () ->
                
                                entityTemplate.select(Jigou.class).from("jigou").all()
                        )
              ```
    - 目录
     - 后台src项目目录
        - domain
            entity
            vo
            dto
        - feign 微服务接口
        - repo 数据仓库
        - rest rest controler 
        
     - 前端
          - vue3  composition api : 反应式语法
          - vben: admin模板 
          - vue ant: 组件库
          - typescript： 高阶js
          - sass: 高阶css
    

- 创建模块
    - modules 新建模块(复制其他模块)
    - setting.gradle 使模块有效
    - build.gradle 在主模块中引入模块
- 微服务
```
    webflux微服务方案
        openfeign方案
            目前webflux不支持feign
        dubbo方案
    层级: dubbo - rest - service - r2dbc
    service必须返回Mono或fulx（非阻塞线程中的方法，不能使用）
```
- 服务
```
Spring Boot Admin 2.3.1 localhost:端口/applications
Swagger 3.0  localhost:端口/doc.html
```
- vue idea 语法设置
    开启eslint
    关闭tslint:原因 eslint包含tslint检测，不需要tslint检测


统一本地开发域名调整(用utools写在hosts中):
    127.0.0.1 apincdev.chinabooz.com
    127.0.0.1 accountdev.chinabooz.com
前台访问:
    apincdev.chinabooz.com:3103
后端接口:
- 授权服务器 资源服务器 保持同域
- 后端服务器  前台服务器 保持同域
- 后端服务器 授权服务器保证二级同域
 
- 指定好版本后,清除IDEA缓存重启
