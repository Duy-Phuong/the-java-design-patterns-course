# Spring Security Zero to Master along with JWT,OAUTH2

[https://freetutsdownload.net/spring-security-zero-to-master-along-with-jwtoauth2-free-download/](https://freetutsdownload.net/spring-security-zero-to-master-along-with-jwtoauth2-free-download/)

pass: *****freetutsdownload.net*****

11h

<aside>
💡 Include jwt

</aside>

 courses

[How To Implement JWT Authentication In Spring Boot Project? | Making Java Easy To Learn](https://javatechonline.com/how-to-implement-jwt-authentication-in-spring-boot-project/?fbclid=IwAR3J4UOIlYeGl4ns-s8-oj2puoyFS1vMAR-9wx4YCnjmwGSyxhZ9DF12zto)

[How To Implement OAuth In Spring Boot Project? | Making Java Easy To Learn](https://javatechonline.com/how-to-implement-oauth-in-spring-boot-project/?fbclid=IwAR20OByY906pBXFvXJJNaPqqAdQPGR75unXrpdtUW1f8wRGwtoLSQf5x3ec)

# Getting Started

## Course Introduction

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%201.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%202.png)

## Course content(git + pdf)

**1.  To save your time from taking notes, I am attaching the content in a PDF format that we will discuss in this entire course for your reference. You can always use this as a quick refresher in future even after completing the course. So just sit back and enjoy the learning of Spring Security, OAUTH2, JWT etc**

[https://github.com/eazybytes/spring-security](https://github.com/eazybytes/spring-security)

⇒ forked

[Spring+Security+Zero+to+Master+along+with+JWT,OAUTH2.pdf](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/SpringSecurityZerotoMasteralongwithJWTOAUTH2.pdf)

[Spring+Security+Zero+to+Master+along+with+JWT,OAUTH2.pdf](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/SpringSecurityZerotoMasteralongwithJWTOAUTH2%201.pdf)

**2. Udemy asks a review very early in the course and at multiple intervals. If you feel you are not ready to leave a review, please feel free to skip it. Once you make some progress in the course, you can leave your review based on your feedback. So please be patient for the first 3-4 sections and I am sure you will love it.**

**3. We will also build a sample bank application called 'EazyBank' focusing spring security by using Angular in the UI and SpringBoot, REST services, JPA in the backend. The code of this application will be shared as we complete the milestones by attaching in the individual sections.**

**Thanks Much and Keep Learning !!**

## What is Security & Why it is important

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%203.png)

## Creating a simple Spring security project

select dependency

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%204.png)

import existing maven project

Create controller

[https://github.com/eazybytes/spring-security/blob/main/section1/springsecuritybasic/src/main/java/com/eazybytes/controller/WelcomeController.java](https://github.com/eazybytes/spring-security/blob/main/section1/springsecuritybasic/src/main/java/com/eazybytes/controller/WelcomeController.java)

```java
package com.eazybytes.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class WelcomeController {

	@GetMapping("/welcome")
	public String sayWelcome() {
		return "Welcome from Spring Application with Security";
	}
	
}
```

Run as Java application

add spring security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%205.png)

explore and copy pom.xml

```java
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.3.3.RELEASE</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.eazybytes</groupId>
	<artifactId>springsecuritybasic</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>springsecuritybasic</name>
	<description>Demo project for Spring Boot</description>

	<properties>
		<java.version>1.8</java.version>
	</properties>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-security</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
			<exclusions>
				<exclusion>
					<groupId>org.junit.vintage</groupId>
					<artifactId>junit-vintage-engine</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework.security</groupId>
			<artifactId>spring-security-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%206.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%207.png)

username is `user` and pass is generated pass

You can configure

```java
spring.security.user.name = eazybytes
spring.security.user.password = 12345
```

## Understanding on how multiple requests work with out credentials

Chỉ hỏi pass 1 lần

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%208.png)

 call again without auth

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%209.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2010.png)

## Spring Security Internal flow and Architecture

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2011.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2012.png)

## Summary of the Section

**In this section, we discussed about the below topics on a high level.**

> Agenda of this courseWhat is security and why it is important for any web applicationCreating a simple spring boot project with security enabled inside itTesting the simple application that we created using browser and postman by using default and configured credentialsUnderstanding on how multiple requests will get processed even with out credentials once the user is authenticated.Internal architecture of Spring Security. Don't worry if you have not understand this. We will discuss in detail about each component involved in the coming sections :)
> 

**The project source code that we developed and discussed is attached to this lecture and can be downloaded for your reference.**

<aside>
💡 Trong folder có source

</aside>

# Changing the default security configurations

## Understanding about UI part of the project

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2013.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2014.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2015.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2016.png)

no auth in this page

## Creating backend services needed for the application

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2017.png)

[https://github.com/eazybytes/spring-security/tree/main/section2/springsecsection2/src/main/java/com/eazybytes/controller](https://github.com/eazybytes/spring-security/tree/main/section2/springsecsection2/src/main/java/com/eazybytes/controller)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2018.png)

## Testing the backend services with default configurations

no auth ⇒ 401

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2019.png)

## Checking the default configuration inside the spring security library

From form, backend, request

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2020.png)

[https://github.com/eazybytes/spring-security/blob/main/section2/springsecsection2/src/main/java/com/eazybytes/config/ProjectSecurityConfig.java](https://github.com/eazybytes/spring-security/blob/main/section2/springsecsection2/src/main/java/com/eazybytes/config/ProjectSecurityConfig.java)

```java
package com.eazybytes.config;

import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;

@Configuration
public class ProjectSecurityConfig extends WebSecurityConfigurerAdapter {

	/**
	 * /myAccount - Secured /myBalance - Secured /myLoans - Secured /myCards -
	 * Secured /notices - Not Secured /contact - Not Secured
	 */
	@Override
	protected void configure(HttpSecurity http) throws Exception {

		/**
		 * Default configurations which will secure all the requests
		 */

		/*
		 * http .authorizeRequests() .anyRequest().authenticated() .and()
		 * .formLogin().and() .httpBasic();
		 */

		/**
		 * Custom configurations as per our requirement
		 */

		/*
		 * http .authorizeRequests() .antMatchers("/myAccount").authenticated()
		 * .antMatchers("/myBalance").authenticated()
		 * .antMatchers("/myLoans").authenticated()
		 * .antMatchers("/myCards").authenticated() .antMatchers("/notices").permitAll()
		 * .antMatchers("/contact").permitAll() .and() .formLogin().and() .httpBasic();
		 */

		/**
		 * Configuration to deny all the requests
		 */

		/*
		 * http .authorizeRequests() .anyRequest().denyAll() .and() .formLogin().and()
		 * .httpBasic();
		 */

		/**
		 * Configuration to permit all the requests
		 */

		http .authorizeRequests() .anyRequest().permitAll().and() .formLogin().and()
		 .httpBasic();
		

	}

}
```

add componentScan

```java
package com.eazybytes.springsecsection2;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.ComponentScans;

@SpringBootApplication
@ComponentScans({ @ComponentScan("com.eazybytes.controller"), @ComponentScan("com.eazybytes.config") })
public class Springsecsection2Application {

	public static void main(String[] args) {
		SpringApplication.run(Springsecsection2Application.class, args);
	}

}
```

## Modifying the code as per our custom requirements

uncomment

```java
/*
		 * http .authorizeRequests() .antMatchers("/myAccount").authenticated()
		 * .antMatchers("/myBalance").authenticated()
		 * .antMatchers("/myLoans").authenticated()
		 * .antMatchers("/myCards").authenticated() .antMatchers("/notices").permitAll()
		 * .antMatchers("/contact").permitAll() .and() .formLogin().and() .httpBasic();
		 */
```

## Denying all the requests

```java
/**
		 * Configuration to deny all the requests
		 */

		/*
		 * http .authorizeRequests() .anyRequest().denyAll() .and() .formLogin().and()
		 * .httpBasic();
		 */
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2021.png)

## Permit all the requests

```java
http .authorizeRequests() .anyRequest().permitAll().and() .formLogin().and()
		 .httpBasic();
```

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2022.png)

# Defining & Managing Users

## Configuring users using inMemoryAuthentication

[https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/config/ProjectSecurityConfig.java](https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/config/ProjectSecurityConfig.java)

```java
package com.eazybytes.config;

import javax.sql.DataSource;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
import org.springframework.security.core.userdetails.UserDetailsService;
import org.springframework.security.crypto.password.NoOpPasswordEncoder;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.security.provisioning.JdbcUserDetailsManager;

@Configuration
public class ProjectSecurityConfig extends WebSecurityConfigurerAdapter {

	/**
	 * /myAccount - Secured /myBalance - Secured /myLoans - Secured /myCards -
	 * Secured /notices - Not Secured /contact - Not Secured
	 */
	@Override
	protected void configure(HttpSecurity http) throws Exception {
		http.authorizeRequests().antMatchers("/myAccount").authenticated().antMatchers("/myBalance").authenticated()
				.antMatchers("/myLoans").authenticated().antMatchers("/myCards").authenticated().antMatchers("/notices")
				.permitAll().antMatchers("/contact").permitAll().and().formLogin().and().httpBasic();
	}

	
	 @Override protected void configure(AuthenticationManagerBuilder auth) throws
	  Exception {
	  auth.inMemoryAuthentication().withUser("admin").password("12345").authorities
	  ("admin").and(). withUser("user").password("12345").authorities("read").and()
	  .passwordEncoder(NoOpPasswordEncoder.getInstance()); }
	 

}
```

 chỉ có admin hay user 12345 mới có thể login

vs user trong [application.properties](http://application.properties) thì k thể ⇒ xoá values đi

## Configuring users using InMemoryUserDetailsManager

Uncomment

```java

	 * @Override protected void configure(AuthenticationManagerBuilder auth) throws
	 * Exception { 
		InMemoryUserDetailsManager userDetailsService = new
	 * InMemoryUserDetailsManager(); 
		 UserDetails user =
	 * User.withUsername("admin").password("12345").authorities("admin").build();
	 * UserDetails user1 =
	 * User.withUsername("user").password("12345").authorities("read").build();

	 * userDetailsService.createUser(user); 
		 userDetailsService.createUser(user1);
	 * auth.userDetailsService(userDetailsService); }
```

Log in with admin’

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2023.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2024.png)

 Add to class above

```java
@Bean
	public PasswordEncoder passwordEncoder() {
		return NoOpPasswordEncoder.getInstance();
	}
```

## Understanding User Management interfaces and Classes

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2025.png)

## Deep Dive of UserDetails Interface

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2026.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2027.png)

we have constructor and 

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2028.png)

## Deep Dive of UserDetailsService Interface

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2029.png)

Tại sao k query trực tiếp vào db ⇒ bad practice ⇒ see log

## Deep Dive of UserDetailsManager Interface

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2030.png)

## Deep Dive of UserDetailsManager Implementations

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2031.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2032.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2033.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2034.png)

 can add breakpoint here

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2035.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2036.png)

## Creating MySQL Database in AWS

![Screen Shot 2022-03-04 at 11.25.24.png](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Screen_Shot_2022-03-04_at_11.25.24.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2037.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2038.png)

click create 

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2039.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2040.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2041.png)

