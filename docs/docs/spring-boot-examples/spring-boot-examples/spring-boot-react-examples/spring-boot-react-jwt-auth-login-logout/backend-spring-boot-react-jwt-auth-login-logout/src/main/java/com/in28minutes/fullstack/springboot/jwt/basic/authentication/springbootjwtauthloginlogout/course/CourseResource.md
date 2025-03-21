# 基础信息

|      |      |
|------|------|
| 名称 | CourseResource |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-react-examples/spring-boot-react-jwt-auth-login-logout/backend-spring-boot-react-jwt-auth-login-logout/src/main/java/com/in28minutes/fullstack/springboot/jwt/basic/authentication/springbootjwtauthloginlogout/course/CourseResource.java |
| 包名 | com.in28minutes.fullstack.springboot.jwt.basic.authentication.springbootjwtauthloginlogout.course |
| 依赖项 | ['java.util.List', 'org.springframework.beans.factory.annotation.Autowired', 'org.springframework.web.bind.annotation.CrossOrigin', 'org.springframework.web.bind.annotation.GetMapping', 'org.springframework.web.bind.annotation.PathVariable', 'org.springframework.web.bind.annotation.RestController'] |
| 概述说明 | 跨域控制器允许3000和4200端口访问，获取用户课程列表。 |

# 说明

跨域控制器配置允许本地3000和4200端口的访问请求，并支持获取指定用户名下的所有课程列表。该功能确保了不同端口间的数据交互，同时通过用户名筛选相关课程信息，提升了系统的灵活性和数据获取的精准性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CourseResource | class | 跨域控制器允许本地3000和4200端口访问，获取指定用户名下的所有课程列表。 |



## 类 CourseResource

|      |      |
|------|------|
| 访问范围 | @CrossOrigin(origins = {"http://localhost:3000", "http://localhost:4200"});@RestController;public |
| 类型 | class |
| 名称 | CourseResource |
| 说明 | 跨域控制器允许本地3000和4200端口访问，获取指定用户名下的所有课程列表。 |


### UML类图

```mermaid
classDiagram
    class CourseResource {
        -CoursesHardcodedService courseManagementService
        +List~Course~ getAllCourses(String username)
    }

    class CoursesHardcodedService {
        +List~Course~ findAll()
    }

    class Course {
        // Course class details not provided in the code
    }

    CourseResource --> CoursesHardcodedService : 依赖
    CoursesHardcodedService --> Course : 依赖
```

**描述：**
`CourseResource` 类是一个Spring Boot的REST控制器，用于处理与课程相关的HTTP请求。它依赖于 `CoursesHardcodedService` 服务类来获取所有课程的数据。`CoursesHardcodedService` 类提供了一个 `findAll()` 方法，返回一个 `Course` 对象的列表。`Course` 类的具体细节在代码中未提供，但可以推测它表示课程的相关信息。


### 内部方法调用关系图

```mermaid
graph TD
    A["类CourseResource"]
    B["注解: @CrossOrigin(origins = {'http://localhost:3000', 'http://localhost:4200'})"]
    C["注解: @RestController"]
    D["属性: @Autowired CoursesHardcodedService courseManagementService"]
    E["方法: @GetMapping('/instructors/{username}/courses') List<Course> getAllCourses(@PathVariable String username)"]
    F["调用: courseManagementService.findAll()"]

    A --> B
    A --> C
    A --> D
    A --> E
    E --> F
```

**描述：**  
该代码定义了一个名为`CourseResource`的类，用于处理与课程相关的REST请求。类上使用了`@CrossOrigin`注解，允许来自指定来源的跨域请求，并通过`@RestController`注解将其标记为REST控制器。类中注入了一个`CoursesHardcodedService`实例，用于管理课程数据。`getAllCourses`方法通过`@GetMapping`注解映射到特定URL路径，并调用`courseManagementService.findAll()`方法获取所有课程列表。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| courseManagementService | CoursesHardcodedService | 自动注入课程管理服务实例。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getAllCourses | List<Course> | 获取指定用户名下的所有课程列表。 |




