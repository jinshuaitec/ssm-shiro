# ssm-shiro
简单的做了ssm集成shiro ,包括权限，角色的管理
1：首先创建maven 项目

2：配置pom.xml 添加框架依赖包

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.pro.shiro.cas</groupId>
  <artifactId>shiroCas</artifactId>
  <packaging>war</packaging>
  <version>0.0.1-SNAPSHOT</version>
  <name>shiroCas Maven Webapp</name>
  <url>http://maven.apache.org</url>

   <properties>
        <!-- base setting -->
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <project.build.locales>zh_CN</project.build.locales>
        <project.build.jdk>1.7</project.build.jdk>

        <!-- plugin setting -->
        <mybatis.generator.generatorConfig.xml>${basedir}/src/test/resources/generatorConfig.xml</mybatis.generator.generatorConfig.xml>
        <mybatis.generator.generatorConfig.properties>file:///${basedir}/src/test/resources/generatorConfig.properties</mybatis.generator.generatorConfig.properties>

        <!-- plugin versions -->
        <plugin.mybatis.generator>1.3.1</plugin.mybatis.generator>
        <plugin.maven-compiler>3.1</plugin.maven-compiler>
        <plugin.maven-surefire>2.18.1</plugin.maven-surefire>
        <skipTests>true</skipTests>

        <!-- lib versions -->
        <junit.version>4.11</junit.version>
        <spring.version>4.0.2.RELEASE</spring.version>
        <mybatis.version>3.2.2</mybatis.version>
        <mybatis.spring.version>1.2.2</mybatis.spring.version>
        <mysql.connector.version>5.1.30</mysql.connector.version>
        <postgresql.version>9.1-901.jdbc4</postgresql.version>
        <slf4j.version>1.6.6</slf4j.version>
        <log4j.version>1.2.12</log4j.version>
        <httpclient.version>4.1.2</httpclient.version>
        <jackson.version>1.9.13</jackson.version>
        <c3p0.version>0.9.1.2</c3p0.version>
        <druid.version>1.0.5</druid.version>
        <tomcat.jdbc.version>7.0.53</tomcat.jdbc.version>
        <jstl.version>1.2</jstl.version>
        <google.collections.version>1.0</google.collections.version>
        <cglib.version>3.1</cglib.version>
        <shiro.version>1.2.3</shiro.version>
        <commons.fileupload.version>1.3.1</commons.fileupload.version>
        <commons.codec.version>1.9</commons.codec.version>
        <commons.net.version>3.3</commons.net.version>
        <aspectj.version>1.6.12</aspectj.version>
        <netty.version>4.0.18.Final</netty.version>
        <hibernate.validator.version>5.1.1.Final</hibernate.validator.version>
    </properties>




  <dependencies>
           <!-- junit -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>${junit.version}</version>
        </dependency>

        <!-- springframe start -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-core</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-web</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-oxm</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-tx</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-aop</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context-support</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-test</artifactId>
            <version>${spring.version}</version>
        </dependency>
        <!-- springframe end -->

        <!-- mybatis start-->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
            <version>${mybatis.version}</version>
        </dependency>

        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-spring</artifactId>
            <version>${mybatis.spring.version}</version>
        </dependency>
        <!--mybatis end-->

        <!-- mysql-connector -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>${mysql.connector.version}</version>
        </dependency>

        <!-- DruidDataSource -->
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
            <version>${druid.version}</version>
        </dependency>

        <!-- jackson -->
        <dependency>
            <groupId>org.codehaus.jackson</groupId>
            <artifactId>jackson-mapper-asl</artifactId>
            <version>${jackson.version}</version>
        </dependency>

        <!-- log start -->
        <dependency>
            <groupId>log4j</groupId>
            <artifactId>log4j</artifactId>
            <version>${log4j.version}</version>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>${slf4j.version}</version>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-log4j12</artifactId>
            <version>${slf4j.version}</version>
        </dependency>
        <!-- log end -->

        <!-- servlet api -->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.0.1</version>
            <scope>provided</scope>
        </dependency>

        <!-- jstl -->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>jstl</artifactId>
            <version>${jstl.version}</version>
        </dependency>

        <!-- start apache -->
        <dependency>
            <groupId>commons-fileupload</groupId>
            <artifactId>commons-fileupload</artifactId>
            <version>${commons.fileupload.version}</version>
        </dependency>

        <dependency>
            <groupId>org.apache.httpcomponents</groupId>
            <artifactId>httpclient</artifactId>
            <version>${httpclient.version}</version>
        </dependency>

        <dependency>
            <groupId>commons-codec</groupId>
            <artifactId>commons-codec</artifactId>
            <version>${commons.codec.version}</version>
        </dependency>

        <dependency>
            <groupId>commons-net</groupId>
            <artifactId>commons-net</artifactId>
            <version>${commons.net.version}</version>
        </dependency>

        <dependency>
            <groupId>commons-logging</groupId>
            <artifactId>commons-logging</artifactId>
            <version>1.1.3</version>
        </dependency>
        <dependency>
            <groupId>commons-collections</groupId>
            <artifactId>commons-collections</artifactId>
            <version>3.2.1</version>
        </dependency>

        <!-- end apache -->

        <!-- google -->
        <dependency>
            <groupId>com.google.collections</groupId>
            <artifactId>google-collections</artifactId>
            <version>${google.collections.version}</version>
        </dependency>

        <!-- cglib -->
        <dependency>
            <groupId>cglib</groupId>
            <artifactId>cglib-nodep</artifactId>
            <version>${cglib.version}</version>
        </dependency>


        <!-- shiro -->
        <dependency>
            <groupId>org.apache.shiro</groupId>
            <artifactId>shiro-spring</artifactId>
            <version>${shiro.version}</version>
        </dependency>
        <dependency>
            <groupId>org.apache.shiro</groupId>
            <artifactId>shiro-ehcache</artifactId>
            <version>${shiro.version}</version>
        </dependency>
        <dependency>
            <groupId>org.apache.shiro</groupId>
            <artifactId>shiro-core</artifactId>
            <version>${shiro.version}</version>
        </dependency>
        <dependency>
            <groupId>org.apache.shiro</groupId>
            <artifactId>shiro-web</artifactId>
            <version>${shiro.version}</version>
        </dependency>
        <dependency>
            <groupId>org.apache.shiro</groupId>
            <artifactId>shiro-quartz</artifactId>
            <version>${shiro.version}</version>
        </dependency>

        <!-- aspectjweaver -->
        <dependency>
            <groupId>org.aspectj</groupId>
            <artifactId>aspectjweaver</artifactId>
            <version>${aspectj.version}</version>
        </dependency>
        <dependency>
            <groupId>org.aspectj</groupId>
            <artifactId>aspectjrt</artifactId>
            <version>${aspectj.version}</version>
        </dependency>

          <!-- hibernate-validator -->
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-validator</artifactId>
            <version>${hibernate.validator.version}</version>
        </dependency>

  </dependencies>
  <build>
    <finalName>springShiroCas</finalName>
  </build>
