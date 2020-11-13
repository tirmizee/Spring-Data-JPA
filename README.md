# Spring-Data-JPA

##### Initailize Data 
 
    spring.jpa.hibernate.ddl-auto=create

Hibernate looks for import.sql in class path for data initialization if ddl-auto value create or create-drop.

####  Initialize using schema.sql and data.sql

    spring.datasource.initialization-mode=always

Both schema and data related sql statements can also be included in single sql file, but by naming convention it’s better approach to maintain all schema related scripts in scema.sql and all the data manipulation related statements in data.sql.

####  Loading Scripts for multiple database vendors

    spring.datasource.initialization-mode=always
    spring.datasource.platform=mysql

It’s quite common having multiple databases to work with in different environments (example H2 in DEV and MySql in production). Spring Boot processes the schema-${platform}.sql and data-${platform}.sql files (if present process, ignores if not presents), where platform is the value of spring.datasource.platform. This allows you to switch to database-specific scripts if necessary.

For example if you have in class path schema-mysql.sql to intialize data in Mysql database and schema-h2.sql to initialize data in H2 database. Following is the configuration to work on Mysql database.

#### Scripts with custom names

    spring.datasource.initialization-mode=always
    spring.datasource.schema=classpath:schema-data-dump.sql

### Annotation

  @Convert

  @Converter
  
  @Temporal
  
  @ColumnDefault
  
  @Entity
  
  @DynamicUpdate
  
  @Table
  
  @UniqueConstraint
  
  @Id
  
  @SequenceGenerator
  
  @GeneratedValue
  
  @NaturalId
  
  @MappedSuperclass
  
  @EntityListeners
  
  @JoinColumn
  
### Class

  AttributeConverter
  
  ![image](https://user-images.githubusercontent.com/15135199/82486351-e7d7a580-9b06-11ea-884e-ad3af97bc681.png)

### Ref

Example of CascadeType.REFRESH in Hibernate

- https://www.connect2java.com/tutorials/hibernate/refresh-method-in-hibernate/
- https://javabydeveloper.com/spring-boot-loading-initial-data/

