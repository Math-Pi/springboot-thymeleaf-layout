# SpringBoot-Thymeleaf-layout

## 1.pom.xml引入依赖

```xml
<dependency>
     <groupId>nz.net.ultraq.thymeleaf</groupId>
     <artifactId>thymeleaf-layout-dialect</artifactId>
     <version>2.0.2</version>
</dependency>12345
```

## 2.创建模板页面(layout.html)
使用**layout:fragment=”“**表示

```html
<div th:replace="layout/header :: header"></div>
<div th:replace="layout/left :: left"></div>
<div layout:fragment="content" > content</div>
<div th:replace="layout/footer :: footer"></div>
```

## 3.使用该模板

使用**layout:decorator=”“**指定要使用的模版

```html
<html xmlns:th="http://www.thymeleaf.org"  
      xmlns:layout="http://www.ultraq.net.nz/web/thymeleaf/layout" 
      layout:decorate="layout">
```

在内容部分，同样使用**layout:fragment=”“**来指定要将片段输出在模版的位置

```html
<div layout:fragment="content" >
    <h2>模板内容</h2>
</div>
```

- 使用这种方式，可以直接继承模版的js以及css样式