Download sqlelectron

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2042.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2043.png)

## Creating Users inside the DB as per JdbcUserDetailsManager class

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2044.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2045.png)

[https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/resources/sql/scripts.sql](https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/resources/sql/scripts.sql)

```java
create database eazybank;

use eazybank;

CREATE TABLE `users` (
`id` INT NOT NULL AUTO_INCREMENT,
`username` VARCHAR(45) NOT NULL,
`password` VARCHAR(45) NOT NULL,
`enabled` INT NOT NULL,
PRIMARY KEY (`id`));

CREATE TABLE `authorities` (
  `id` int NOT NULL AUTO_INCREMENT,
  `username` varchar(45) NOT NULL,
  `authority` varchar(45) NOT NULL,
  PRIMARY KEY (`id`));

INSERT IGNORE INTO `users` VALUES (NULL, 'happy', '12345', '1');
INSERT IGNORE INTO `authorities` VALUES (NULL, 'happy', 'write');

CREATE TABLE `customer` (
  `id` int NOT NULL AUTO_INCREMENT,
  `email` varchar(45) NOT NULL,
  `pwd` varchar(45) NOT NULL,
  `role` varchar(45) NOT NULL,
  PRIMARY KEY (`id`)
);

INSERT INTO `customer` (`email`, `pwd`, `role`)
 VALUES ('johndoe@example.com', '54321', 'admin');
```

## Using JdbcUserDetailsManager to perform authentication

pom.xml

```java
		<dependency>
			<groupId>org.springframework.ldap</groupId>
			<artifactId>spring-ldap-core</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.security</groupId>
			<artifactId>spring-security-ldap</artifactId>
		</dependency>

      <dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-jdbc</artifactId>
		</dependency>
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
```

```java
spring.datasource.url=jdbc:mysql://database-2.c5f7inlufhnn.ap-south-1.rds.amazonaws.com/eazybank
spring.datasource.username=admin
spring.datasource.password=MySQLSpringSecurity
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2046.png)

Uncomment

```java
/*
	 * @Bean public UserDetailsService userDetailsService(DataSource dataSource) {
	 * return new JdbcUserDetailsManager(dataSource); }
	 */
	

	@Bean
	public PasswordEncoder passwordEncoder() {
		return NoOpPasswordEncoder.getInstance();
	}
```

Test login with happy

## Creating our own custom implementation of UserDetailsService

create table customer

[https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/model/Customer.java](https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/model/Customer.java)

```java
package com.eazybytes.model;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class Customer {

	@Id
	@GeneratedValue(strategy=GenerationType.AUTO)
	private int id;
	private String email;
	private String pwd;
	private String role;

	public int getId() {
		return id;
	}

	public void setId(int id) {
		this.id = id;
	}

	public String getEmail() {
		return email;
	}

	public void setEmail(String email) {
		this.email = email;
	}

	public String getPwd() {
		return pwd;
	}

	public void setPwd(String pwd) {
		this.pwd = pwd;
	}

	public String getRole() {
		return role;
	}

	public void setRole(String role) {
		this.role = role;
	}}
```

[https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/repository/CustomerRepository.java](https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/repository/CustomerRepository.java)

```java
@Repository
public interface CustomerRepository extends CrudRepository<Customer, Long> {
	
	List<Customer> findByEmail(String email);

}
```

[https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/model/SecurityCustomer.java](https://github.com/eazybytes/spring-security/blob/main/section3/springsecsection3/src/main/java/com/eazybytes/model/SecurityCustomer.java)

```java
public class SecurityCustomer implements UserDetails {

	/**
	 * 
	 */
	private static final long serialVersionUID = -6690946490872875352L;

	private final Customer customer;

	public SecurityCustomer(Customer customer) {
		this.customer = customer;
	}

	@Override
	public Collection<? extends GrantedAuthority> getAuthorities() {
		List<GrantedAuthority> authorities = new ArrayList<>();
		authorities.add(new SimpleGrantedAuthority(customer.getRole()));
		return authorities;
	}

	@Override
	public String getPassword() {
		return customer.getPwd();
	}

	@Override
	public String getUsername() {
		return customer.getEmail();
	}

	@Override
	public boolean isAccountNonExpired() {
		return true;
	}

	@Override
	public boolean isAccountNonLocked() {
		return true;
	}

	@Override
	public boolean isCredentialsNonExpired() {
		return true;
	}

	@Override
	public boolean isEnabled() {
		return true;
	}

}
```

EazyBankUserDetails

```java
package com.eazybytes.config;

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.security.core.userdetails.UserDetails;
import org.springframework.security.core.userdetails.UserDetailsService;
import org.springframework.security.core.userdetails.UsernameNotFoundException;
import org.springframework.stereotype.Service;

import com.eazybytes.model.Customer;
import com.eazybytes.model.SecurityCustomer;
import com.eazybytes.repository.CustomerRepository;

@Service
public class EazyBankUserDetails implements UserDetailsService {

	@Autowired
	private CustomerRepository customerRepository;

	@Override
	public UserDetails loadUserByUsername(String username) throws UsernameNotFoundException {
		List<Customer> customer = customerRepository.findByEmail(username);
		if (customer.size() == 0) {
			throw new UsernameNotFoundException("User details not found for the user : " + username);
		}
		return new SecurityCustomer(customer.get(0));
	}

}
```

comment

```java
/*
	 * @Bean public UserDetailsService userDetailsService(DataSource dataSource) {
	 * return new JdbcUserDetailsManager(dataSource); }
	 */
	
```

EazyBankBackendApplication add @EnableJpaRepositories("com.eazybytes.repository")

```java
package com.eazybytes.application;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.boot.autoconfigure.domain.EntityScan;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.ComponentScans;
import org.springframework.data.jpa.repository.config.EnableJpaRepositories;

@SpringBootApplication
@ComponentScans({ @ComponentScan("com.eazybytes.controller"), @ComponentScan("com.eazybytes.config")})
@EnableJpaRepositories("com.eazybytes.repository")
@EntityScan("com.eazybytes.model")
public class EazyBankBackendApplication {

	public static void main(String[] args) {
		SpringApplication.run(EazyBankBackendApplication.class, args);
	}

}
```

Test with [johndoe@example.com](mailto:johndoe@example.com)

## Summary of the section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2047.png)

# Password Management with PasswordEncoders

## How our passwords validated in Spring Security by default

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2048.png)

## Encoding Vs Encryption Vs Hashing

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2049.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2050.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2051.png)

## How Our passwords will be validated with hashing by Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2052.png)

## Definition of the PasswordEncoder

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2053.png)

## Deepdive into NoOpPasswordEncoder

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2054.png)

## Deepdive into StandardPasswordEncoder

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2055.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2056.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2057.png)

## Deepdive into Bcrypt and Scrypt PasswordEncoders

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2058.png)

## Deepdive into Pbkdf2PasswordEncoder

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2059.png)

⇒ slow

256 bit

18500 is address

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2060.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2061.png)

## Implementing and enhancing our application to use Bcrypt password encoder

```java
@Bean
	public PasswordEncoder passwordEncoder() {
		return new BCryptPasswordEncoder();
	}
```

```java
CREATE TABLE `customer` (
  `id` int NOT NULL AUTO_INCREMENT,
  `email` varchar(45) NOT NULL,
  `pwd` varchar(200) NOT NULL,
  `role` varchar(45) NOT NULL,
  PRIMARY KEY (`id`)
);

INSERT INTO `customer` (`email`, `pwd`, `role`)
 VALUES ('johndoe@example.com', '54321', 'admin');
 
INSERT INTO `customer` (`email`, `pwd`, `role`)
 VALUES ('happy@example.com', '$2y$12$oRRbkNfwuR8ug4MlzH5FOeui.//1mkd.RsOAJMbykTSupVy.x/vb2', 'admin');
```

[https://bcrypt-generator.com/](https://bcrypt-generator.com/)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2062.png)

Login with happy ⇒ ok

johndoe@example.com ⇒ failed

## Details about Spring Security Crypto package

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2063.png)

## Summary of the section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2064.png)

# Understanding Authentication Provider and Implementing it

## Role of AuthenticationProvider in the Spring Security flow

## Scenarios where we need to implement Authentication Provider

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2065.png)

## Understanding Authentication Provider definition

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2066.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2067.png)

## Understanding Authentication & Principal Interfaces

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2068.png)

## Implementing and Customizing the Authentication Provider inside our application

EazyBankUsernamePwdAuthenticationProvider

```java
package com.eazybytes.config;

import java.util.ArrayList;
import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.security.authentication.AuthenticationProvider;
import org.springframework.security.authentication.BadCredentialsException;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.Authentication;
import org.springframework.security.core.GrantedAuthority;
import org.springframework.security.core.authority.SimpleGrantedAuthority;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.stereotype.Component;

import com.eazybytes.model.Customer;
import com.eazybytes.repository.CustomerRepository;

@Component
public class EazyBankUsernamePwdAuthenticationProvider implements AuthenticationProvider {

	@Autowired
	private CustomerRepository customerRepository;
	
	@Autowired
	private PasswordEncoder passwordEncoder;

	@Override
	public Authentication authenticate(Authentication authentication) {
		String username = authentication.getName();
		String pwd = authentication.getCredentials().toString();
		List<Customer> customer = customerRepository.findByEmail(username);
		if (customer.size() > 0) {
			if (passwordEncoder.matches(pwd, customer.get(0).getPwd())) {
				List<GrantedAuthority> authorities = new ArrayList<>();
				authorities.add(new SimpleGrantedAuthority(customer.get(0).getRole()));
				return new UsernamePasswordAuthenticationToken(username, pwd, authorities);
			} else {
				throw new BadCredentialsException("Invalid password!");
			}
		} else {
			throw new BadCredentialsException("No user registered with this details!");
		}
	}

	@Override
	public boolean supports(Class<?> authenticationType) {
		return authenticationType.equals(UsernamePasswordAuthenticationToken.class);
	}
}
```

Add @Component to spring know

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2069.png)

 not run into EazyBankUserDetails

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2070.png)

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2071.png)

# Understanding CORs & CSRF

## Setting up the EazyBank UI project

[1 - Angular-Project-Setup.pdf](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/1_-_Angular-Project-Setup.pdf)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2072.png)

1. 1)  Download and Install the node.js from https://nodejs.org/en/download/ as per your operating
system and check if the installation is successful using the command ‘node -v’ which will print
the current installed version.

2. 2)  Run the command ‘npm install -g @angular/cli’ to install Angular CLI.

3. 3)  Download the visual code using the link https://code.visualstudio.com/ and import the angular

project provided.

4. 4)  Navigate to the folder inside the project where package.json is present and run the command

‘npm install’ by opening a terminal. This will install all the dependencies inside the new folder

created with the name ‘node_modules’

5. 5)  Run the command ‘ng serve’ and it will start the application at ‘http://localhost:4200/’ by

default.

## Understanding the UI project and walkthrough of the Angular code

[https://github.com/eazybytes/spring-security/blob/main/section6/bankappui/bank-app-ui/src/app/app-routing.module.ts](https://github.com/eazybytes/spring-security/blob/main/section6/bankappui/bank-app-ui/src/app/app-routing.module.ts)

## Understanding the backend project and walkthrough of the latest code

[https://github.com/eazybytes/spring-security/blob/main/section6/springsecsection6/src/main/java/com/eazybytes/application/EazyBankBackendApplication.java](https://github.com/eazybytes/spring-security/blob/main/section6/springsecsection6/src/main/java/com/eazybytes/application/EazyBankBackendApplication.java)

Update controller 

sql

```java
create database eazybank;

