# Introduction

- the unit of modularity is the aspect

## terminology

- Aspect: a modularization of a concern that cuts across multiple classes
- Join point: in spring, join point always means a method execution
- Advice: action taken by an aspect at a particular join point
    - around, before, after
- Pointcut: a predicate that matches join points
    - for example, the execution of a method with a certain name
- Introduction: declaring additional methods or fields on behalf of a type
- Target object(*advised* object):  object being advised by one or more aspects
- *AOP proxy*

# defining Aspect

## aspect

- Aspect를 bean으로 등록하고 `@Aspect` annotation 설정
- may also contain pointcut, advice and introduction declarations
- Aspect 만으로 bean으로 등록되지 않으므로 Component annotation을 사용하던지 해야함

## pointcut

- Spring AOP는 Spring beans 에 대한 method execution join points만 지원함
    - pointcut as matching the execution of methods on Spring beans
- declaration
    - name and parameters
    - 관심있는 bean에 대해 어떤 method가 작용했는지
    - `@Pointcut` annotation
        - point cut methods must have a `void` return type
        - 
- pointcut designators
    - execution, within 등