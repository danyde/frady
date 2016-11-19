# Tips for Spring boot  
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