use eazybank;

CREATE TABLE `users` (
`id` INT NOT NULL AUTO_INCREMENT,
`username` VARCHAR(45) NOT NULL,
`password` VARCHAR(45) NOT NULL,
`enabled` INT NOT NULL,
PRIMARY KEY (`id`));

CREATE TABLE `authorities` (
  `id` int NOT NULL AUTO_INCREMENT,
  `username` varchar(45) NOT NULL,
  `authority` varchar(45) NOT NULL,
  PRIMARY KEY (`id`));

INSERT IGNORE INTO `users` VALUES (NULL, 'happy', '12345', '1');
INSERT IGNORE INTO `authorities` VALUES (NULL, 'happy', 'write');

CREATE TABLE `customer` (
  `id` int NOT NULL AUTO_INCREMENT,
  `email` varchar(45) NOT NULL,
  `pwd` varchar(200) NOT NULL,
  `role` varchar(45) NOT NULL,
  PRIMARY KEY (`id`)
);

INSERT INTO `customer` (`email`, `pwd`, `role`)
 VALUES ('johndoe@example.com', '54321', 'admin');
 
INSERT INTO `customer` (`email`, `pwd`, `role`)
 VALUES ('happy@example.com', '$2y$12$oRRbkNfwuR8ug4MlzH5FOeui.//1mkd.RsOAJMbykTSupVy.x/vb2', 'admin');
 
CREATE TABLE `customer` (
  `customer_id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `email` varchar(100) NOT NULL,
  `mobile_number` varchar(20) NOT NULL,
  `pwd` varchar(500) NOT NULL,
  `role` varchar(100) NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`customer_id`)
);

INSERT INTO `customer` (`name`,`email`,`mobile_number`, `pwd`, `role`,`create_dt`)
 VALUES ('Happy','happy@example.com','9876548337', '$2y$12$oRRbkNfwuR8ug4MlzH5FOeui.//1mkd.RsOAJMbykTSupVy.x/vb2', 'admin',CURDATE());
 
CREATE TABLE `accounts` (
  `customer_id` int NOT NULL,
   `account_number` int NOT NULL,
  `account_type` varchar(100) NOT NULL,
  `branch_address` varchar(200) NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`account_number`),
  KEY `customer_id` (`customer_id`),
  CONSTRAINT `customer_ibfk_1` FOREIGN KEY (`customer_id`) REFERENCES `customer` (`customer_id`) ON DELETE CASCADE
);

INSERT INTO `accounts` (`customer_id`, `account_number`, `account_type`, `branch_address`, `create_dt`)
 VALUES (1, 186576453434, 'Savings', '123 Main Street, New York', CURDATE());
 
CREATE TABLE `account_transactions` (
  `transaction_id` varchar(200) NOT NULL,
  `account_number` int NOT NULL,
  `customer_id` int NOT NULL,
  `transaction_dt` date NOT NULL,
  `transaction_summary` varchar(200) NOT NULL,
  `transaction_type` varchar(100) NOT NULL,
  `transaction_amt` int NOT NULL,
  `closing_balance` int NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`transaction_id`),
  KEY `customer_id` (`customer_id`),
  KEY `account_number` (`account_number`),
  CONSTRAINT `accounts_ibfk_2` FOREIGN KEY (`account_number`) REFERENCES `accounts` (`account_number`) ON DELETE CASCADE,
  CONSTRAINT `acct_user_ibfk_1` FOREIGN KEY (`customer_id`) REFERENCES `customer` (`customer_id`) ON DELETE CASCADE
);

 
INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `customer_id`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453434, 1, CURDATE()-7, 'Coffee Shop', 'Withdrawal', 30,34500,CURDATE()-7);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `customer_id`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453434, 1, CURDATE()-6, 'Uber', 'Withdrawal', 100,34400,CURDATE()-6);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `customer_id`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453434, 1, CURDATE()-5, 'Self Deposit', 'Deposit', 500,34900,CURDATE()-5);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `customer_id`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453434, 1, CURDATE()-4, 'Ebay', 'Withdrawal', 600,34300,CURDATE()-4);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `customer_id`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453434, 1, CURDATE()-2, 'OnlineTransfer', 'Deposit', 700,35000,CURDATE()-2);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `customer_id`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453434, 1, CURDATE()-1, 'Amazon.com', 'Withdrawal', 100,34900,CURDATE()-1);

CREATE TABLE `loans` (
  `loan_number` int NOT NULL AUTO_INCREMENT,
  `customer_id` int NOT NULL,
  `start_dt` date NOT NULL,
  `loan_type` varchar(100) NOT NULL,
  `total_loan` int NOT NULL,
  `amount_paid` int NOT NULL,
  `outstanding_amount` int NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`loan_number`),
  KEY `customer_id` (`customer_id`),
  CONSTRAINT `loan_customer_ibfk_1` FOREIGN KEY (`customer_id`) REFERENCES `customer` (`customer_id`) ON DELETE CASCADE
);

INSERT INTO `loans` ( `customer_id`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 1, '2020-10-13', 'Home', 200000, 50000, 150000, '2020-10-13');
 
INSERT INTO `loans` ( `customer_id`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 1, '2020-06-06', 'Vehicle', 40000, 10000, 30000, '2020-06-06');
 
INSERT INTO `loans` ( `customer_id`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 1, '2018-02-14', 'Home', 50000, 10000, 40000, '2018-02-14');

INSERT INTO `loans` ( `customer_id`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 1, '2018-02-14', 'Personal', 10000, 3500, 6500, '2018-02-14');

CREATE TABLE `cards` (
  `card_id` int NOT NULL AUTO_INCREMENT,
  `card_number` varchar(100) NOT NULL,
  `customer_id` int NOT NULL,
  `card_type` varchar(100) NOT NULL,
  `total_limit` int NOT NULL,
  `amount_used` int NOT NULL,
  `available_amount` int NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`card_id`),
  KEY `customer_id` (`customer_id`),
  CONSTRAINT `card_customer_ibfk_1` FOREIGN KEY (`customer_id`) REFERENCES `customer` (`customer_id`) ON DELETE CASCADE
);

INSERT INTO `cards` (`card_number`, `customer_id`, `card_type`, `total_limit`, `amount_used`, `available_amount`, `create_dt`)
 VALUES ('4565XXXX4656', 1, 'Credit', 10000, 500, 9500, CURDATE());

INSERT INTO `cards` (`card_number`, `customer_id`, `card_type`, `total_limit`, `amount_used`, `available_amount`, `create_dt`)
 VALUES ('3455XXXX8673', 1, 'Credit', 7500, 600, 6900, CURDATE());
 
INSERT INTO `cards` (`card_number`, `customer_id`, `card_type`, `total_limit`, `amount_used`, `available_amount`, `create_dt`)
 VALUES ('2359XXXX9346', 1, 'Credit', 20000, 4000, 16000, CURDATE());
 
CREATE TABLE `notice_details` (
  `notice_id` int NOT NULL AUTO_INCREMENT,
  `notice_summary` varchar(200) NOT NULL,
  `notice_details` varchar(500) NOT NULL,
  `notic_beg_dt` date NOT NULL,
  `notic_end_dt` date DEFAULT NULL,
  `create_dt` date DEFAULT NULL,
  `update_dt` date DEFAULT NULL,
  PRIMARY KEY (`notice_id`)
);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Home Loan Interest rates reduced', 'Home loan interest rates are reduced as per the goverment guidelines. The updated rates will be effective immediately', 
'2020-10-14', '2020-11-30', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Net Banking Offers', 'Customers who will opt for Internet banking while opening a saving account will get a $50 amazon voucher', 
'2020-10-14', '2020-12-05', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Mobile App Downtime', 'The mobile application of the EazyBank will be down from 2AM-5AM on 12/05/2020 due to maintenance activities', 
'2020-10-14', '2020-12-01', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('E Auction notice', 'There will be a e-auction on 12/08/2020 on the Bank website for all the stubborn arrears.Interested parties can participate in the e-auction', 
'2020-10-14', '2020-12-08', CURDATE(), null);
   
INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Launch of Millennia Cards', 'Millennia Credit Cards are launched for the premium customers of EazyBank. With these cards, you will get 5% cashback for each purchase', 
'2020-10-14', '2020-11-28', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('COVID-19 Insurance', 'EazyBank launched an insurance policy which will cover COVID-19 expenses. Please reach out to the branch for more details', 
'2020-10-14', '2020-12-31', CURDATE(), null);

CREATE TABLE `contact_messages` (
  `contact_id` varchar(50) NOT NULL,
  `contact_name` varchar(50) NOT NULL,
  `contact_email` varchar(100) NOT NULL,
  `subject` varchar(500) NOT NULL,
  `message` varchar(2000) NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`contact_id`)
);
```

## Testing the EazyBank application with both UI and Backend applications up

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2073.png)

## Deep dive into CORS (CROSS-ORIGIN RESOURCE SHARING)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2074.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2075.png)

## Making code changes to resolve CORS issue

run app ⇒ log in ⇒ run into cors ⇒ allow cors ⇒call again ⇒ 403 due to csrf when call post method not get

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2076.png)

```java
package com.eazybytes.config;

import java.util.Collections;

import javax.servlet.http.HttpServletRequest;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.security.web.csrf.CookieCsrfTokenRepository;
import org.springframework.web.cors.CorsConfiguration;
import org.springframework.web.cors.CorsConfigurationSource;

@Configuration
public class ProjectSecurityConfig extends WebSecurityConfigurerAdapter {

	/**
	 * /myAccount - Secured /myBalance - Secured /myLoans - Secured /myCards -
	 * Secured /notices - Not Secured /contact - Not Secured
	 */
	@Override
	protected void configure(HttpSecurity http) throws Exception {

		http.cors().configurationSource(new CorsConfigurationSource() {
			@Override
			public CorsConfiguration getCorsConfiguration(HttpServletRequest request) {
				CorsConfiguration config = new CorsConfiguration();
				config.setAllowedOrigins(Collections.singletonList("http://localhost:4200"));
				config.setAllowedMethods(Collections.singletonList("*"));
				config.setAllowCredentials(true);
				config.setAllowedHeaders(Collections.singletonList("*"));
				config.setMaxAge(3600L);
				return config;
			}
		}).and().csrf().ignoringAntMatchers("/contact").csrfTokenRepository(CookieCsrfTokenRepository.withHttpOnlyFalse()).and().
		authorizeRequests().antMatchers("/myAccount").authenticated().antMatchers("/myBalance").authenticated()
				.antMatchers("/myLoans").authenticated().antMatchers("/myCards").authenticated()
				.antMatchers("/user").authenticated().antMatchers("/notices").permitAll()
				.antMatchers("/contact").permitAll().and().httpBasic();
	}
	
	/*
	 * @Override protected void configure(AuthenticationManagerBuilder auth) throws
	 * Exception {
	 * auth.inMemoryAuthentication().withUser("admin").password("12345").authorities
	 * ("admin").and(). withUser("user").password("12345").authorities("read").and()
	 * .passwordEncoder(NoOpPasswordEncoder.getInstance()); }
	 */

	/*
	 * @Override protected void configure(AuthenticationManagerBuilder auth) throws
	 * Exception { InMemoryUserDetailsManager userDetailsService = new
	 * InMemoryUserDetailsManager(); UserDetails user =
	 * User.withUsername("admin").password("12345").authorities("admin").build();
	 * UserDetails user1 =
	 * User.withUsername("user").password("12345").authorities("read").build();
	 * userDetailsService.createUser(user); userDetailsService.createUser(user1);
	 * auth.userDetailsService(userDetailsService); }
	 */

	/*
	 * @Bean public UserDetailsService userDetailsService(DataSource dataSource) {
	 * return new JdbcUserDetailsManager(dataSource); }
	 */

	@Bean
	public PasswordEncoder passwordEncoder() {
		return new BCryptPasswordEncoder();
	}
}
```

