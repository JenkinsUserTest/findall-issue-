
java.lang.IllegalStateException: Failed to load ApplicationContext for [MergedContextConfiguration@3efb863c testClass = com.cognizant.test.TestRideInfoRepository, locations = [], classes = [com.cognizant.main.RideProviderModuleApplication], contextInitializerClasses = [], activeProfiles = [], propertySourceDescriptors = [], propertySourceProperties = ["org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTestContextBootstrapper=true"], contextCustomizers = [[ImportsContextCustomizer@5527dbb0 key = [org.springframework.boot.autoconfigure.transaction.TransactionAutoConfiguration, org.springframework.boot.autoconfigure.data.jpa.JpaRepositoriesAutoConfiguration, org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManagerAutoConfiguration, org.springframework.boot.autoconfigure.cache.CacheAutoConfiguration, org.springframework.boot.autoconfigure.orm.jpa.HibernateJpaAutoConfiguration, org.springframework.boot.autoconfigure.sql.init.SqlInitializationAutoConfiguration, org.springframework.boot.test.autoconfigure.jdbc.TestDatabaseAutoConfiguration, org.springframework.boot.autoconfigure.flyway.FlywayAutoConfiguration, org.springframework.boot.autoconfigure.jdbc.DataSourceTransactionManagerAutoConfiguration, org.springframework.boot.autoconfigure.liquibase.LiquibaseAutoConfiguration, org.springframework.boot.autoconfigure.jdbc.JdbcClientAutoConfiguration, org.springframework.boot.autoconfigure.jdbc.DataSourceAutoConfiguration, org.springframework.boot.autoconfigure.jdbc.JdbcTemplateAutoConfiguration]], org.springframework.boot.test.context.filter.ExcludeFilterContextCustomizer@3403e2ac, org.springframework.boot.test.json.DuplicateJsonObjectContextCustomizerFactory$DuplicateJsonObjectContextCustomizer@327bcebd, org.springframework.boot.test.mock.mockito.MockitoContextCustomizer@0, org.springframework.boot.test.autoconfigure.OverrideAutoConfigurationContextCustomizerFactory$DisableAutoConfigurationContextCustomizer@1fa1cab1, org.springframework.boot.test.autoconfigure.actuate.observability.ObservabilityContextCustomizerFactory$DisableObservabilityContextCustomizer@1f, org.springframework.boot.test.autoconfigure.filter.TypeExcludeFiltersContextCustomizer@34be3d80, org.springframework.boot.test.autoconfigure.properties.PropertyMappingContextCustomizer@8ced4b8, org.springframework.boot.test.autoconfigure.web.servlet.WebDriverContextCustomizer@66c61024, org.springframework.boot.test.context.SpringBootTestAnnotation@7d51c9be], contextLoader = org.springframework.boot.test.context.SpringBootContextLoader, parent = null]
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:180)
	at org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:130)
	at org.springframework.test.context.support.DependencyInjectionTestExecutionListener.injectDependencies(DependencyInjectionTestExecutionListener.java:142)
	at org.springframework.test.context.support.DependencyInjectionTestExecutionListener.prepareTestInstance(DependencyInjectionTestExecutionListener.java:98)
	at org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:260)
	at org.springframework.test.context.junit.jupiter.SpringExtension.postProcessTestInstance(SpringExtension.java:163)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179)
	at java.base/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1625)
	at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509)
	at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499)
	at java.base/java.util.stream.StreamSpliterators$WrappingSpliterator.forEachRemaining(StreamSpliterators.java:310)
	at java.base/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:735)
	at java.base/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:734)
	at java.base/java.util.stream.ReferencePipeline$Head.forEach(ReferencePipeline.java:762)
	at java.base/java.util.Optional.orElseGet(Optional.java:364)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1511)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1511)
