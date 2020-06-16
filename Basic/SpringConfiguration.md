### XML configuration file
- Khi bắt đầu thì spring dùng xml để config project và spring bean.
- Khai báo bean trong trong application context xml. 
<bean name="studentRepository" class="com.repository.studentRepositoryImpl"/>
- Inject bean using setter
<bean name="studentService" class="com.service.studentServiceImpl">
    <property name="studentRepository" ref="studentRepository"></property>
</bean>
- Inject bean using contructor
<bean name="studentService" class="com.service.studentServiceImpl">
    <constructor-arg name="studentRepository" ref="studentRepository"></constructor-arg>
</bean>
- Inject bean using autowire (by constructor, byType, byName)
<bean name="studentService" class="com.service.studentServiceImpl" autowire="default"/>
+ byContructor: call contructor with parameter.
+ byType: call default contructor with no parameter for create bean. Identify bean base on class.
+ byName: call default contructor with no parameter for create bean. Identify base on name.

### Annotation-base configuration
    Java giới thiệu annotation từ java 5 -> spring 2.5 đưa anotation vào để cho phép lập trình viên có 1 lựa chọn khác để thiết lập cấu hình.
- Sử dụng để khai báo, inject các bean trong spring thay vì dùng xml.
- Anotation injection được thực hiện trước XML injection. -> Khai báo trùng thì anotation injection sẽ bị override.
- Anotation không được chạy mặc định mà cần phải khai báo trong spring. Xử dụng XML configuration files.
- Annotation-config vs component-scan
    + Annotation-config: là các tag cho phép chúng ta gọi các annotation đã khai báo cho những bean trong application context. VD: @required, @Autowired, @PostConstruct, @Predestroy, @Resource
    + Annotation-scan: tương tự như annotation config tuy nhiên còn cho phép scan package để tìm và đăng ký bean trong application context. VD: @Component, @Repository, @Controller, @Service, @RestController, @ControllerAdvice, @Configuration


### Java-based configuration: Từ spring 4.1 thì spring cho phép 1 loại cấu hình nữa là java based