## Deep dive into CSRF (CROSS-SITE REQUEST FORGERY)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2077.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2078.png)

## Resolving CSRF error by disabling it in Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2079.png)

go to balance ok

## Resolving CFRF error by generating a CSRF token

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2080.png)

Thêm phần còn lại để generate token every first request

 CookieCsrfTokenRepository.withHttpOnlyFalse: token or cookie can be read by UI

```java
import { Component, OnInit } from '@angular/core';
import { User } from "src/app/model/user.model";
import { NgForm } from '@angular/forms';
import { LoginService } from 'src/app/services/login/login.service';
import { Router } from '@angular/router';

@Component({
  selector: 'app-login',
  templateUrl: './login.component.html',
  styleUrls: ['./login.component.css']
})
export class LoginComponent implements OnInit {
  authStatus: string;
  model = new User();

  constructor(private loginService: LoginService, private router: Router) {

   }

  ngOnInit(): void {

  }

  validateUser(loginForm: NgForm) {
    this.loginService.validateLoginDetails(this.model).subscribe(
      responseData => {
        this.model = <any> responseData.body;
        this.model.authStatus = 'AUTH';
        window.sessionStorage.setItem("userdetails",JSON.stringify(this.model));
        let xsrf = this.getCookie('XSRF-TOKEN');
        window.sessionStorage.setItem("XSRF-TOKEN",xsrf);
        this.router.navigate(['dashboard']);
      }, error => {
        console.log(error);
      });

  }

  getCookie(name) {
    let cookie = {};
    document.cookie.split(';').forEach(function(el) {
      let [k,v] = el.split('=');
      cookie[k.trim()] = v;
    })
    return cookie[name];
  }

}
```

interceptor

```java
import { Injectable } from '@angular/core';
import { HttpInterceptor,HttpRequest,HttpHandler,HttpErrorResponse, HttpHeaders } from '@angular/common/http';
import {Router} from '@angular/router';
import {tap} from 'rxjs/operators';
import { User } from 'src/app/model/user.model';

@Injectable()
export class XhrInterceptor implements HttpInterceptor {

  user = new User();
  constructor(private router: Router) {}

  intercept(req: HttpRequest<any>, next: HttpHandler) {
    let httpHeaders = new HttpHeaders();
    this.user = JSON.parse(sessionStorage.getItem('userdetails'));
    if(this.user && this.user.password && this.user.email){
      httpHeaders = httpHeaders.append('Authorization', 'Basic ' + btoa(this.user.email + ':' + this.user.password));
    }
    let xsrf = sessionStorage.getItem('XSRF-TOKEN');
    if(xsrf){
      httpHeaders = httpHeaders.append('X-XSRF-TOKEN', xsrf);  
    }
    httpHeaders = httpHeaders.append('X-Requested-With', 'XMLHttpRequest');
    const xhr = req.clone({
      headers: httpHeaders
    });
  return next.handle(xhr).pipe(tap(() => { },
      (err: any) => {
        if (err instanceof HttpErrorResponse) {
          if (err.status !== 401) {
            return;
          }
          this.router.navigate(['dashboard']);
        }
      }));
  }
} 
```

## Making Spring Security changes to make CSRF not applicable for Contact page

in contact page user not log in and go to contact call api ⇒ 403

```java
.csrf().ignoringAntMatchers("/contact")
```

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2081.png)

# Understanding & Implementing Authorization

## Authentication Vs Authorization

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2082.png)

e.g: when we have a flight we need to verify identity, passport number... It is authorized, care about role, authorities, rules,..

## Spring Security Internal flow for AUTHN & AUTHZ

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2083.png)

## How Authorities stored in Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2084.png)

example

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2085.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2086.png)

## Configuring Authorities in Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2087.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2088.png)

Add method hasAuthority

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2089.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2090.png)

[https://github.com/eazybytes/spring-security/blob/main/section7/springsecsection7/src/main/java/com/eazybytes/model/Customer.java](https://github.com/eazybytes/spring-security/blob/main/section7/springsecsection7/src/main/java/com/eazybytes/model/Customer.java)

```java
@JsonIgnore
	@OneToMany(mappedBy="customer",fetch=FetchType.EAGER)
	private Set<Authority> authorities; 
```

Authority

```java
package com.eazybytes.model;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.ManyToOne;
import javax.persistence.Table;

@Entity
@Table(name = "authorities")
public class Authority {

	@Id
	@GeneratedValue(strategy = GenerationType.AUTO)
	private Long id;

	private String name;

	@ManyToOne
	@JoinColumn(name = "customer_id")
	private Customer customer;

	public Long getId() {
		return id;
	}

	public void setId(Long id) {
		this.id = id;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public Customer getCustomer() {
		return customer;
	}

	public void setCustomer(Customer customer) {
		this.customer = customer;
	}
}
```

```java
package com.eazybytes.config;

import java.util.ArrayList;
import java.util.List;
import java.util.Set;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.security.authentication.AuthenticationProvider;
import org.springframework.security.authentication.BadCredentialsException;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.Authentication;
import org.springframework.security.core.GrantedAuthority;
import org.springframework.security.core.authority.SimpleGrantedAuthority;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.stereotype.Component;

import com.eazybytes.model.Authority;
import com.eazybytes.model.Customer;
import com.eazybytes.repository.CustomerRepository;

@Component
public class EazyBankUsernamePwdAuthenticationProvider implements AuthenticationProvider {

	@Autowired
	private CustomerRepository customerRepository;
	
	@Autowired
	private PasswordEncoder passwordEncoder;

	@Override
	public Authentication authenticate(Authentication authentication) {
		String username = authentication.getName();
		String pwd = authentication.getCredentials().toString();
		List<Customer> customer = customerRepository.findByEmail(username);
		if (customer.size() > 0) {
			if (passwordEncoder.matches(pwd, customer.get(0).getPwd())) {
				return new UsernamePasswordAuthenticationToken(username, pwd, getGrantedAuthorities(customer.get(0).getAuthorities()));
			} else {
				throw new BadCredentialsException("Invalid password!");
			}
		}else {
			throw new BadCredentialsException("No user registered with this details!");
		}
	}
	
	private List<GrantedAuthority> getGrantedAuthorities(Set<Authority> authorities) {
		List<GrantedAuthority> grantedAuthorities = new ArrayList<>();
        for (Authority authority : authorities) {
        	grantedAuthorities.add(new SimpleGrantedAuthority(authority.getName()));
        }
        return grantedAuthorities;
    }

	@Override
	public boolean supports(Class<?> authenticationType) {
		return authenticationType.equals(UsernamePasswordAuthenticationToken.class);
	}
}
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2091.png)

email with happy can access most of all but for myLoans since we don't have right to access  

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2092.png)

## Authority Vs Role

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2093.png)

## Configuring Roles in Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2094.png)

```java
@Override
	protected void configure(HttpSecurity http) throws Exception {

		http.cors().configurationSource(new CorsConfigurationSource() {
			@Override
			public CorsConfiguration getCorsConfiguration(HttpServletRequest request) {
				CorsConfiguration config = new CorsConfiguration();
				config.setAllowedOrigins(Collections.singletonList("http://localhost:4200"));
				config.setAllowedMethods(Collections.singletonList("*"));
				config.setAllowCredentials(true);
				config.setAllowedHeaders(Collections.singletonList("*"));
				config.setMaxAge(3600L);
				return config;
			}
		}).and().csrf().ignoringAntMatchers("/contact").csrfTokenRepository(CookieCsrfTokenRepository.withHttpOnlyFalse())
				.and().authorizeRequests()
				.antMatchers("/myAccount").hasRole("USER")
				.antMatchers("/myBalance").hasAnyRole("USER","ADMIN")
				.antMatchers("/myLoans").hasRole("ROOT")
				.antMatchers("/myCards").authenticated()
				.antMatchers("/user").authenticated()
				.antMatchers("/notices").permitAll()
				.antMatchers("/contact").permitAll().and().httpBasic();
	} 
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2095.png)

go to loan ⇒ 403

## Deep dive of Ant, MVC, Regex matchers for applying restrictions on the paths

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2096.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2097.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2098.png)

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%2099.png)

# Filters in Spring Security

## Introduction to Filters in Spring Security and the sample use cases

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20100.png)

## Inbuilt Filters provided by Spring Security and validating them inside our app

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20101.png)

```java
@EnableWebSecurity(debug = true)
public class EazyBankBackendApplication
```

[https://github.com/eazybytes/spring-security/blob/main/section8/springsecsection8/src/main/resources/application.properties](https://github.com/eazybytes/spring-security/blob/main/section8/springsecsection8/src/main/resources/application.properties)

```java
logging.level.org.springframework.security.web.FilterChainProxy=DEBUG
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20102.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20103.png)

not for production

## Implementing our own custom filter in Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20104.png)

## Adding a custom filter using addFilterBefore() method

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20105.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20106.png)

[https://github.com/eazybytes/spring-security/blob/main/section8/springsecsection8/src/main/java/com/eazybytes/filter/RequestValidationBeforeFilter.java](https://github.com/eazybytes/spring-security/blob/main/section8/springsecsection8/src/main/java/com/eazybytes/filter/RequestValidationBeforeFilter.java)

```java
package com.eazybytes.filter;

import static org.springframework.http.HttpHeaders.AUTHORIZATION;

import java.io.IOException;
import java.nio.charset.Charset;
import java.nio.charset.StandardCharsets;
import java.util.Base64;

import javax.servlet.Filter;
import javax.servlet.FilterChain;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import org.springframework.security.authentication.BadCredentialsException;
import org.springframework.util.StringUtils;

public class RequestValidationBeforeFilter implements Filter {

	public static final String AUTHENTICATION_SCHEME_BASIC = "Basic";
	private Charset credentialsCharset = StandardCharsets.UTF_8;

	@Override
	public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain)
			throws IOException, ServletException {
		HttpServletRequest req = (HttpServletRequest) request;
		HttpServletResponse res = (HttpServletResponse) response;
		String header = req.getHeader(AUTHORIZATION);
		if (header != null) {
			header = header.trim();
			if (StringUtils.startsWithIgnoreCase(header, AUTHENTICATION_SCHEME_BASIC)) {
				byte[] base64Token = header.substring(6).getBytes(StandardCharsets.UTF_8);
				byte[] decoded;
				try {
					decoded = Base64.getDecoder().decode(base64Token);
					String token = new String(decoded, getCredentialsCharset(req));
					int delim = token.indexOf(":");
					if (delim == -1) {
						throw new BadCredentialsException("Invalid basic authentication token");
					}
					String email = token.substring(0, delim);
					if(email.toLowerCase().contains("test")) {
						res.setStatus(HttpServletResponse.SC_BAD_REQUEST);
						return;
					}
				} catch (IllegalArgumentException e) {
					throw new BadCredentialsException("Failed to decode basic authentication token");
				}
			}
		}
		chain.doFilter(request, response);
	}

	protected Charset getCredentialsCharset(HttpServletRequest request) {
		return getCredentialsCharset();
	}

	public Charset getCredentialsCharset() {
		return this.credentialsCharset;
	}

}
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20107.png)