</project>
3：配置web.xml

<?xml version="1.0" encoding="utf-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/javaee"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_3_0.xsd"
         id="WebApp_ID" version="3.0">

    <!-- Spring -->
    <!-- 配置Spring配置文件路径 -->
    <context-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>
            classpath*:spring-*.xml
        </param-value>
    </context-param>
    <!-- 配置Spring上下文监听器 -->
    <listener>
        <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
    </listener>
    <!-- Spring -->

    <!-- 配置Spring字符编码过滤器 -->
    <filter>
        <filter-name>encodingFilter</filter-name>
        <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
        <init-param>
            <param-name>encoding</param-name>
            <param-value>UTF-8</param-value>
        </init-param>
        <init-param>
            <param-name>forceEncoding</param-name>
            <param-value>true</param-value>
        </init-param>
    </filter>
    <filter-mapping>
        <filter-name>encodingFilter</filter-name>
        <url-pattern>/*</url-pattern>
    </filter-mapping>

    <!-- shiro 安全过滤器 -->
    <filter>
        <filter-name>shiroFilter</filter-name>
        <filter-class>org.springframework.web.filter.DelegatingFilterProxy</filter-class>
        <async-supported>true</async-supported>
        <init-param>
            <param-name>targetFilterLifecycle</param-name>
            <param-value>true</param-value>
        </init-param>
    </filter>
    <filter-mapping>
        <filter-name>shiroFilter</filter-name>
        <url-pattern>/*</url-pattern>
    </filter-mapping>

    <!-- 配置log4j配置文件路径 -->
    <context-param>
        <param-name>log4jConfigLocation</param-name>
        <param-value>classpath:log4j.properties</param-value>
    </context-param>
    <!-- 60s 检测日志配置 文件变化 -->
    <context-param>
        <param-name>log4jRefreshInterval</param-name>
        <param-value>60000</param-value>
    </context-param>

    <!-- 配置Log4j监听器 -->
    <listener>
        <listener-class>org.springframework.web.util.Log4jConfigListener</listener-class>
    </listener>

    <!-- Spring MVC 核心控制器 DispatcherServlet 配置 -->
    <servlet>
        <servlet-name>dispatcher</servlet-name>
        <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
        <init-param>
            <param-name>contextConfigLocation</param-name>
            <param-value>classpath*:spring-mvc.xml</param-value>
        </init-param>
        <load-on-startup>1</load-on-startup>
    </servlet>
    <servlet-mapping>
        <servlet-name>dispatcher</servlet-name>
        <!-- 拦截所有/rest/* 的请求,交给DispatcherServlet处理,性能最好 -->
        <url-pattern>/rest/*</url-pattern>
    </servlet-mapping>

    <!-- 首页 -->
    <welcome-file-list>
        <welcome-file>rest/index</welcome-file>
    </welcome-file-list>

    <!-- 错误页 -->
    <error-page>
        <error-code>404</error-code>
        <location>/rest/page/404</location>
    </error-page>
    <error-page>
        <error-code>500</error-code>
        <location>/rest/page/500</location>
    </error-page>
    <error-page>
        <exception-type>org.apache.shiro.authz.AuthorizationException</exception-type>
        <location>/rest/page/401</location>
    </error-page>

</web-app>
4、spring配置 spring-mybatis.xml：

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:context="http://www.springframework.org/schema/context"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:tx="http://www.springframework.org/schema/tx" xmlns:p="http://www.springframework.org/schema/p"
       xmlns:util="http://www.springframework.org/schema/util" xmlns:jdbc="http://www.springframework.org/schema/jdbc"
       xmlns:cache="http://www.springframework.org/schema/cache"
       xsi:schemaLocation="
    http://www.springframework.org/schema/context
    http://www.springframework.org/schema/context/spring-context.xsd
    http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans.xsd
    http://www.springframework.org/schema/tx
    http://www.springframework.org/schema/tx/spring-tx.xsd
    http://www.springframework.org/schema/jdbc
    http://www.springframework.org/schema/jdbc/spring-jdbc.xsd
    http://www.springframework.org/schema/cache
    http://www.springframework.org/schema/cache/spring-cache.xsd
    http://www.springframework.org/schema/aop
    http://www.springframework.org/schema/aop/spring-aop.xsd
    http://www.springframework.org/schema/util
    http://www.springframework.org/schema/util/spring-util.xsd">

    <!-- 自动扫描quick4j包 ,将带有注解的类 纳入spring容器管理 -->
    <context:component-scan base-package="com.shiro"></context:component-scan>

    <!-- 引入配置文件 -->
    <bean id="propertyConfigurer" class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
        <property name="locations">
            <list>
                <value>classpath*:jdbc.properties</value>
            </list>
        </property>
    </bean>

    <!-- dataSource 配置 -->
    <bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource" init-method="init" destroy-method="close">
        <!-- 基本属性 url、user、password -->
        <property name="url" value="${jdbc.url}"/>
        <property name="username" value="${jdbc.username}"/>
        <property name="password" value="${jdbc.password}"/>

        <!-- 配置初始化大小、最小、最大 -->
        <property name="initialSize" value="${ds.initialSize}"/>
        <property name="minIdle" value="${ds.minIdle}"/>
        <property name="maxActive" value="${ds.maxActive}"/>

        <!-- 配置获取连接等待超时的时间 -->
        <property name="maxWait" value="${ds.maxWait}"/>

        <!-- 配置间隔多久才进行一次检测，检测需要关闭的空闲连接，单位是毫秒 -->
        <property name="timeBetweenEvictionRunsMillis" value="${ds.timeBetweenEvictionRunsMillis}"/>

        <!-- 配置一个连接在池中最小生存的时间，单位是毫秒 -->
        <property name="minEvictableIdleTimeMillis" value="${ds.minEvictableIdleTimeMillis}"/>

        <property name="validationQuery" value="SELECT 'x'"/>
        <property name="testWhileIdle" value="true"/>
        <property name="testOnBorrow" value="false"/>
        <property name="testOnReturn" value="false"/>

        <!-- 打开PSCache，并且指定每个连接上PSCache的大小 -->
        <property name="poolPreparedStatements" value="false"/>
        <property name="maxPoolPreparedStatementPerConnectionSize" value="20"/>

        <!-- 配置监控统计拦截的filters -->
        <property name="filters" value="stat"/>
    </bean>

 <!-- spring和MyBatis完美整合，不需要mybatis的配置映射文件 -->
    <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <!-- 自动扫描mapping.xml 文件 -->
        <property name="mapperLocations" value="classpath:com/shiro/dao/*.xml" />
         <!-- 开启缓存支持 -->
         <property name="configurationProperties">
            <props>
                <prop key="cacheEnabled">true</prop>
                <!-- 查询时，关闭关联对象即时加载以提高性能 -->
                <prop key="lazyLoadingEnabled">false</prop>
                <!-- 设置关联对象加载的形态，此处为按需加载字段(加载字段由SQL指定)，不会加载关联表的所有字段，以提高性能 -->
                <prop key="aggressiveLazyLoading">true</prop>
                <!-- 对于未知的SQL查询，允许返回不同的结果集以达到通用的效果 -->
                <prop key="multipleResultSetsEnabled">true</prop>
                <!-- 允许使用列标签代替列名 -->
                <prop key="useColumnLabel">true</prop>
                <!-- 允许使用自定义的主键值(比如由程序生成的UUID 32位编码作为键值)，数据表的PK生成策略将被覆盖 -->
                <prop key="useGeneratedKeys">true</prop>
                <!-- 给予被嵌套的resultMap以字段-属性的映射支持 -->
                <prop key="autoMappingBehavior">FULL</prop>
                <!-- 对于批量更新操作缓存SQL以提高性能 -->
                <prop key="defaultExecutorType">BATCH</prop>
                <!-- 数据库超过25000秒仍未响应则超时 -->
                <prop key="defaultStatementTimeout">25000</prop>
            </props>
        </property>        
    </bean>

    <!-- spring与mybatis整合配置，扫描所有dao -->
    <bean class="org.mybatis.spring.mapper.MapperScannerConfigurer" p:basePackage="com.shiro.dao"
          p:sqlSessionFactoryBeanName="sqlSessionFactory"/>

    <!-- 对dataSource 数据源进行事务管理 -->
    <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager"
          p:dataSource-ref="dataSource"/>

    <!-- 事务管理 通知 -->
    <tx:advice id="txAdvice" transaction-manager="transactionManager">
        <tx:attributes>
            <!-- 对insert,update,delete 开头的方法进行事务管理,只要有异常就回滚 -->
            <tx:method name="insert*" propagation="REQUIRED" rollback-for="java.lang.Throwable"/>
            <tx:method name="update*" propagation="REQUIRED" rollback-for="java.lang.Throwable"/>
            <tx:method name="delete*" propagation="REQUIRED" rollback-for="java.lang.Throwable"/>
            <!-- select,count开头的方法,开启只读,提高数据库访问性能 -->
            <tx:method name="select*" read-only="true"/>
            <tx:method name="count*" read-only="true"/>
            <!-- 对其他方法 使用默认的事务管理 -->
            <tx:method name="*"/>
        </tx:attributes>
    </tx:advice>

    <!-- 事务 aop 配置 -->
    <aop:config>
        <aop:pointcut id="serviceMethods" expression="execution(* com.shiro.service..*(..))"/>
        <aop:advisor advice-ref="txAdvice" pointcut-ref="serviceMethods"/>
    </aop:config>

    <!-- 配置使Spring采用CGLIB代理 -->
    <aop:aspectj-autoproxy proxy-target-class="true"/>

    <!-- 启用对事务注解的支持 -->
    <tx:annotation-driven transaction-manager="transactionManager"/>

    <!-- Cache配置 -->
    <cache:annotation-driven cache-manager="cacheManager"/>
    <bean id="ehCacheManagerFactory" class="org.springframework.cache.ehcache.EhCacheManagerFactoryBean"
          p:configLocation="classpath:ehcache.xml"/>
    <bean id="cacheManager" class="org.springframework.cache.ehcache.EhCacheCacheManager"
          p:cacheManager-ref="ehCacheManagerFactory"/>
</beans>
5： 数据库配置文件 jdbc.properties

##JDBC Global Setting  
jdbc.driver=com.mysql.jdbc.Driver  
jdbc.url=jdbc:mysql://localhost:3306/quick4j?useUnicode=true&characterEncoding=utf-8  
jdbc.username=root  
jdbc.password=admin123  

##DataSource Global Setting  

#配置初始化大小、最小、最大  
ds.initialSize=1  
ds.minIdle=1  
ds.maxActive=20  

#配置获取连接等待超时的时间   
ds.maxWait=60000  

#配置间隔多久才进行一次检测，检测需要关闭的空闲连接，单位是毫秒  
ds.timeBetweenEvictionRunsMillis=60000  

#配置一个连接在池中最小生存的时间，单位是毫秒  
ds.minEvictableIdleTimeMillis=300000
6：缓存配置文件 ehcache.xml

<?xml version="1.0" encoding="UTF-8"?>  
<ehcache updateCheck="false" name="txswx-ehcache">  
    <diskStore path="java.io.tmpdir"/>  
    <!-- DefaultCache setting. -->  
    <defaultCache maxEntriesLocalHeap="10000" eternal="true" timeToIdleSeconds="300" timeToLiveSeconds="600"  
                  overflowToDisk="true" maxEntriesLocalDisk="100000"/>  
</ehcache>
7： ehcache-shiro.xml

 <ehcache updateCheck="false" name="shiroCache">

    <defaultCache
            maxElementsInMemory="10000"
            eternal="false"
            timeToIdleSeconds="120"
            timeToLiveSeconds="120"
            overflowToDisk="false"
            diskPersistent="false"
            diskExpiryThreadIntervalSeconds="120"
            />
</ehcache>
8： Shiro 配置 ： spring-shiro.xml要配置realms bean

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:util="http://www.springframework.org/schema/util"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="
       http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/util http://www.springframework.org/schema/util/spring-util.xsd">

    <description>apache shiro配置</description>

    <bean id="shiroFilter" class="org.apache.shiro.spring.web.ShiroFilterFactoryBean">
        <property name="securityManager" ref="securityManager"/>
        <property name="loginUrl" value="/rest/page/login"/>
        <property name="successUrl" value="/rest/index"/>
        <property name="unauthorizedUrl" value="/rest/page/401"/>
        <property name="filterChainDefinitions">
            <value>
                <!-- 静态资源允许访问 -->
                /app/** = anon
                /assets/** = anon
                <!-- 登录页允许访问 -->
                /rest/user/login = anon
                <!-- 如果某个资源允许访问， 直接匹配成anon 即可 -->
                 <!--  /rest/user/* = anon  -->  
                 <!-- 如果某个资源需要认证，且要有相应的角色，可以直接如下设置，可以设置多个角色用逗号隔开,  有可以设置权限控制 -->   
                 <!--  也是使用注解来实现， 具体见 UserController 类 -->     
                /rest/user/admin = authc ,roles[admin]  ,perms[user:create]         
               <!--  /rest/user/admin = authc ,perms[user:create] -->
                 <!-- 其他资源需要认证  ，需要认证的资源 匹配成 authc-->                    
              <!--    /** = authc -->
            </value>
        </property>
    </bean>

    <!-- 缓存管理器 使用Ehcache实现 -->
    <bean id="shiroEhcacheManager" class="org.apache.shiro.cache.ehcache.EhCacheManager">
        <property name="cacheManagerConfigFile" value="classpath:ehcache-shiro.xml"/>
    </bean>

    <!-- 会话DAO -->
    <bean id="sessionDAO" class="org.apache.shiro.session.mgt.eis.MemorySessionDAO"/>

    <!-- 会话管理器 -->
    <bean id="sessionManager" class="org.apache.shiro.web.session.mgt.DefaultWebSessionManager">
        <property name="sessionDAO" ref="sessionDAO"/>
    </bean>

    <!-- 安全管理器 -->
    <bean id="securityManager" class="org.apache.shiro.web.mgt.DefaultWebSecurityManager">
        <property name="realms">
            <list>
            <!-- 这里引用的是 com.shiro.security.SecurityRealm.java 类 -->
                <ref bean="securityRealm"/>
            </list>
        </property>
        <!-- cacheManager,集合spring缓存工厂 -->
        <!-- <property name="cacheManager" ref="shiroEhcacheManager" /> -->
        <!-- <property name="sessionManager" ref="sessionManager" /> -->
    </bean>

    <!-- Shiro生命周期处理器 -->
    <bean id="lifecycleBeanPostProcessor" class="org.apache.shiro.spring.LifecycleBeanPostProcessor"/>

</beans>
9：Spring MVC 配置

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:p="http://www.springframework.org/schema/p"
       xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop.xsd
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd 
        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd 
        http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc.xsd 
        http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx.xsd">

    <!-- 扫描controller（controller层注入） -->
    <context:component-scan base-package="com.shiro.controller"/>

    <!-- 会自动注册DefaultAnnotationHandlerMapping与AnnotationMethodHandlerAdapter 两个bean,是spring MVC为@Controllers分发请求所必须的 -->
    <!-- 指定自己定义的validator -->
    <mvc:annotation-driven validator="validator"/>

    <!-- 以下 validator ConversionService 在使用 mvc:annotation-driven 会 自动注册 -->
    <bean id="validator" class="org.springframework.validation.beanvalidation.LocalValidatorFactoryBean">
        <property name="providerClass" value="org.hibernate.validator.HibernateValidator"/>
        <!-- 如果不加默认到 使用classpath下的 ValidationMessages.properties -->
        <property name="validationMessageSource" ref="messageSource"/>
    </bean>

    <!-- 国际化的消息资源文件（本系统中主要用于显示/错误消息定制） -->
    <bean id="messageSource" class="org.springframework.context.support.ReloadableResourceBundleMessageSource">
        <property name="basenames">
            <list>
                <!-- 在web环境中一定要定位到classpath 否则默认到当前web应用下找 -->
                <value>classpath:messages</value>
                <value>classpath:org/hibernate/validator/ValidationMessages</value>
            </list>
        </property>
        <property name="useCodeAsDefaultMessage" value="false"/>
        <property name="defaultEncoding" value="UTF-8"/>
        <property name="cacheSeconds" value="60"/>
    </bean>

    <mvc:interceptors>
        <bean class="org.springframework.web.servlet.i18n.LocaleChangeInterceptor"/>
    </mvc:interceptors>

    <bean id="localeResolver" class="org.springframework.web.servlet.i18n.CookieLocaleResolver">
        <property name="defaultLocale" value="zh_CN"/>
    </bean>

    <!-- 支持返回json(避免IE在ajax请求时，返回json出现下载 ) -->
    <bean class="org.springframework.web.servlet.mvc.annotation.AnnotationMethodHandlerAdapter">
        <property name="messageConverters">
            <list>
                <ref bean="mappingJacksonHttpMessageConverter"/>
            </list>
        </property>
    </bean>
    <bean id="mappingJacksonHttpMessageConverter"
          class="org.springframework.http.converter.json.MappingJacksonHttpMessageConverter">
        <property name="supportedMediaTypes">
            <list>
                <value>text/plain;charset=UTF-8</value>
                <value>application/json;charset=UTF-8</value>
            </list>
        </property>
    </bean>
    <!-- 支持返回json -->

    <!-- 对模型视图添加前后缀 -->
    <bean id="viewResolver" class="org.springframework.web.servlet.view.InternalResourceViewResolver"
          p:prefix="/WEB-INF/views/" p:suffix=".jsp"/>

    <!-- 配置springMVC处理上传文件的信息 -->
    <bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
        <property name="defaultEncoding" value="utf-8"/>
        <property name="maxUploadSize" value="10485760000"/>
        <property name="maxInMemorySize" value="40960"/>
    </bean>

    <!-- 启用shrio授权注解拦截方式 -->
    <aop:config proxy-target-class="true"></aop:config>
    <bean class="org.apache.shiro.spring.security.interceptor.AuthorizationAttributeSourceAdvisor">
        <property name="securityManager" ref="securityManager"/>
    </bean>

</beans>
10：log4j.properties

# DEBUG,INFO,WARN,ERROR,FATAL  
LOG_LEVEL=INFO  

log4j.rootLogger=${LOG_LEVEL},CONSOLE,FILE  

log4j.appender.CONSOLE=org.apache.log4j.ConsoleAppender  
log4j.appender.CONSOLE.Encoding=utf-8  
log4j.appender.CONSOLE.layout=org.apache.log4j.PatternLayout  
#log4j.appender.CONSOLE.layout.ConversionPattern=[%-5p] %d{yyyy-MM-dd HH:mm:ss} %C{8}@(%F:%L):%m%n   
log4j.appender.CONSOLE.layout.ConversionPattern=[%-5p] %d{yyyy-MM-dd HH:mm:ss} %C{1}@(%F:%L):%m%n  

log4j.appender.FILE=org.apache.log4j.DailyRollingFileAppender  
log4j.appender.FILE.File=${catalina.base}/logs/quick4j.log  
log4j.appender.FILE.Encoding=utf-8  
log4j.appender.FILE.DatePattern='.'yyyy-MM-dd  
log4j.appender.FILE.layout=org.apache.log4j.PatternLayout  
#log4j.appender.FILE.layout=org.apache.log4j.HTMLLayout  
log4j.appender.FILE.layout.ConversionPattern=[%-5p] %d{yyyy-MM-dd HH\:mm\:ss} %C{8}@(%F\:%L)\:%m%n
11： sql 文件在项目中

12：shiro 理解

 1： 使用shiro 在访问资源的时候， 首先会通过shiro 进行过滤，具体过滤条件

 <bean id="shiroFilter" class="org.apache.shiro.spring.web.ShiroFilterFactoryBean">
        <property name="securityManager" ref="securityManager"/>
        <!-- 如果需要权限， 然而没有登录的话，会跳转到 登录界面url /rest/page/login -->
        <property name="loginUrl" value="/rest/page/login"/>
         <!-- 登录成功后会跳转到  /rest/index-->
        <property name="successUrl" value="/rest/index"/>
        <!-- 如果没有权限的话，会跳转到 /rest/page/401 -->
        <property name="unauthorizedUrl" value="/rest/page/401"/>
        <property name="filterChainDefinitions">
            <value>
                <!-- 静态资源允许访问 -->
                /app/** = anon
                /assets/** = anon
                <!-- 登录页允许访问 -->
                /rest/user/login = anon
                <!-- 如果某个资源允许访问， 直接匹配成anon 即可 -->
                 <!--  /rest/user/* = anon  -->  
                 <!-- 如果某个资源需要认证，且要有相应的角色，可以直接如下设置，可以设置多个角色用逗号隔开,  有可以设置权限控制 -->   
                 <!--  也是使用注解来实现， 具体见 UserController 类 -->     
                /rest/user/admin = authc ,roles[admin]  ,perms[user:create]         
               <!--  /rest/user/admin = authc ,perms[user:create] -->
                 <!-- 其他资源需要认证  ，需要认证的资源 匹配成 authc-->                    
              <!--    /** = authc -->
            </value>
        </property>
    </bean>

 2：用户在进行登录的时候会进行身份的验证， 具体见UserController.java
转载来自链接：http://www.jianshu.com/p/023ca8206067