Caused by: org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'rideInfoRepository' defined in com.cognizant.repositories.RideInfoRepository defined in @EnableJpaRepositories declared on RideProviderModuleApplication: Could not create query for public abstract java.util.List com.cognizant.repositories.RideInfoRepository.findAllRideInfo(); Reason: Failed to create query for method public abstract java.util.List com.cognizant.repositories.RideInfoRepository.findAllRideInfo(); No property 'findAllRideInfo' found for type 'RideInfo'
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1773)
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:599)
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:521)
	at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:325)
	at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234)
	at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:323)
	at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:199)
	at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingletons(DefaultListableBeanFactory.java:969)
	at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:959)
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:624)
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:754)
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:456)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:334)
	at org.springframework.boot.test.context.SpringBootContextLoader.lambda$loadContext$3(SpringBootContextLoader.java:137)
	at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:58)
	at org.springframework.util.function.ThrowingSupplier.get(ThrowingSupplier.java:46)
	at org.springframework.boot.SpringApplication.withHook(SpringApplication.java:1454)
	at org.springframework.boot.test.context.SpringBootContextLoader$ContextLoaderHook.run(SpringBootContextLoader.java:552)
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:137)
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:108)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContextInternal(DefaultCacheAwareContextLoaderDelegate.java:225)
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:152)
	... 17 more
Caused by: org.springframework.data.repository.query.QueryCreationException: Could not create query for public abstract java.util.List com.cognizant.repositories.RideInfoRepository.findAllRideInfo(); Reason: Failed to create query for method public abstract java.util.List com.cognizant.repositories.RideInfoRepository.findAllRideInfo(); No property 'findAllRideInfo' found for type 'RideInfo'
	at org.springframework.data.repository.query.QueryCreationException.create(QueryCreationException.java:101)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.lookupQuery(QueryExecutorMethodInterceptor.java:115)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.mapMethodsToQuery(QueryExecutorMethodInterceptor.java:99)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.lambda$new$0(QueryExecutorMethodInterceptor.java:88)
	at java.base/java.util.Optional.map(Optional.java:260)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.<init>(QueryExecutorMethodInterceptor.java:88)
	at org.springframework.data.repository.core.support.RepositoryFactorySupport.getRepository(RepositoryFactorySupport.java:357)
	at org.springframework.data.repository.core.support.RepositoryFactoryBeanSupport.lambda$afterPropertiesSet$5(RepositoryFactoryBeanSupport.java:279)
	at org.springframework.data.util.Lazy.getNullable(Lazy.java:135)
	at org.springframework.data.util.Lazy.get(Lazy.java:113)
	at org.springframework.data.repository.core.support.RepositoryFactoryBeanSupport.afterPropertiesSet(RepositoryFactoryBeanSupport.java:285)
	at org.springframework.data.jpa.repository.support.JpaRepositoryFactoryBean.afterPropertiesSet(JpaRepositoryFactoryBean.java:132)
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.invokeInitMethods(AbstractAutowireCapableBeanFactory.java:1820)
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1769)
	... 38 more
Caused by: java.lang.IllegalArgumentException: Failed to create query for method public abstract java.util.List com.cognizant.repositories.RideInfoRepository.findAllRideInfo(); No property 'findAllRideInfo' found for type 'RideInfo'
	at org.springframework.data.jpa.repository.query.PartTreeJpaQuery.<init>(PartTreeJpaQuery.java:106)
	at org.springframework.data.jpa.repository.query.JpaQueryLookupStrategy$CreateQueryLookupStrategy.resolveQuery(JpaQueryLookupStrategy.java:124)
	at org.springframework.data.jpa.repository.query.JpaQueryLookupStrategy$CreateIfNotFoundQueryLookupStrategy.resolveQuery(JpaQueryLookupStrategy.java:258)
	at org.springframework.data.jpa.repository.query.JpaQueryLookupStrategy$AbstractQueryLookupStrategy.resolveQuery(JpaQueryLookupStrategy.java:95)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.lookupQuery(QueryExecutorMethodInterceptor.java:111)
	... 50 more