```java
@Override
	protected void configure(HttpSecurity http) throws Exception {

		http.cors().configurationSource(new CorsConfigurationSource() {
			@Override
			public CorsConfiguration getCorsConfiguration(HttpServletRequest request) {
				CorsConfiguration config = new CorsConfiguration();
				config.setAllowedOrigins(Collections.singletonList("http://localhost:4200"));
				config.setAllowedMethods(Collections.singletonList("*"));
				config.setAllowCredentials(true);
				config.setAllowedHeaders(Collections.singletonList("*"));
				config.setMaxAge(3600L);
				return config;
			}
		}).and().csrf().ignoringAntMatchers("/contact").csrfTokenRepository(CookieCsrfTokenRepository.withHttpOnlyFalse())
				.and().addFilterBefore(new RequestValidationBeforeFilter(), BasicAuthenticationFilter.class)
				.addFilterAfter(new AuthoritiesLoggingAfterFilter(), BasicAuthenticationFilter.class)
				.addFilterAt(new AuthoritiesLoggingAtFilter(), BasicAuthenticationFilter.class)
				.authorizeRequests()
				.antMatchers("/myAccount").hasRole("USER")
				.antMatchers("/myBalance").hasAnyRole("USER","ADMIN")
				.antMatchers("/myLoans").hasRole("ROOT")
				.antMatchers("/myCards").hasAnyRole("USER","ADMIN")
				.antMatchers("/user").authenticated()
				.antMatchers("/notices").permitAll()
				.antMatchers("/contact").permitAll().and().httpBasic();
	} 
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20108.png)

Login with happytest@ .com ⇒ return 400 Bad request 

## Adding a custom filter using addFilterAfter() method

```java
package com.eazybytes.filter;

import java.io.IOException;
import java.util.logging.Logger;

import javax.servlet.Filter;
import javax.servlet.FilterChain;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;

import org.springframework.security.core.Authentication;
import org.springframework.security.core.context.SecurityContextHolder;

public class AuthoritiesLoggingAfterFilter implements Filter {

	private final Logger LOG =
			Logger.getLogger(AuthoritiesLoggingAfterFilter.class.getName());

	@Override
	public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain)
			throws IOException, ServletException {
		Authentication authentication = SecurityContextHolder.getContext().getAuthentication();
		if(null!=authentication) {
			LOG.info("User "+authentication.getName()+" is successfully authenticated and "
					+ "has the authorities "+authentication.getAuthorities().toString());
		}
		
		chain.doFilter(request, response);
	}

}
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20109.png)

## Adding a custom filter using addFilterAt() method

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20110.png)

```java
package com.eazybytes.filter;

import java.io.IOException;
import java.util.logging.Logger;

import javax.servlet.Filter;
import javax.servlet.FilterChain;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;

public class AuthoritiesLoggingAtFilter implements Filter {

	private final Logger LOG =
			Logger.getLogger(AuthoritiesLoggingAtFilter.class.getName());

	@Override
	public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain)
			throws IOException, ServletException {
		LOG.info("Authentication Validation is in progress");
		chain.doFilter(request, response);
	}

}
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20111.png)

## Details about GenericFilterBean and OncePerRequestFilter

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20112.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20113.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20114.png)

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20115.png)

# Token based Authentication using JSON Web Token (JWT)

## Introduction to Tokens in Authentication flow

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20116.png)

 

## Advantages of Token based Authentication

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20117.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20118.png)

## Exploring the JSESSIONID & CSRF Tokens inside our application

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20119.png)

update jsession ⇒ 401

delete xsrf

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20120.png)

## Deep dive about JWT Tokens

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20121.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20122.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20123.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20124.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20125.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20126.png)

## Making project configuration to use JWT tokens

add 

```java
<dependency>
			<groupId>io.jsonwebtoken</groupId>
			<artifactId>jjwt-api</artifactId>
			<version>0.11.1</version>
		</dependency>
		<dependency>
			<groupId>io.jsonwebtoken</groupId>
			<artifactId>jjwt-impl</artifactId>
			<version>0.11.1</version>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>io.jsonwebtoken</groupId>
			<artifactId>jjwt-jackson</artifactId>
			<version>0.11.1</version>
			<scope>runtime</scope>
		</dependency> 
```

disbale `.csrf().disable()` and http.sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS).and().

⇒ don't create history type or token

`config.setExposedHeaders(Arrays.asList("Authorization"));`

## Configuring filters to generate and validate JWT tokens

[https://github.com/eazybytes/spring-security/blob/main/section9/springsecsection9/src/main/java/com/eazybytes/filter/JWTTokenGeneratorFilter.java](https://github.com/eazybytes/spring-security/blob/main/section9/springsecsection9/src/main/java/com/eazybytes/filter/JWTTokenGeneratorFilter.java)

```java
package com.eazybytes.filter;

import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.util.Collection;
import java.util.Date;
import java.util.HashSet;
import java.util.Set;

import javax.crypto.SecretKey;
import javax.servlet.FilterChain;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import org.springframework.security.core.Authentication;
import org.springframework.security.core.GrantedAuthority;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.web.filter.OncePerRequestFilter;

import com.eazybytes.constants.SecurityConstants;

import io.jsonwebtoken.Jwts;
import io.jsonwebtoken.security.Keys;

public class JWTTokenGeneratorFilter extends OncePerRequestFilter {

	
	@Override
	public void doFilterInternal(HttpServletRequest request, HttpServletResponse response, FilterChain chain)
			throws IOException, ServletException {
		Authentication authentication = SecurityContextHolder.getContext().getAuthentication();
		if (null != authentication) {
			SecretKey key = Keys.hmacShaKeyFor(SecurityConstants.JWT_KEY.getBytes(StandardCharsets.UTF_8));
			String jwt = Jwts.builder().setIssuer("Eazy Bank").setSubject("JWT Token")
						.claim("username", authentication.getName())
					  .claim("authorities", populateAuthorities(authentication.getAuthorities()))
					  .setIssuedAt(new Date())
					.setExpiration(new Date((new Date()).getTime() + 3000000000))
					.signWith(key).compact();
			response.setHeader(SecurityConstants.JWT_HEADER, jwt);
		}

		chain.doFilter(request, response);
	}

	@Override
	protected boolean shouldNotFilter(HttpServletRequest request) {
		return !request.getServletPath().equals("/user");
	}
	
	private String populateAuthorities(Collection<? extends GrantedAuthority> collection) {
		Set<String> authoritiesSet = new HashSet<>();
        for (GrantedAuthority authority : collection) {
        	authoritiesSet.add(authority.getAuthority());
        }
        return String.join(",", authoritiesSet);
	}
}
```

 only filter login request

```java
package com.eazybytes.filter;

import java.io.IOException;
import java.nio.charset.StandardCharsets;

import javax.crypto.SecretKey;
import javax.servlet.FilterChain;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import org.springframework.security.authentication.BadCredentialsException;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.Authentication;
import org.springframework.security.core.authority.AuthorityUtils;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.web.filter.OncePerRequestFilter;

import com.eazybytes.constants.SecurityConstants;

import io.jsonwebtoken.Claims;
import io.jsonwebtoken.Jwts;
import io.jsonwebtoken.security.Keys;

public class JWTTokenValidatorFilter extends OncePerRequestFilter {

	
	@Override
	public void doFilterInternal(HttpServletRequest request, HttpServletResponse response, FilterChain chain)
			throws IOException, ServletException {
		String jwt = request.getHeader(SecurityConstants.JWT_HEADER);
		if (null != jwt) {
			try {
				SecretKey key = Keys.hmacShaKeyFor(
						SecurityConstants.JWT_KEY.getBytes(StandardCharsets.UTF_8));
				
				Claims claims = Jwts.parserBuilder()
						.setSigningKey(key)
						.build()
						.parseClaimsJws(jwt)
						.getBody();
				String username = String.valueOf(claims.get("username"));
				String authorities = (String) claims.get("authorities");
				Authentication auth = new UsernamePasswordAuthenticationToken(username,null,
						AuthorityUtils.commaSeparatedStringToAuthorityList(authorities));
				SecurityContextHolder.getContext().setAuthentication(auth);
			}catch (Exception e) {
				throw new BadCredentialsException("Invalid Token received!");
			}
			
		}
		chain.doFilter(request, response);
	}

	
	  @Override protected boolean shouldNotFilter(HttpServletRequest request) {
	  return request.getServletPath().equals("/user"); }
	 
	
} 
```

ProjectSecurityConfig

```java
@Override
	protected void configure(HttpSecurity http) throws Exception {

		http.sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS).and().
		cors().configurationSource(new CorsConfigurationSource() {
			@Override
			public CorsConfiguration getCorsConfiguration(HttpServletRequest request) {
				CorsConfiguration config = new CorsConfiguration();
				config.setAllowedOrigins(Collections.singletonList("http://localhost:4200"));
				config.setAllowedMethods(Collections.singletonList("*"));
				config.setAllowCredentials(true);
				config.setAllowedHeaders(Collections.singletonList("*"));
				config.setExposedHeaders(Arrays.asList("Authorization"));
				config.setMaxAge(3600L);
				return config;
			}
		}).and().csrf().disable()
				.addFilterBefore(new RequestValidationBeforeFilter(), BasicAuthenticationFilter.class)
				.addFilterAfter(new AuthoritiesLoggingAfterFilter(), BasicAuthenticationFilter.class)
				.addFilterBefore(new JWTTokenValidatorFilter(), BasicAuthenticationFilter.class)
				.addFilterAfter(new JWTTokenGeneratorFilter(), BasicAuthenticationFilter.class)
				.addFilterAt(new AuthoritiesLoggingAtFilter(), BasicAuthenticationFilter.class)
				.authorizeRequests()
				.antMatchers("/myAccount").hasRole("USER")
				.antMatchers("/myBalance").hasAnyRole("USER","ADMIN")
				.antMatchers("/myLoans").hasRole("ROOT")
				.antMatchers("/myCards").hasAnyRole("USER","ADMIN")
				.antMatchers("/user").authenticated()
				.antMatchers("/notices").permitAll()
				.antMatchers("/contact").permitAll().and().httpBasic();
	}
