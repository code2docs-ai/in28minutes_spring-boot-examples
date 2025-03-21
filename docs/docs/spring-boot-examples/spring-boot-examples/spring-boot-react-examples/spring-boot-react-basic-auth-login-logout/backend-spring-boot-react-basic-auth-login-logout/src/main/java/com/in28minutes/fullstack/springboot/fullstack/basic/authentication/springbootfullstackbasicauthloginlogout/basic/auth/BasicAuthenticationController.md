# 基础信息

|      |      |
|------|------|
| 名称 | BasicAuthenticationController |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-react-examples/spring-boot-react-basic-auth-login-logout/backend-spring-boot-react-basic-auth-login-logout/src/main/java/com/in28minutes/fullstack/springboot/fullstack/basic/authentication/springbootfullstackbasicauthloginlogout/basic/auth/BasicAuthenticationController.java |
| 包名 | com.in28minutes.fullstack.springboot.fullstack.basic.authentication.springbootfullstackbasicauthloginlogout.basic.auth |
| 依赖项 | ['org.springframework.web.bind.annotation.CrossOrigin', 'org.springframework.web.bind.annotation.GetMapping', 'org.springframework.web.bind.annotation.RestController'] |
| 概述说明 | 跨域控制器处理本地请求并返回认证信息。 |

# 说明

跨域控制器负责处理本地请求，并返回相应的认证信息。该控制器确保在跨域场景下，本地请求能够被正确识别和处理，同时提供必要的认证数据，以保障系统的安全性和功能性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| BasicAuthenticationController | class | 跨域控制器处理本地请求，返回认证信息。 |



## 类 BasicAuthenticationController

|      |      |
|------|------|
| 访问范围 | @CrossOrigin(origins = {"http://localhost:3000", "http://localhost:4200"});@RestController;public |
| 类型 | class |
| 名称 | BasicAuthenticationController |
| 说明 | 跨域控制器处理本地请求，返回认证信息。 |


### UML类图

```mermaid
classDiagram
    class BasicAuthenticationController {
        +AuthenticationBean helloWorldBean()
    }

    class AuthenticationBean {
        -String message
        +AuthenticationBean(String message)
        +String getMessage()
        +void setMessage(String message)
        +String toString()
    }

    BasicAuthenticationController --> AuthenticationBean : 返回
```

这段代码定义了一个名为 `BasicAuthenticationController` 的 REST 控制器，它通过 `@CrossOrigin` 注解允许来自指定来源的跨域请求。控制器中包含一个 `@GetMapping` 注解的方法 `helloWorldBean`，该方法返回一个 `AuthenticationBean` 对象，该对象包含一条认证成功的消息。`AuthenticationBean` 类是一个简单的 POJO，包含一个消息字段及其 getter 和 setter 方法。


### 内部方法调用关系图

```mermaid
graph TD
    A["类BasicAuthenticationController"]
    B["注解: @CrossOrigin(origins = {'http://localhost:3000', 'http://localhost:4200'})"]
    C["注解: @RestController"]
    D["方法: @GetMapping(path = '/basicauth')"]
    E["方法: helloWorldBean()"]
    F["返回: new AuthenticationBean('You are authenticated')"]

    A --> B
    A --> C
    A --> D
    D --> E
    E --> F
```

这段代码定义了一个名为 `BasicAuthenticationController` 的控制器类，该类使用了 `@CrossOrigin` 和 `@RestController` 注解。`@CrossOrigin` 注解允许来自指定源（`http://localhost:3000` 和 `http://localhost:4200`）的跨域请求。`@RestController` 注解表明该类是一个 RESTful 控制器。类中包含一个 `@GetMapping` 注解的方法 `helloWorldBean()`，该方法处理路径为 `/basicauth` 的 GET 请求，并返回一个 `AuthenticationBean` 对象，该对象包含认证成功的消息。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| helloWorldBean | AuthenticationBean | 获取路径为"/basicauth"，返回认证信息"您已认证"。 |




