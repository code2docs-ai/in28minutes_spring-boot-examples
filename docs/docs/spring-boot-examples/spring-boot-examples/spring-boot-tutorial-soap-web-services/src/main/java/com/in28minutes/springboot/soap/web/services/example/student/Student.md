# 基础信息

|      |      |
|------|------|
| 名称 | Student |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-tutorial-soap-web-services/src/main/java/com/in28minutes/springboot/soap/web/services/example/student/Student.java |
| 包名 | com.in28minutes.springboot.soap.web.services.example.student |
| 依赖项 | [] |
| 概述说明 | Java类Student包含id、name、passportNumber属性及其构造方法和getter/setter。 |

# 说明

Java类Student定义了三个属性：id、name和passportNumber。该类提供了构造方法用于初始化这些属性，并包含相应的getter和setter方法，用于访问和修改这些属性的值。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| Student | class | Java类Student包含id、name、passportNumber属性及构造方法和getter/setter。 |



## 类 Student

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | Student |
| 说明 | Java类Student包含id、name、passportNumber属性及构造方法和getter/setter。 |


### UML类图

```mermaid
classDiagram
    class Student {
        -Long id
        -String name
        -String passportNumber
        +Student()
        +Student(Long id, String name, String passportNumber)
        +Student(String name, String passportNumber)
        +Long getId()
        +void setId(Long id)
        +String getName()
        +void setName(String name)
        +String getPassportNumber()
        +void setPassportNumber(String passportNumber)
        +String toString()
    }
```

这段代码定义了一个`Student`类，包含三个私有属性：`id`、`name`和`passportNumber`。类中提供了三个构造函数，分别用于无参初始化、全参初始化和部分参数初始化。此外，类中还提供了属性的getter和setter方法，以及一个重写的`toString`方法，用于格式化输出学生信息。该类主要用于表示学生的基本信息，并提供了对这些信息的访问和修改功能。


### 内部方法调用关系图

```mermaid
graph TD
    A["类Student"]
    B["属性: Long id"]
    C["属性: String name"]
    D["属性: String passportNumber"]
    E["构造方法: Student()"]
    F["构造方法: Student(Long id, String name, String passportNumber)"]
    G["构造方法: Student(String name, String passportNumber)"]
    H["方法: Long getId()"]
    I["方法: void setId(Long id)"]
    J["方法: String getName()"]
    K["方法: void setName(String name)"]
    L["方法: String getPassportNumber()"]
    M["方法: void setPassportNumber(String passportNumber)"]
    N["重写方法: String toString()"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    A --> I
    A --> J
    A --> K
    A --> L
    A --> M
    A --> N
```

这段代码定义了一个名为`Student`的类，包含三个属性：`id`、`name`和`passportNumber`。类中提供了三个构造方法，分别用于无参初始化、全参数初始化和部分参数初始化。此外，类中还提供了属性的getter和setter方法，以及重写的`toString`方法，用于格式化输出对象信息。流程图清晰地展示了类的结构及其内部方法之间的关系。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| name | String | 声明一个私有字符串类型的变量name。 |
| id | Long | 定义了一个长整型的私有变量id。 |
| passportNumber | String | 护照号码为私有字符串类型。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getPassportNumber | String | 获取护照号码的方法。 |
| getName | String | 该方法返回名为`name`的字符串变量值。 |
| setPassportNumber | void | 设置护照号码的方法。 |
| setName | void | 该方法用于设置对象的名称属性。 |
| getId | Long | 该方法返回一个长整型ID值。 |
| setId | void | 该方法用于设置对象的ID属性。 |
| toString | String | 重写toString方法，返回学生ID、姓名和护照号。 |