```

## Making changes on the client side for JWT token based authentication

[https://github.com/eazybytes/spring-security/blob/main/section9/bank-app-ui/src/app/components/login/login.component.ts](https://github.com/eazybytes/spring-security/blob/main/section9/bank-app-ui/src/app/components/login/login.component.ts)

```java
validateUser(loginForm: NgForm) {
    this.loginService.validateLoginDetails(this.model).subscribe(
      responseData => {
        window.sessionStorage.setItem("Authorization",responseData.headers.get('Authorization'));
        this.model = <any> responseData.body;
        this.model.authStatus = 'AUTH';
        window.sessionStorage.setItem("userdetails",JSON.stringify(this.model));
        this.router.navigate(['dashboard']);
      }, error => {
        console.log(error);
      });

  }
```

[https://github.com/eazybytes/spring-security/blob/main/section9/bank-app-ui/src/app/interceptors/app.request.interceptor.ts](https://github.com/eazybytes/spring-security/blob/main/section9/bank-app-ui/src/app/interceptors/app.request.interceptor.ts)

```java
import { Injectable } from '@angular/core';
import { HttpInterceptor,HttpRequest,HttpHandler,HttpErrorResponse, HttpHeaders } from '@angular/common/http';
import {Router} from '@angular/router';
import {tap} from 'rxjs/operators';
import { User } from 'src/app/model/user.model';

@Injectable()
export class XhrInterceptor implements HttpInterceptor {

  user = new User();
  constructor(private router: Router) {}

  intercept(req: HttpRequest<any>, next: HttpHandler) {
    let httpHeaders = new HttpHeaders();
    this.user = JSON.parse(sessionStorage.getItem('userdetails'));
    if(this.user && this.user.password && this.user.email){
      httpHeaders = httpHeaders.append('Authorization', 'Basic ' + btoa(this.user.email + ':' + this.user.password));
    }else{
      let authorization = sessionStorage.getItem('Authorization');
      if(authorization){
        httpHeaders = httpHeaders.append('Authorization', authorization);  
      }
    }
    
    httpHeaders = httpHeaders.append('X-Requested-With', 'XMLHttpRequest');
    const xhr = req.clone({
      headers: httpHeaders
    });
  return next.handle(xhr).pipe(tap(() => {},
      (err: any) => {
        if (err instanceof HttpErrorResponse) {
          if (err.status !== 401) {
            return;
          }
          this.router.navigate(['dashboard']);
        }
      }));
  }
}  
```

## Validating the JWT changes made by running the applications

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20127.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20128.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20129.png)

## Validating the JWT token expiration scenario

change to 30000 ~ 30s to test

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20130.png)

# Method Level Security

## Introduction to method level security in Spring Security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20131.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20132.png)

## Details about method invocation authorization in method level security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20133.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20134.png)

transaction will not rollback

## Implementing method level security using preauthorize and postauthorize

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20135.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20136.png)

```java
@Configuration
@EnableGlobalMethodSecurity(prePostEnabled = true,securedEnabled = true,  jsr250Enabled = true)
public class ProjectSecurityConfig extends WebSecurityConfigurerAdapter {

}).and().csrf().disable()
				.addFilterBefore(new RequestValidationBeforeFilter(), BasicAuthenticationFilter.class)
				.addFilterAfter(new AuthoritiesLoggingAfterFilter(), BasicAuthenticationFilter.class)
				.addFilterBefore(new JWTTokenValidatorFilter(), BasicAuthenticationFilter.class)
				.addFilterAfter(new JWTTokenGeneratorFilter(), BasicAuthenticationFilter.class)
				.addFilterAt(new AuthoritiesLoggingAtFilter(), BasicAuthenticationFilter.class)
				.authorizeRequests()
				.antMatchers("/myAccount").hasRole("USER")
				.antMatchers("/myBalance").hasAnyRole("USER","ADMIN")
				.antMatchers("/myLoans").authenticated() // add 
				.antMatchers("/myCards").hasAnyRole("USER","ADMIN")
				.antMatchers("/user").authenticated()
				.antMatchers("/notices").permitAll()
				.antMatchers("/contact").permitAll().and().httpBasic();
```

```java
package com.eazybytes.repository;

import java.util.List;

import org.springframework.data.repository.CrudRepository;
import org.springframework.stereotype.Repository;
import org.springframework.security.access.prepost.PreAuthorize;

import com.eazybytes.model.Loans;

@Repository
public interface LoanRepository extends CrudRepository<Loans, Long> {

	@PreAuthorize("hasRole('ROOT')")	
	List<Loans> findByCustomerIdOrderByStartDtDesc(int customerId);

} 
```

```java
package com.eazybytes.controller;

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.security.access.prepost.PostAuthorize;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RestController;

import com.eazybytes.model.Customer;
import com.eazybytes.model.Loans;
import com.eazybytes.repository.LoanRepository;

@RestController
public class LoansController {
	
	@Autowired
	private LoanRepository loanRepository;
	
	@PostMapping("/myLoans")
	@PostAuthorize("hasRole('ROOT')")
	public List<Loans> getLoanDetails(@RequestBody Customer customer) {
		List<Loans> loans = loanRepository.findByCustomerIdOrderByStartDtDesc(customer.getId());
		if (loans != null ) {
			return loans;
		}else {
			return null;
		}
	}

} 
```

## Details about filtering authorization in method level security

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20137.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20138.png)

## Implementing method level security using prefilter and postfilter

```java
package com.eazybytes.controller;

import java.sql.Date;
import java.util.Random;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.security.access.prepost.PostFilter;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RestController;

import com.eazybytes.model.Contact;
import com.eazybytes.repository.ContactRepository;

@RestController
public class ContactController {

	@Autowired
	private ContactRepository contactRepository;
	
	@PostMapping("/contact")
	//@PreFilter("filterObject.contactName == 'Test'")
	@PostFilter("filterObject.contactName == 'Test'")
	public Contact saveContactInquiryDetails(@RequestBody Contact contact) {
		contact.setContactId(getServiceReqNumber());
		contact.setCreateDt(new Date(System.currentTimeMillis()));
		return contactRepository.save(contact);
	}

	public String getServiceReqNumber() {
	    Random random = new Random();
	    int ranNum = random.nextInt(999999999 - 9999) + 9999;
	    return "SR"+ranNum;
	}
} 
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20139.png)

Post can execute logic in the background, no rollback

## Summary of the section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20140.png)

# Deep dive of OAUTH2

## Problems that OAUTH2 framework trying to solve

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20141.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20142.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20143.png)

## Introduction to OAUTH2

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20144.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20145.png)

## Different Components involved in OAUTH2 flow

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20146.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20147.png)

## Authorization code grant type flow in OAUTH2

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20148.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20149.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20150.png)

Like stackoverflow  

## Implicit grant type flow in OAUTH2

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20151.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20152.png)

## Resource owner credentials grant type flow in OAUTH2

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20153.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20154.png)

## Client credentials grant type flow in OAUTH2

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20155.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20156.png)

## Refresh token grant type flow in OAUTH2

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20157.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20158.png)

## How resource server validates the tokens issued by Auth server

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20159.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20160.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20161.png)

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20162.png)

# Implementing OAUTH2 using spring security

[https://www.baeldung.com/spring-security-5-oauth2-login](https://www.baeldung.com/spring-security-5-oauth2-login)

## Registering the client details with the GitHub to use it's OAUTH2 Auth server

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20163.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20164.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20165.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20166.png)

scroll down and click generate again

 

## Building a sample spring application that uses GitHub Auth server during OAUTH2

```java
<dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-oauth2-client</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-security</artifactId>
        </dependency>
```

[https://github.com/eazybytes/spring-security/blob/main/section_12/SpringSecOAUTHGitHub/src/main/java/com/springsec/oauth/controllers/SecureController.java](https://github.com/eazybytes/spring-security/blob/main/section_12/SpringSecOAUTHGitHub/src/main/java/com/springsec/oauth/controllers/SecureController.java)

```java
package com.springsec.oauth.controllers;

import org.springframework.security.oauth2.client.authentication.OAuth2AuthenticationToken;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class SecureController {

    @GetMapping("/")
    public String main(OAuth2AuthenticationToken token) {
        System.out.println(token.getPrincipal());
        return "secure.html";
    }
}
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20167.png)

[https://github.com/eazybytes/spring-security/blob/main/section_12/SpringSecOAUTHGitHub/src/main/java/com/springsec/oauth/config/SpringSecOAUTHGitHubConfig.java](https://github.com/eazybytes/spring-security/blob/main/section_12/SpringSecOAUTHGitHub/src/main/java/com/springsec/oauth/config/SpringSecOAUTHGitHubConfig.java)

```java
package com.springsec.oauth.config;

import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;

@Configuration
public class SpringSecOAUTHGitHubConfig extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
		http.authorizeRequests().anyRequest().authenticated().and().oauth2Login();
	}

	
	 * private ClientRegistration clientRegistration() { return
	 * CommonOAuth2Provider.GITHUB.getBuilder("github").clientId(
	 * "e482d40474aaaec77980")
	 * .clientSecret("dcd7d4f3b2fabeaf8a8646b0d1d653a4378170e9").build(); }
	 *

	
	/*
	 * private ClientRegistration clientRegistration() { ClientRegistration cr =
	 * ClientRegistration.withRegistrationId("github").clientId(
	 * "3c9be97074f067e78e75")
	 * .clientSecret("ab313f7ade3d79e06c192ca80cf152c43cb5d916").scope(new String[]
	 * { "read:user" })
	 * .authorizationUri("https://github.com/login/oauth/authorize")
	 * .tokenUri("https://github.com/login/oauth/access_token").userInfoUri(
	 * "https://api.github.com/user")
	 * .userNameAttributeName("id").clientName("GitHub")
	 * .authorizationGrantType(AuthorizationGrantType.AUTHORIZATION_CODE)
	 * .redirectUriTemplate("{baseUrl}/{action}/oauth2/code/{registrationId}").build
	 * (); return cr; }
	 */
	 

	 * @Bean public ClientRegistrationRepository clientRepository() {
	 * ClientRegistration clientReg = clientRegistration(); return new
	 * InMemoryClientRegistrationRepository(clientReg); }
	

}
```

 do not use the 2nd method since there are a lot of configurations, it's useful when we build auth server in your organization

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20168.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20169.png)

```java
spring.security.oauth2.client.registration.github.client-id=e482d40474aaaec77980
spring.security.oauth2.client.registration.github.client-secret=dcd7d4f3b2fabeaf8a8646b0d1d653a4378170e9

server.port=8080
```

## Running and verifying the sample application using GitHub OAUTH2

localhost:8080

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20170.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20171.png)

# 13 - Implementing OAUTH2 style login inside EazyBank using KeyCloak

## 1 - Introduction to OAUTH2 flow inside EazyBank web App

Preview

08:11

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20172.png)

06:28

## Introduction to OpenID Connect

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20173.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20174.png)

## Introduction to KeyCloak Auth Server

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20175.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20176.png)

## Installation of KeyCloak server & setup admin account

extract file

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20177.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20178.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20179.png)

after login

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20180.png)

## Setup a Realm inside KeyCloak Server for EazyBank App

realm is dedicated for business use cases

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20181.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20182.png)

07:01

## Creating Client Credentials inside KeyCloak for API-API secured invocations

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20183.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20184.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20185.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20186.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20187.png)

save

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20188.png)

15:00

## Setup EazyBank Resource Server

[https://github.com/eazybytes/spring-security/blob/main/section_13/resourceserver/pom.xml](https://github.com/eazybytes/spring-security/blob/main/section_13/resourceserver/pom.xml)

```java
<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-oauth2-resource-server</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
			<scope>runtime</scope>
			<optional>true</optional>
		</dependency>
		<dependency>
			<groupId>com.h2database</groupId>
			<artifactId>h2</artifactId>
			<scope>runtime</scope>
		</dependency>
