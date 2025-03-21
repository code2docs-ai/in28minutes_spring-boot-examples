# 基础信息

|      |      |
|------|------|
| 名称 | CourseResource |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-react-examples/spring-boot-react-jpa-hibernate-with-h2-full-stack/backend-spring-boot-react-jpa-hibernate-with-h2-full-stack/src/main/java/com/in28minutes/fullstack/springboot/jpa/hibernate/springbootjpahibernatewithh2fullstack/course/CourseResource.java |
| 包名 | com.in28minutes.fullstack.springboot.jpa.hibernate.springbootjpahibernatewithh2fullstack.course |
| 依赖项 | ['java.net.URI', 'java.util.List', 'org.springframework.beans.factory.annotation.Autowired', 'org.springframework.http.HttpStatus', 'org.springframework.http.ResponseEntity', 'org.springframework.web.bind.annotation.CrossOrigin', 'org.springframework.web.bind.annotation.DeleteMapping', 'org.springframework.web.bind.annotation.GetMapping', 'org.springframework.web.bind.annotation.PathVariable', 'org.springframework.web.bind.annotation.PostMapping', 'org.springframework.web.bind.annotation.PutMapping', 'org.springframework.web.bind.annotation.RequestBody', 'org.springframework.web.bind.annotation.RequestMapping', 'org.springframework.web.bind.annotation.RestController', 'org.springframework.web.servlet.support.ServletUriComponentsBuilder'] |
| 概述说明 | 控制器管理课程资源，支持跨域，提供增删改查功能。 |

# 说明

该控制器专门负责管理课程资源，具备处理跨域请求的能力。它提供了全面的课程管理功能，包括获取课程信息、创建新课程、更新现有课程内容以及删除不再需要的课程。通过这些功能，用户可以高效地进行课程资源的操作和管理。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CourseResource | class | 该控制器处理课程资源，支持跨域请求，提供获取、创建、更新和删除课程的功能。 |



## 类 CourseResource

|      |      |
|------|------|
| 访问范围 | @CrossOrigin(origins = {"http://localhost:3000", "http://localhost:4200"});@RestController;@RequestMapping("/instructors/{username}/courses");public |
| 类型 | class |
| 名称 | CourseResource |
| 说明 | 该控制器处理课程资源，支持跨域请求，提供获取、创建、更新和删除课程的功能。 |


### UML类图

```mermaid
classDiagram
    class CourseResource {
        -CourseJpaRepository courseRepository
        +List~Course~ getAllCourses(String username)
        +Course getCourse(String username, long id)
        +ResponseEntity~Void~ deleteCourse(String username, long id)
        +ResponseEntity~Course~ updateCourse(String username, long id, Course course)
        +ResponseEntity~Void~ createCourse(String username, Course course)
    }

    class CourseJpaRepository {
        <<Interface>>
        +List~Course~ findAll()
        +Optional~Course~ findById(long id)
        +void deleteById(long id)
        +Course save(Course course)
    }

    class Course {
        -String username
        -long id
        +String getUsername()
        +void setUsername(String username)
        +long getId()
        +void setId(long id)
    }

    class ResponseEntity~T~ {
        +static ResponseEntity~Void~ noContent()
        +static ResponseEntity~T~ created(URI uri)
    }

    class ServletUriComponentsBuilder {
        +static ServletUriComponentsBuilder fromCurrentRequest()
        +URI buildAndExpand(Object... uriVariables)
    }

    CourseResource --> CourseJpaRepository : 依赖
    CourseResource --> ResponseEntity~Void~ : 依赖
    CourseResource --> ResponseEntity~Course~ : 依赖
    CourseResource --> ServletUriComponentsBuilder : 依赖
    CourseJpaRepository --> Course : 依赖
```

这段代码描述了一个Spring Boot的REST控制器`CourseResource`，用于管理课程资源。`CourseResource`依赖于`CourseJpaRepository`接口来执行数据库操作，如查找、删除、更新和创建课程。`Course`类表示课程实体，包含用户名和ID等属性。`ResponseEntity`和`ServletUriComponentsBuilder`类用于处理HTTP响应和URI构建。该控制器支持跨域请求，并提供了获取所有课程、获取单个课程、删除课程、更新课程和创建课程的功能。


### 内部方法调用关系图

```mermaid
graph TD
    A["类CourseResource"]
    B["注解: @CrossOrigin(origins = {'http://localhost:3000', 'http://localhost:4200'})"]
    C["注解: @RestController"]
    D["注解: @RequestMapping('/instructors/{username}/courses')"]
    E["属性: @Autowired CourseJpaRepository courseRepository"]
    F["方法: @GetMapping getAllCourses(@PathVariable String username)"]
    G["方法: @GetMapping('/{id}') getCourse(@PathVariable String username, @PathVariable long id)"]
    H["方法: @DeleteMapping('/{id}') deleteCourse(@PathVariable String username, @PathVariable long id)"]
    I["方法: @PutMapping('/{id}') updateCourse(@PathVariable String username, @PathVariable long id, @RequestBody Course course)"]
    J["方法: @PostMapping createCourse(@PathVariable String username, @RequestBody Course course)"]
    K["调用: courseRepository.findAll()"]
    L["调用: courseRepository.findById(id)"]
    M["调用: courseRepository.deleteById(id)"]
    N["调用: courseRepository.save(course)"]
    O["调用: ServletUriComponentsBuilder.fromCurrentRequest().path('/{id}').buildAndExpand(createdCourse.getId()).toUri()"]
    P["返回: ResponseEntity.noContent().build()"]
    Q["返回: new ResponseEntity<Course>(courseUpdated, HttpStatus.OK)"]
    R["返回: ResponseEntity.created(uri).build()"]

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
    H --> P
    I --> Q
    J --> R
```

这段代码定义了一个名为 `CourseResource` 的 REST 控制器类，用于处理与课程相关的 HTTP 请求。它包含多个方法，分别用于获取所有课程、获取特定课程、删除课程、更新课程和创建课程。每个方法都通过 `courseRepository` 与数据库进行交互，并返回相应的 HTTP 响应。代码通过注解配置了跨域请求和请求映射，确保请求能够正确路由到相应的方法。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| courseRepository | CourseJpaRepository | 自动注入课程JPA仓库实例。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| deleteCourse | ResponseEntity<Void> | 通过ID删除课程，返回无内容响应。 |
| getAllCourses | List<Course> | 获取所有课程的API接口，返回用户课程列表。 |
| updateCourse | ResponseEntity<Course> | 通过ID更新课程信息，保存并返回更新后的课程状态。 |
| getCourse | Course | 通过ID获取课程信息，若未找到则抛出异常。 |
| createCourse | ResponseEntity<Void> | 创建课程API，关联用户名并保存，返回创建资源URI。 |




