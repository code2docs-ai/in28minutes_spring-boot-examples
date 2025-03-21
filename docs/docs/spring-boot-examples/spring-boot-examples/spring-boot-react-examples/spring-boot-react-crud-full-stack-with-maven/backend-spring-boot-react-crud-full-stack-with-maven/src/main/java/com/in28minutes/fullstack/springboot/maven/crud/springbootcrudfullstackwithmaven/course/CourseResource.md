# 基础信息

|      |      |
|------|------|
| 名称 | CourseResource |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-react-examples/spring-boot-react-crud-full-stack-with-maven/backend-spring-boot-react-crud-full-stack-with-maven/src/main/java/com/in28minutes/fullstack/springboot/maven/crud/springbootcrudfullstackwithmaven/course/CourseResource.java |
| 包名 | com.in28minutes.fullstack.springboot.maven.crud.springbootcrudfullstackwithmaven.course |
| 依赖项 | ['java.net.URI', 'java.util.List', 'org.springframework.beans.factory.annotation.Autowired', 'org.springframework.http.HttpStatus', 'org.springframework.http.ResponseEntity', 'org.springframework.web.bind.annotation.CrossOrigin', 'org.springframework.web.bind.annotation.DeleteMapping', 'org.springframework.web.bind.annotation.GetMapping', 'org.springframework.web.bind.annotation.PathVariable', 'org.springframework.web.bind.annotation.PostMapping', 'org.springframework.web.bind.annotation.PutMapping', 'org.springframework.web.bind.annotation.RequestBody', 'org.springframework.web.bind.annotation.RequestMapping', 'org.springframework.web.bind.annotation.RestController', 'org.springframework.web.servlet.support.ServletUriComponentsBuilder'] |
| 概述说明 | 课程管理API支持查询、删除、更新和创建课程操作。 |

# 说明

该代码实现了一个课程管理API，提供了对课程的基本操作功能。用户可以通过该API查询课程信息，删除现有课程，更新课程内容，以及创建新的课程。这些操作涵盖了课程管理的核心需求，使得用户可以方便地对课程数据进行增删改查。API的设计旨在简化课程管理流程，提高数据操作的效率和准确性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CourseResource | class | 该代码定义了一个课程管理API，支持查询、删除、更新和创建课程操作。 |



## 类 CourseResource

|      |      |
|------|------|
| 访问范围 | @CrossOrigin(origins = {"http://localhost:3000", "http://localhost:4200"});@RestController;@RequestMapping("/instructors/{username}/courses");public |
| 类型 | class |
| 名称 | CourseResource |
| 说明 | 该代码定义了一个课程管理API，支持查询、删除、更新和创建课程操作。 |


### UML类图

```mermaid
classDiagram
    class CourseResource {
        -CoursesHardcodedService courseManagementService
        +List~Course~ getAllCourses(String username)
        +Course getCourse(String username, long id)
        +ResponseEntity~Void~ deleteCourse(String username, long id)
        +ResponseEntity~Course~ updateCourse(String username, long id, Course course)
        +ResponseEntity~Void~ createCourse(String username, Course course)
    }

    class CoursesHardcodedService {
        +List~Course~ findAll()
        +Course findById(long id)
        +Course deleteById(long id)
        +Course save(Course course)
    }

    class Course {
        // Course类的内容未在代码中定义，假设它有id等属性
    }

    CourseResource --> CoursesHardcodedService : 依赖
    CoursesHardcodedService --> Course : 依赖
```

### 描述
`CourseResource` 是一个Spring Boot的REST控制器，用于处理与课程相关的HTTP请求。它依赖于 `CoursesHardcodedService` 服务类来执行具体的业务逻辑，如查找、删除、更新和创建课程。`CoursesHardcodedService` 类提供了对课程数据的操作，而 `Course` 类表示课程实体。控制器通过不同的HTTP方法（GET、DELETE、PUT、POST）来响应客户端请求，并返回相应的HTTP状态码和资源。


### 内部方法调用关系图

```mermaid
graph TD
    A["类CourseResource"]
    B["注解: @CrossOrigin(origins = {'http://localhost:3000', 'http://localhost:4200'})"]
    C["注解: @RestController"]
    D["注解: @RequestMapping('/instructors/{username}/courses')"]
    E["属性: @Autowired private CoursesHardcodedService courseManagementService"]
    F["方法: @GetMapping() public List<Course> getAllCourses(@PathVariable String username)"]
    G["方法: @GetMapping('/{id}') public Course getCourse(@PathVariable String username, @PathVariable long id)"]
    H["方法: @DeleteMapping('/{id}') public ResponseEntity<Void> deleteCourse(@PathVariable String username, @PathVariable long id)"]
    I["方法: @PutMapping('/{id}') public ResponseEntity<Course> updateCourse(@PathVariable String username, @PathVariable long id, @RequestBody Course course)"]
    J["方法: @PostMapping() public ResponseEntity<Void> createCourse(@PathVariable String username, @RequestBody Course course)"]
    K["调用: courseManagementService.findAll()"]
    L["调用: courseManagementService.findById(id)"]
    M["调用: courseManagementService.deleteById(id)"]
    N["调用: courseManagementService.save(course)"]
    O["调用: ServletUriComponentsBuilder.fromCurrentRequest().path('/{id}').buildAndExpand(createdCourse.getId()).toUri()"]
    P["输出: System.out.println(courseManagementService.findById(createdCourse.getId()))"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    A --> I
    A --> J
    F --> K
    G --> L
    H --> M
    I --> N
    J --> N
    J --> O
    J --> P
```

**描述：**
这段代码定义了一个名为 `CourseResource` 的 REST 控制器类，用于处理与课程相关的 HTTP 请求。类中包含多个方法，分别用于获取所有课程、获取指定课程、删除课程、更新课程和创建课程。每个方法都通过 `@PathVariable` 或 `@RequestBody` 注解获取请求参数，并调用 `CoursesHardcodedService` 服务类中的方法来执行具体的业务逻辑。代码还使用了 `@CrossOrigin` 注解来允许跨域请求，并通过 `@RestController` 和 `@RequestMapping` 注解定义了请求的路径。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| courseManagementService | CoursesHardcodedService | 自动注入课程管理服务实例。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getAllCourses | List<Course> | 通过Get请求获取所有课程信息。 |
| createCourse | ResponseEntity<Void> | 创建课程API，保存课程并返回资源URL。 |
| getCourse | Course | 通过ID获取课程信息的API接口。 |
| deleteCourse | ResponseEntity<Void> | 删除课程接口，根据ID删除课程，成功返回204，失败返回404。 |
| updateCourse | ResponseEntity<Course> | 通过ID更新课程信息，返回更新后的课程状态。 |




