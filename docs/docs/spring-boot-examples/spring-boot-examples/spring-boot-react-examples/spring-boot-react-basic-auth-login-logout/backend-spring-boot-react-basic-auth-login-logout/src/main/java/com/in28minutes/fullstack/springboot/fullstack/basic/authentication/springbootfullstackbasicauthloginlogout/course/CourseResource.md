# 基础信息

|      |      |
|------|------|
| 名称 | CourseResource |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-react-examples/spring-boot-react-basic-auth-login-logout/backend-spring-boot-react-basic-auth-login-logout/src/main/java/com/in28minutes/fullstack/springboot/fullstack/basic/authentication/springbootfullstackbasicauthloginlogout/course/CourseResource.java |
| 包名 | com.in28minutes.fullstack.springboot.fullstack.basic.authentication.springbootfullstackbasicauthloginlogout.course |
| 依赖项 | ['java.util.List', 'org.springframework.beans.factory.annotation.Autowired', 'org.springframework.web.bind.annotation.CrossOrigin', 'org.springframework.web.bind.annotation.GetMapping', 'org.springframework.web.bind.annotation.PathVariable', 'org.springframework.web.bind.annotation.RestController'] |
| 概述说明 | 允许跨域访问本地3000和4200端口，获取指定用户名的课程列表。 |

# 说明

该功能允许从本地3000和4200端口进行跨域访问，主要用于获取指定用户名的课程列表。通过跨域配置，确保不同端口间的数据传输顺畅，从而实现用户课程信息的查询与展示。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CourseResource | class | 跨域允许本地3000和4200端口，获取指定用户名的课程列表。 |



## 类 CourseResource

|      |      |
|------|------|
| 访问范围 | @CrossOrigin(origins = {"http://localhost:3000", "http://localhost:4200"});@RestController;public |
| 类型 | class |
| 名称 | CourseResource |
| 说明 | 跨域允许本地3000和4200端口，获取指定用户名的课程列表。 |


### UML类图

```mermaid
classDiagram
    class CourseResource {
        -CoursesHardcodedService courseManagementService
        +getAllCourses(String username) List~Course~
    }

    class CoursesHardcodedService {
        <<Interface>>
        +findAll() List~Course~
    }

    CourseResource --> CoursesHardcodedService : 依赖
```

类图描述：`CourseResource` 类是一个 REST 控制器，通过 `@CrossOrigin` 注解允许跨域请求，并依赖 `CoursesHardcodedService` 接口来获取课程数据。`CoursesHardcodedService` 是一个接口，定义了 `findAll` 方法，返回课程列表。`CourseResource` 类通过 `@Autowired` 注解注入 `CoursesHardcodedService` 的实现，并在 `getAllCourses` 方法中调用 `findAll` 方法获取所有课程。


### 内部方法调用关系图

```mermaid
graph TD
    A["类CourseResource"]
    B["注解: @CrossOrigin(origins = {'http://localhost:3000', 'http://localhost:4200'})"]
    C["注解: @RestController"]
    D["属性: @Autowired private CoursesHardcodedService courseManagementService"]
    E["方法: @GetMapping('/instructors/{username}/courses')"]
    F["方法参数: @PathVariable String username"]
    G["方法体: return courseManagementService.findAll()"]

    A --> B
    A --> C
    A --> D
    A --> E
    E --> F
    E --> G
```

这段代码定义了一个名为 `CourseResource` 的 REST 控制器类，使用 `@CrossOrigin` 注解允许来自指定域名的跨域请求。类中通过 `@Autowired` 注解自动注入了一个 `CoursesHardcodedService` 类型的服务对象。`getAllCourses` 方法通过 `@GetMapping` 注解映射到 `/instructors/{username}/courses` 路径，接收一个 `username` 路径变量，并调用 `courseManagementService.findAll()` 方法返回所有课程列表。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| courseManagementService | CoursesHardcodedService | 自动注入课程管理服务实例。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getAllCourses | List<Course> | 通过用户名获取所有课程的API接口。 |




