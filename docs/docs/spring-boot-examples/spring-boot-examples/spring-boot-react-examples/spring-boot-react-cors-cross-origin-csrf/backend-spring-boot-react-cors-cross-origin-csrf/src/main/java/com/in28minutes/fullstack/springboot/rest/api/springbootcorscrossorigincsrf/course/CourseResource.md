# 基础信息

|      |      |
|------|------|
| 名称 | CourseResource |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-react-examples/spring-boot-react-cors-cross-origin-csrf/backend-spring-boot-react-cors-cross-origin-csrf/src/main/java/com/in28minutes/fullstack/springboot/rest/api/springbootcorscrossorigincsrf/course/CourseResource.java |
| 包名 | com.in28minutes.fullstack.springboot.rest.api.springbootcorscrossorigincsrf.course |
| 依赖项 | ['java.util.List', 'org.springframework.beans.factory.annotation.Autowired', 'org.springframework.web.bind.annotation.CrossOrigin', 'org.springframework.web.bind.annotation.GetMapping', 'org.springframework.web.bind.annotation.PathVariable', 'org.springframework.web.bind.annotation.RestController'] |
| 概述说明 | 允许跨域访问，获取用户所有课程列表。 |

# 说明

该功能允许跨域访问，旨在获取指定用户名下的所有课程列表。通过此功能，系统能够跨域请求数据，确保用户在不同域之间无缝获取相关课程信息。这一设计提高了系统的灵活性和用户体验，使得数据获取更加便捷和高效。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CourseResource | class | 允许跨域访问，获取指定用户名下的所有课程列表。 |



## 类 CourseResource

|      |      |
|------|------|
| 访问范围 | @CrossOrigin(origins = {"http://localhost:3000", "http://localhost:4200"});@RestController;public |
| 类型 | class |
| 名称 | CourseResource |
| 说明 | 允许跨域访问，获取指定用户名下的所有课程列表。 |


### UML类图

```mermaid
classDiagram
    class CourseResource {
        -CoursesHardcodedService courseManagementService
        +getAllCourses(String username) List~Course~
    }
    class CoursesHardcodedService {
        +findAll() List~Course~
    }
    class Course {
        // Course class details not provided in the code
    }
    CourseResource --> CoursesHardcodedService : 依赖
    CoursesHardcodedService --> Course : 依赖
```

这段代码定义了一个名为 `CourseResource` 的 REST 控制器类，它通过 `@CrossOrigin` 注解允许来自特定源的跨域请求。`CourseResource` 类依赖于 `CoursesHardcodedService` 服务类来获取课程数据。`CoursesHardcodedService` 类提供了一个 `findAll` 方法，返回一个 `Course` 对象的列表。`CourseResource` 类中的 `getAllCourses` 方法通过调用 `courseManagementService.findAll()` 来获取所有课程，并将其返回给客户端。


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

这段代码定义了一个名为`CourseResource`的REST控制器类，使用`@CrossOrigin`注解允许跨域请求，并通过`@Autowired`注入`CoursesHardcodedService`服务。`getAllCourses`方法通过`@GetMapping`映射到`/instructors/{username}/courses`路径，调用`courseManagementService.findAll()`获取所有课程列表。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| courseManagementService | CoursesHardcodedService | 自动注入课程管理服务实例。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getAllCourses | List<Course> | 通过用户名获取讲师所有课程的API接口。 |




