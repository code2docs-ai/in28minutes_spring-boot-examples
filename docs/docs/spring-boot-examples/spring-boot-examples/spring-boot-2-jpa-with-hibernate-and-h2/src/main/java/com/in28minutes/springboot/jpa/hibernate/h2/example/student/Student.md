# 基础信息

|      |      |
|------|------|
| 名称 | Student |
| 编码语言 | .java |
| 代码路径 | spring-boot-examples/spring-boot-2-jpa-with-hibernate-and-h2/src/main/java/com/in28minutes/springboot/jpa/hibernate/h2/example/student/Student.java |
| 包名 | com.in28minutes.springboot.jpa.hibernate.h2.example.student |
| 依赖项 | ['jakarta.persistence.Entity', 'jakarta.persistence.GeneratedValue', 'jakarta.persistence.Id'] |
| 概述说明 | Java类Student包含id、name和passportNumber属性，提供构造方法和getter/setter。 |

# 说明

Java类Student定义了三个属性：id、name和passportNumber。该类提供了构造方法用于初始化这些属性，并包含对应的getter和setter方法，以便访问和修改这些属性的值。这个类设计用于存储和管理学生的基本信息。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| Student | class | Java类Student包含id、name和passportNumber属性，提供构造方法和getter/setter。 |



## 类 Student

|      |      |
|------|------|
| 访问范围 | @Entity;public |
| 类型 | class |
| 名称 | Student |
| 说明 | Java类Student包含id、name和passportNumber属性，提供构造方法和getter/setter。 |


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

**描述：**  
`Student` 类是一个实体类，用于表示学生信息。它包含三个私有属性：`id`、`name` 和 `passportNumber`，分别表示学生的唯一标识、姓名和护照号码。类中提供了三个构造函数，用于不同场景下的对象初始化。此外，类中还提供了获取和设置这些属性的方法，以及重写了 `toString` 方法，用于返回学生对象的字符串表示形式。这个类可以用于数据库操作或其他需要管理学生信息的场景。


### 内部方法调用关系图

```mermaid
graph TD
    A["类Student"]
    B["属性: Long id"]
    C["属性: String name"]
    D["属性: String passportNumber"]
    E["默认构造方法: Student()"]
    F["带参构造方法: Student(Long id, String name, String passportNumber)"]
    G["带参构造方法: Student(String name, String passportNumber)"]
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

这段代码定义了一个名为`Student`的实体类，包含三个属性：`id`、`name`和`passportNumber`。类提供了三个构造方法，分别用于创建空对象、带所有参数的完整对象以及不带`id`的部分对象。此外，类还提供了各个属性的`getter`和`setter`方法，并重写了`toString`方法以便返回对象的字符串表示。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| name | String | 定义了一个私有字符串类型的变量name。 |
| passportNumber | String | 定义私有字符串变量护照号码。 |
| id | Long | 实体类中定义了一个自动生成的长整型ID字段。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| setId | void | 设置对象ID的方法。 |
| getPassportNumber | String | 获取护照号码的方法。 |
| getName | String | 获取并返回名称属性的字符串值。 |
| setName | void | 定义方法`setName`，用于设置对象的`name`属性。 |
| getId | Long | 该方法返回长整型变量id的值。 |
| setPassportNumber | void | 设置护照号码的方法。 |
| toString | String | 重写toString方法，返回学生ID、姓名和护照号。 |