```

[https://github.com/eazybytes/spring-security/blob/main/section_13/resourceserver/src/main/java/com/eazybytes/resourceserver/ResourceserverApplication.java](https://github.com/eazybytes/spring-security/blob/main/section_13/resourceserver/src/main/java/com/eazybytes/resourceserver/ResourceserverApplication.java)

```java
package com.eazybytes.resourceserver;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.boot.autoconfigure.domain.EntityScan;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.ComponentScans;
import org.springframework.data.jpa.repository.config.EnableJpaRepositories;

@SpringBootApplication
@ComponentScans({ @ComponentScan("com.eazybytes.controller"), @ComponentScan("com.eazybytes.config")})
@EnableJpaRepositories("com.eazybytes.repository") // interact with db
@EntityScan("com.eazybytes.model")
public class ResourceserverApplication {

	public static void main(String[] args) {
		SpringApplication.run(ResourceserverApplication.class, args);
	}

}
```

[https://github.com/eazybytes/spring-security/blob/main/section_13/resourceserver/src/main/java/com/eazybytes/config/ProjectSecurityConfig.java](https://github.com/eazybytes/spring-security/blob/main/section_13/resourceserver/src/main/java/com/eazybytes/config/ProjectSecurityConfig.java)

```java
package com.eazybytes.config;

import java.util.Collections;

import javax.servlet.http.HttpServletRequest;

import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;
import org.springframework.security.oauth2.server.resource.authentication.JwtAuthenticationConverter;
import org.springframework.web.cors.CorsConfiguration;
import org.springframework.web.cors.CorsConfigurationSource;

@Configuration
public class ProjectSecurityConfig extends WebSecurityConfigurerAdapter {

	/**
	 * /myAccount - Secured /myBalance - Secured /myLoans - Secured /myCards -
	 * Secured /notices - Not Secured /contact - Not Secured
	 */
	@Override
	protected void configure(HttpSecurity http) throws Exception {

		JwtAuthenticationConverter jwtAuthenticationConverter = new JwtAuthenticationConverter();
		jwtAuthenticationConverter.setJwtGrantedAuthoritiesConverter(new KeycloakRoleConverter());

		http.cors().configurationSource(new CorsConfigurationSource() {
			@Override public CorsConfiguration getCorsConfiguration(HttpServletRequest
			request) { CorsConfiguration config = new CorsConfiguration();
			config.setAllowedOrigins(Collections.singletonList("http://localhost:4200"));
			config.setAllowedMethods(Collections.singletonList("*"));
			config.setAllowCredentials(true);
			config.setAllowedHeaders(Collections.singletonList("*"));
			config.setMaxAge(3600L); return config;
			}
		}).and()
			.authorizeRequests()
			.antMatchers("/myAccount").hasAnyRole("USER")
			.antMatchers("/myBalance").hasAnyRole("ADMIN")
			.antMatchers("/myLoans").authenticated()
			.antMatchers("/myCards").hasAnyRole("USER", "ADMIN")
			.antMatchers("/notices").permitAll()
			.antMatchers("/contact").permitAll()
			.and().csrf().disable()
			.oauth2ResourceServer().jwt().jwtAuthenticationConverter(jwtAuthenticationConverter);
		
		/**
		 * This configuration is needed to view the /h2-console with out any issues.
		 * Since H2 Console uses frames to display the UI, we need to allow the frames.
		 * Otherwise since by default Spring Security consider X-Frame-Options: DENY
		 * to avoid Clickjacking attacks, the /h2-console will not work properly.
		 * More details can be found at 
		 * https://docs.spring.io/spring-security/site/docs/5.0.x/reference/html/headers.html#headers-frame-options
		 */
		http.headers().frameOptions().sameOrigin();

	}

}
```

KeycloakRoleConverter 

```java
package com.eazybytes.config;

import java.util.ArrayList;
import java.util.Collection;
import java.util.List;
import java.util.Map;
import java.util.stream.Collectors;

import org.springframework.core.convert.converter.Converter;
import org.springframework.security.core.GrantedAuthority;
import org.springframework.security.core.authority.SimpleGrantedAuthority;
import org.springframework.security.oauth2.jwt.Jwt;

public class KeycloakRoleConverter implements Converter<Jwt, Collection<GrantedAuthority>> {

	@Override
	public Collection<GrantedAuthority> convert(Jwt jwt) {
        Map<String, Object> realmAccess = (Map<String, Object>) jwt.getClaims().get("realm_access");

        if (realmAccess == null || realmAccess.isEmpty()) {
            return new ArrayList<>();
        }

        Collection<GrantedAuthority> returnValue = ((List<String>) realmAccess.get("roles"))
                .stream().map(roleName -> "ROLE_" + roleName)  
                .map(SimpleGrantedAuthority::new)
                .collect(Collectors.toList());
 
        return returnValue;
	}

}
```

<aside>
💡 must starts with ROLE_ to let spring understand role os the user

</aside>

```java
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.h2.console.enabled=true
server.port=8081
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update

spring.security.oauth2.resourceserver.jwt.jwk-set-uri = http://localhost:8080/auth/realms/eazybankdev/protocol/openid-connect/certs
```

sql

```java
DROP TABLE IF EXISTS accounts;
DROP TABLE IF EXISTS account_transactions;
DROP TABLE IF EXISTS loans;
DROP TABLE IF EXISTS cards;
DROP TABLE IF EXISTS notice_details;
DROP TABLE IF EXISTS contact_messages;

CREATE TABLE `accounts` (
   `account_number` int NOT NULL,
   `email` varchar(100) NOT NULL,
  `account_type` varchar(100) NOT NULL,
  `branch_address` varchar(200) NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`account_number`)
);

INSERT INTO `accounts` (`account_number`,`email`, `account_type`, `branch_address`, `create_dt`)
 VALUES (186576453,'accounts@eazybytes.com', 'Savings', '123 Main Street, New York', CURDATE());
 
CREATE TABLE `account_transactions` (
  `transaction_id` varchar(200) NOT NULL,
  `account_number` int NOT NULL,
  `email` varchar(100) NOT NULL,
  `transaction_dt` date NOT NULL,
  `transaction_summary` varchar(200) NOT NULL,
  `transaction_type` varchar(100) NOT NULL,
  `transaction_amt` int NOT NULL,
  `closing_balance` int NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`transaction_id`)
);

 
INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `email`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453, 'accounts@eazybytes.com', CURDATE()-7, 'Coffee Shop', 'Withdrawal', 30,34500,CURDATE()-7);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `email`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453, 'accounts@eazybytes.com', CURDATE()-6, 'Uber', 'Withdrawal', 100,34400,CURDATE()-6);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `email`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453, 'accounts@eazybytes.com', CURDATE()-5, 'Self Deposit', 'Deposit', 500,34900,CURDATE()-5);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `email`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453, 'accounts@eazybytes.com', CURDATE()-4, 'Ebay', 'Withdrawal', 600,34300,CURDATE()-4);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `email`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453, 'accounts@eazybytes.com', CURDATE()-2, 'OnlineTransfer', 'Deposit', 700,35000,CURDATE()-2);

INSERT INTO `account_transactions` (`transaction_id`, `account_number`, `email`, `transaction_dt`, `transaction_summary`, `transaction_type`,`transaction_amt`, 
`closing_balance`, `create_dt`)  VALUES (UUID(), 186576453, 'accounts@eazybytes.com', CURDATE()-1, 'Amazon.com', 'Withdrawal', 100,34900,CURDATE()-1);

CREATE TABLE `loans` (
  `loan_number` int NOT NULL AUTO_INCREMENT,
   `email` varchar(100) NOT NULL,
  `start_dt` date NOT NULL,
  `loan_type` varchar(100) NOT NULL,
  `total_loan` int NOT NULL,
  `amount_paid` int NOT NULL,
  `outstanding_amount` int NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`loan_number`)
);

INSERT INTO `loans` ( `email`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 'accounts@eazybytes.com', '2020-10-13', 'Home', 200000, 50000, 150000, '2020-10-13');
 
INSERT INTO `loans` ( `email`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 'accounts@eazybytes.com', '2020-06-06', 'Vehicle', 40000, 10000, 30000, '2020-06-06');
 
INSERT INTO `loans` ( `email`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 'accounts@eazybytes.com', '2018-02-14', 'Home', 50000, 10000, 40000, '2018-02-14');

INSERT INTO `loans` ( `email`, `start_dt`, `loan_type`, `total_loan`, `amount_paid`, `outstanding_amount`, `create_dt`)
 VALUES ( 'accounts@eazybytes.com', '2018-02-14', 'Personal', 10000, 3500, 6500, '2018-02-14');

CREATE TABLE `cards` (
  `card_id` int NOT NULL AUTO_INCREMENT,
  `card_number` varchar(100) NOT NULL,
   `email` varchar(100) NOT NULL,
  `card_type` varchar(100) NOT NULL,
  `total_limit` int NOT NULL,
  `amount_used` int NOT NULL,
  `available_amount` int NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`card_id`)
);

INSERT INTO `cards` (`card_number`, `email`, `card_type`, `total_limit`, `amount_used`, `available_amount`, `create_dt`)
 VALUES ('4565XXXX4656', 'accounts@eazybytes.com', 'Credit', 10000, 500, 9500, CURDATE());

INSERT INTO `cards` (`card_number`, `email`, `card_type`, `total_limit`, `amount_used`, `available_amount`, `create_dt`)
 VALUES ('3455XXXX8673', 'accounts@eazybytes.com', 'Credit', 7500, 600, 6900, CURDATE());
 
INSERT INTO `cards` (`card_number`, `email`, `card_type`, `total_limit`, `amount_used`, `available_amount`, `create_dt`)
 VALUES ('2359XXXX9346', 'accounts@eazybytes.com', 'Credit', 20000, 4000, 16000, CURDATE());
 
CREATE TABLE `notice_details` (
  `notice_id` int NOT NULL AUTO_INCREMENT,
  `notice_summary` varchar(200) NOT NULL,
  `notice_details` varchar(500) NOT NULL,
  `notic_beg_dt` date NOT NULL,
  `notic_end_dt` date DEFAULT NULL,
  `create_dt` date DEFAULT NULL,
  `update_dt` date DEFAULT NULL,
  PRIMARY KEY (`notice_id`)
);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Home Loan Interest rates reduced', 'Home loan interest rates are reduced as per the goverment guidelines. The updated rates will be effective immediately', 
'2021-08-20', '2021-08-28', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Net Banking Offers', 'Customers who will opt for Internet banking while opening a saving account will get a $50 amazon voucher', 
'2021-08-20', '2021-08-28', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Mobile App Downtime', 'The mobile application of the EazyBank will be down from 2AM-5AM on 12/05/2020 due to maintenance activities', 
'2021-08-20', '2021-08-28', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('E Auction notice', 'There will be a e-auction on 12/08/2020 on the Bank website for all the stubborn arrears.Interested parties can participate in the e-auction', 
'2021-08-20', '2021-08-28', CURDATE(), null);
   
INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('Launch of Millennia Cards', 'Millennia Credit Cards are launched for the premium customers of EazyBank. With these cards, you will get 5% cashback for each purchase', 
'2021-08-20', '2021-08-28', CURDATE(), null);

INSERT INTO `notice_details` ( `notice_summary`, `notice_details`, `notic_beg_dt`, `notic_end_dt`, `create_dt`, `update_dt`)
VALUES ('COVID-19 Insurance', 'EazyBank launched an insurance policy which will cover COVID-19 expenses. Please reach out to the branch for more details', 
'2021-08-20', '2021-08-28', CURDATE(), null);

CREATE TABLE `contact_messages` (
  `contact_id` varchar(50) NOT NULL,
  `contact_name` varchar(50) NOT NULL,
  `contact_email` varchar(100) NOT NULL,
  `subject` varchar(500) NOT NULL,
  `message` varchar(2000) NOT NULL,
  `create_dt` date DEFAULT NULL,
  PRIMARY KEY (`contact_id`)
);
```

03:55

## Getting Access token from KeyCloak using client credentials grant type

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20189.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20190.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20191.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20192.png)

## Passing Access token to Resource server for response through Postman

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20193.png)

send ⇒ since don't  have role USER

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20194.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20195.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20196.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20197.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20198.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20199.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20200.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20201.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20202.png)

 base on data check Converter

copy id token from token api

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20203.png)

## Understanding Authorization code grant type for EazyBank App

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20204.png)

04:51

## Creating Client and User details inside KeyCloak for Auth code grant flow

Create

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20205.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20206.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20207.png)

⇒ important since hacker can attack

save

Create user

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20208.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20209.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20210.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20211.png)

07:37

## Testing Authorization code grant type using Postman App

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20212.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20213.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20214.png)

but we use user detail accounts 12345

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20215.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20216.png)

copy code

call if error copy link paste again to get code

 

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20217.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20218.png)

copy access token

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20219.png)

 

05:35

## Deep dive on Authorization code grant type with PKCE

03:13

## Creating public facing client details inside KeyCloak server

Create client

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20220.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20221.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20222.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20223.png)

save

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20224.png)

15:54

## Understanding PKCE Authorization code grant type inside Angular UI App

[keycloak-angular](https://www.npmjs.com/package/keycloak-angular)

`npm install keycloak-angular keycloak-js`

[https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/app.module.ts](https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/app.module.ts)

```java
import { BrowserModule } from '@angular/platform-browser';
import { APP_INITIALIZER,NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpClientModule, HttpClientXsrfModule } from '@angular/common/http';
import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { HeaderComponent } from './components/header/header.component';
import { ContactComponent } from './components/contact/contact.component';
import { LoginComponent } from './components/login/login.component';
import { DashboardComponent } from './components/dashboard/dashboard.component';
import { NoticesComponent } from './components/notices/notices.component';
import { AccountComponent } from './components/account/account.component';
import { BalanceComponent } from './components/balance/balance.component';
import { LoansComponent } from './components/loans/loans.component';
import { CardsComponent } from './components/cards/cards.component';
import { KeycloakAngularModule, KeycloakService } from 'keycloak-angular';

function initializeKeycloak(keycloak: KeycloakService) {
  return () =>
    keycloak.init({
      config: {
        url: 'http://localhost:8080/auth',
        realm: 'eazybankdev',
        clientId: 'eazypublicclient',
      },
      initOptions: {
        pkceMethod: 'S256',
        redirectUri: 'http://localhost:4200/dashboard'
      },loadUserProfileAtStartUp: false
    });
}

@NgModule({
  declarations: [
    AppComponent,
    HeaderComponent,
    ContactComponent,
    LoginComponent,
    DashboardComponent,
    NoticesComponent,
    AccountComponent,
    BalanceComponent,
    LoansComponent,
    CardsComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    FormsModule,
    KeycloakAngularModule,
    HttpClientModule,
    HttpClientXsrfModule.withOptions({
      cookieName: 'XSRF-TOKEN',
      headerName: 'X-XSRF-TOKEN',
    }),
  ],
  providers: [
    {
      provide: APP_INITIALIZER,
      useFactory: initializeKeycloak,
      multi: true,
      deps: [KeycloakService],
    }
  ],
  bootstrap: [AppComponent]
})
export class AppModule {

}
```

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20225.png)

[https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/components/header/header.component.html](https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/components/header/header.component.html)

```java
<div data-navigation="container" class="i-top-header">
  <div class="wrapper top-section">
    <div class="hleft"><a class="logo selfLogo" routerLink="/dashboard"><img alt="logo"
          src="../assets/images/logo.png"></a></div>
    <div class="mnav_hb hide">
      <div class="hamburger"><span class="line"></span><span class="line"></span><span class="line"></span></div>
    </div>
    <nav class="hright dnav">
      <ul>
        <li *ngIf="user.authStatus!='AUTH'" routerLinkActive="active"><a routerLink="/home">Home</a></li>
        <li *ngIf="user.authStatus!='AUTH'" routerLinkActive="active"><a (click)="login()">Login</a></li>
        <li *ngIf="user.authStatus!='AUTH'" routerLinkActive="active"><a routerLink="/contact">Contact US</a></li>
        <li *ngIf="user.authStatus!='AUTH'" routerLinkActive="active"><a routerLink="/notices">Notices</a></li>
        <li *ngIf="user.authStatus=='AUTH'" routerLinkActive="active"><a routerLink="/dashboard">Dashboard</a></li>
        <li *ngIf="user.authStatus=='AUTH'" routerLinkActive="active"><a (click)="logout()">Logout</a></li>

      </ul>
    </nav>
  </div>
</div>
<router-outlet></router-outlet> 
```

```java
import { Component, OnInit } from '@angular/core';
import { User } from 'src/app/model/user.model';
import { KeycloakService } from 'keycloak-angular';
import { KeycloakProfile } from 'keycloak-js';

@Component({
  selector: 'app-header',
  templateUrl: './header.component.html',
  styleUrls: ['./header.component.css']
})
export class HeaderComponent implements OnInit {
  
  user = new User();
  public isLoggedIn = false;
  public userProfile: KeycloakProfile | null = null;

  constructor(private readonly keycloak: KeycloakService) { }

  public async ngOnInit() {
    this.isLoggedIn = await this.keycloak.isLoggedIn();

    if (this.isLoggedIn) {
      this.userProfile = await this.keycloak.loadUserProfile();
      this.user.authStatus = 'AUTH';
      this.user.name = this.userProfile.firstName;
      window.sessionStorage.setItem("userdetails",JSON.stringify(this.user));
      
    }
  }

  public login() {
    this.keycloak.login();
  }

  public logout() {
    this.keycloak.logout();
  }

}
```

[https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/app-routing.module.ts](https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/app-routing.module.ts)

```java
import { NgModule } from '@angular/core';
import { Routes, RouterModule } from '@angular/router';
import { ContactComponent } from './components/contact/contact.component';
import { LoginComponent } from './components/login/login.component';
import { DashboardComponent } from './components/dashboard/dashboard.component';
import { AccountComponent } from '../app/components/account/account.component';
import { BalanceComponent } from '../app/components/balance/balance.component';
import { NoticesComponent } from './components/notices/notices.component';
import { LoansComponent } from './components/loans/loans.component';
import { CardsComponent } from './components/cards/cards.component';
import { AuthKeyClockGuard } from './routeguards/auth.route';

const routes: Routes = [
  { path: '', redirectTo: '/home', pathMatch: 'full'},
  { path: 'home', component: LoginComponent},
  { path: 'login', component: LoginComponent},
  { path: 'contact', component: ContactComponent},
  { path: 'notices', component: NoticesComponent},
  { path: 'dashboard', component: DashboardComponent, canActivate: [AuthKeyClockGuard],data: {
    roles: ['USER','ADMIN']
  }},
  { path: 'myAccount', component: AccountComponent, canActivate: [AuthKeyClockGuard],data: {
    roles: ['USER']
  }},
  { path: 'myBalance', component: BalanceComponent, canActivate: [AuthKeyClockGuard],data: {
    roles: ['ADMIN']
  }},
  { path: 'myLoans', component: LoansComponent, canActivate: [AuthKeyClockGuard],data: {
    roles: ['USER','ADMIN']
  }},
  { path: 'myCards', component: CardsComponent, canActivate: [AuthKeyClockGuard],data: {
    roles: ['USER','ADMIN']
  }}
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

[https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/routeguards/auth.route.ts](https://github.com/eazybytes/spring-security/blob/main/section_13/client-app-ui/src/app/routeguards/auth.route.ts)

```java
import { Injectable } from '@angular/core';
import {
  ActivatedRouteSnapshot,
  Router,
  RouterStateSnapshot,
} from '@angular/router';
import { KeycloakAuthGuard, KeycloakService } from 'keycloak-angular';
import { User } from '../model/user.model';
import { KeycloakProfile } from 'keycloak-js';

@Injectable({
  providedIn: 'root',
})
export class AuthKeyClockGuard extends KeycloakAuthGuard {
  user = new User();
  public userProfile: KeycloakProfile | null = null;
  constructor(
    protected readonly router: Router,
    protected readonly keycloak: KeycloakService
  ) {
    super(router, keycloak);
  }

  public async isAccessAllowed(
    route: ActivatedRouteSnapshot,
    state: RouterStateSnapshot
  ) {
    // Force the user to log in if currently unauthenticated.
    if (!this.authenticated) {
      await this.keycloak.login({
        redirectUri: window.location.origin + state.url,
      });
    }else{
        this.userProfile = await this.keycloak.loadUserProfile();
        this.user.authStatus = 'AUTH';
        this.user.name = this.userProfile.firstName;
        this.user.email = this.userProfile.email;
        window.sessionStorage.setItem("userdetails",JSON.stringify(this.user));
    }

    // Get the roles required from the route.
    const requiredRoles = route.data.roles;

    // Allow the user to to proceed if no additional roles are required to access the route.
    if (!(requiredRoles instanceof Array) || requiredRoles.length === 0) {
      return true;
    }

    // Allow the user to proceed if all the required roles are present.
    return requiredRoles.some((role) => this.roles.includes(role));
  }
} 
```

Click on login on the header

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20226.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20227.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20228.png)

save

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20229.png)

 log out

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20230.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20231.png)

08:37

## Important features of KeyCloak

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20232.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20233.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20234.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20235.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20236.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20237.png)

Khi create user mới sẽ báo lỗi

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20238.png)

Preview 06:41

## Social Login integration with the help of KeyCloak Server

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20239.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20240.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20241.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20242.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20243.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20244.png)

save

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20245.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20246.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20247.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20248.png)

save

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20249.png)

click to login can see the content

 

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20250.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20251.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20252.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20253.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20254.png)

## Summary of the Section

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20255.png)

![Untitled](Spring%20Security%20Zero%20to%20Master%20along%20with%20JWT,OAUT/Untitled%20256.png)