Caused by: org.springframework.data.mapping.PropertyReferenceException: No property 'findAllRideInfo' found for type 'RideInfo'
	at org.springframework.data.mapping.PropertyPath.<init>(PropertyPath.java:90)
	at org.springframework.data.mapping.PropertyPath.create(PropertyPath.java:443)
	at org.springframework.data.mapping.PropertyPath.create(PropertyPath.java:419)
	at org.springframework.data.mapping.PropertyPath.lambda$from$0(PropertyPath.java:372)
	at java.base/java.util.concurrent.ConcurrentMap.computeIfAbsent(ConcurrentMap.java:330)
	at org.springframework.data.mapping.PropertyPath.from(PropertyPath.java:354)
	at org.springframework.data.mapping.PropertyPath.from(PropertyPath.java:332)
	at org.springframework.data.repository.query.parser.Part.<init>(Part.java:81)
	at org.springframework.data.repository.query.parser.PartTree$OrPart.lambda$new$0(PartTree.java:259)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179)
	at java.base/java.util.Spliterators$ArraySpliterator.forEachRemaining(Spliterators.java:992)
	at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509)
	at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499)
	at java.base/java.util.stream.ReduceOps$ReduceOp.evaluateSequential(ReduceOps.java:921)
	at java.base/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:234)
	at java.base/java.util.stream.ReferencePipeline.collect(ReferencePipeline.java:682)
	at org.springframework.data.repository.query.parser.PartTree$OrPart.<init>(PartTree.java:260)
	at org.springframework.data.repository.query.parser.PartTree$Predicate.lambda$new$0(PartTree.java:389)
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:197)
	at java.base/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:179)
	at java.base/java.util.Spliterators$ArraySpliterator.forEachRemaining(Spliterators.java:992)
	at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509)
	at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499)
	at java.base/java.util.stream.ReduceOps$ReduceOp.evaluateSequential(ReduceOps.java:921)
	at java.base/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:234)
	at java.base/java.util.stream.ReferencePipeline.collect(ReferencePipeline.java:682)
	at org.springframework.data.repository.query.parser.PartTree$Predicate.<init>(PartTree.java:390)
	at org.springframework.data.repository.query.parser.PartTree.<init>(PartTree.java:100)
	at org.springframework.data.jpa.repository.query.PartTreeJpaQuery.<init>(PartTreeJpaQuery.java:100)
	... 54 more
























If you're using a `CrudRepository` instead of a `JpaRepository`, the procedure is similar. Here's how you can adjust the test class:

```java
import java.util.List;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;

import static org.junit.jupiter.api.Assertions.*;

@DataJpaTest
public class TestRideInfoRepository {

    @Autowired
    private RideInfoRepository rideInfoRepository;

    @Test
    public void testFindAll() {
        Iterable<RideInfo> rideInfos = rideInfoRepository.findAll();
        assertNotNull(rideInfos);
        assertTrue(rideInfos.iterator().hasNext());
    }
}
```

In this version, `findAll()` method returns an `Iterable<RideInfo>`, so we adjust the test accordingly. We check if the iterable is not null and if it has at least one element.

Make sure that `RideInfoRepository` extends `CrudRepository<RideInfo, RideInfo.RideInfoVehicleRpId>`.

If the issue persists, please provide more details or the exact error message, and I'll assist you further.






I see, if you're not currently writing the service layer and are instead focusing on testing the repository directly, you can still work around the issue with `findAll()` by using alternative approaches in your test cases.

One approach is to retrieve entities individually using their composite keys. Since `findById()` method works fine with composite keys, you can loop through all possible composite keys and fetch each entity one by one. However, this approach may not be efficient, especially if you have a large number of entities.

Another approach is to use a custom query in your repository test cases to fetch all entities. You can define a custom query to select all entities directly from the database. Here's an example of how you can do it:

```java
@Test
public void testFindAll() {
    List<RideInfo> rideInfos = rideInfoRepository.findAllRideInfo();
    assertNotNull(rideInfos);
    assertFalse(rideInfos.isEmpty());
}
```

And in your repository interface:

```java
@Repository
public interface RideInfoRepository extends JpaRepository<RideInfo, RideInfo.RideInfoVehicleRpId> {

    @Query("SELECT ri FROM RideInfo ri")
    List<RideInfo> findAllRideInfo();
}
```

This approach allows you to fetch all entities using a custom query that directly selects all records from the corresponding table. Make sure to test this custom query to ensure it retrieves the expected results.

If you encounter any issues or need further assistance, feel free to ask!
