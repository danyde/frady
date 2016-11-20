# Tips for Spring boot used fpr spring batch (JavaConfig)  and Spring integration 
# # 1. Spring boot failing to start because no database is provided

Error starting ApplicationContext. To display the auto-configuration report re-run your application with 'debug' enabled.
2016-11-19 12:29:04.581 ERROR 9464 --- [           main] o.s.b.d.LoggingFailureAnalysisReporter   : 

***************************
APPLICATION FAILED TO START
***************************

Description:

Cannot determine embedded database driver class for database type NONE


1. In pom.xml:  add yaur database dependencies. (HSQL db for the testing purpose can resolve yaur issue)  
2. Disable  the datasource auto-configation: If you prefer to configure yaur datasource add this line in yaur spring bootstrap class: 
                @EnableAutoConfiguration(exclude = {DataSourceAutoConfiguration.class, 
                                                    DataSourceTransactionManagerAutoConfiguration.class, 
                                                    HibernateJpaAutoConfiguration.class})




# # 2. Spring boot failing: NoUniqueBeanDefinitionException: No qualifying bean of type

- Missing configuration 
- @Primary keyword missing often


# # 3. No datasoucre found for Spring batch 
