org.springframework.orm.jpa.JpaSystemException: Unable to locate constructor for embeddable 'com.cognizant.entities.RideInfo$RideInfoVehicleRpId'
	at org.springframework.orm.jpa.vendor.HibernateJpaDialect.convertHibernateAccessException(HibernateJpaDialect.java:341)
	at org.springframework.orm.jpa.vendor.HibernateJpaDialect.translateExceptionIfPossible(HibernateJpaDialect.java:241)
	at org.springframework.orm.jpa.AbstractEntityManagerFactoryBean.translateExceptionIfPossible(AbstractEntityManagerFactoryBean.java:550)
	at org.springframework.dao.support.ChainedPersistenceExceptionTranslator.translateExceptionIfPossible(ChainedPersistenceExceptionTranslator.java:61)
	at org.springframework.dao.support.DataAccessUtils.translateIfNecessary(DataAccessUtils.java:335)
	at org.springframework.dao.support.PersistenceExceptionTranslationInterceptor.invoke(PersistenceExceptionTranslationInterceptor.java:152)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184)
	at org.springframework.data.jpa.repository.support.CrudMethodMetadataPostProcessor$CrudMethodMetadataPopulatingMethodInterceptor.invoke(CrudMethodMetadataPostProcessor.java:164)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184)
	at org.springframework.aop.interceptor.ExposeInvocationInterceptor.invoke(ExposeInvocationInterceptor.java:97)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184)
	at org.springframework.aop.framework.JdkDynamicAopProxy.invoke(JdkDynamicAopProxy.java:220)
	at jdk.proxy2/jdk.proxy2.$Proxy120.findAll(Unknown Source)
	at com.cognizant.test.TestRideInfoRepository.testFindAllPositive(TestRideInfoRepository.java:75)
	at java.base/java.lang.reflect.Method.invoke(Method.java:568)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1511)
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1511)
Caused by: org.hibernate.InstantiationException: Unable to locate constructor for embeddable 'com.cognizant.entities.RideInfo$RideInfoVehicleRpId'
	at org.hibernate.metamodel.internal.EmbeddableInstantiatorPojoStandard.instantiate(EmbeddableInstantiatorPojoStandard.java:58)
	at org.hibernate.sql.results.graph.embeddable.AbstractEmbeddableInitializer.createCompositeInstance(AbstractEmbeddableInitializer.java:348)
	at org.hibernate.sql.results.graph.embeddable.AbstractEmbeddableInitializer.prepareCompositeInstance(AbstractEmbeddableInitializer.java:250)
	at org.hibernate.sql.results.graph.embeddable.AbstractEmbeddableInitializer.initializeInstance(AbstractEmbeddableInitializer.java:189)
	at org.hibernate.sql.results.graph.embeddable.internal.EmbeddableAssembler.assemble(EmbeddableAssembler.java:34)
	at org.hibernate.sql.results.graph.entity.AbstractEntityInitializer.initializeIdentifier(AbstractEntityInitializer.java:374)
	at org.hibernate.sql.results.graph.entity.AbstractEntityInitializer.resolveEntityKey(AbstractEntityInitializer.java:351)
	at org.hibernate.sql.results.graph.entity.AbstractEntityInitializer.resolveKey(AbstractEntityInitializer.java:293)
	at org.hibernate.sql.results.internal.InitializersList.resolveKeys(InitializersList.java:82)
	at org.hibernate.sql.results.internal.StandardRowReader.coordinateInitializers(StandardRowReader.java:107)
	at org.hibernate.sql.results.internal.StandardRowReader.readRow(StandardRowReader.java:86)
	at org.hibernate.sql.results.spi.ListResultsConsumer.consume(ListResultsConsumer.java:204)
	at org.hibernate.sql.results.spi.ListResultsConsumer.consume(ListResultsConsumer.java:33)
	at org.hibernate.sql.exec.internal.JdbcSelectExecutorStandardImpl.doExecuteQuery(JdbcSelectExecutorStandardImpl.java:209)
	at org.hibernate.sql.exec.internal.JdbcSelectExecutorStandardImpl.executeQuery(JdbcSelectExecutorStandardImpl.java:83)
	at org.hibernate.sql.exec.spi.JdbcSelectExecutor.list(JdbcSelectExecutor.java:76)
	at org.hibernate.sql.exec.spi.JdbcSelectExecutor.list(JdbcSelectExecutor.java:65)
	at org.hibernate.query.sqm.internal.ConcreteSqmSelectQueryPlan.lambda$new$2(ConcreteSqmSelectQueryPlan.java:137)
	at org.hibernate.query.sqm.internal.ConcreteSqmSelectQueryPlan.withCacheableSqmInterpretation(ConcreteSqmSelectQueryPlan.java:359)
	at org.hibernate.query.sqm.internal.ConcreteSqmSelectQueryPlan.performList(ConcreteSqmSelectQueryPlan.java:300)
	at org.hibernate.query.sqm.internal.QuerySqmImpl.doList(QuerySqmImpl.java:509)
	at org.hibernate.query.spi.AbstractSelectionQuery.list(AbstractSelectionQuery.java:427)
	at org.hibernate.query.Query.getResultList(Query.java:120)
	at org.springframework.data.jpa.repository.support.SimpleJpaRepository.findAll(SimpleJpaRepository.java:383)
	at org.springframework.data.jpa.repository.support.SimpleJpaRepository.findAll(SimpleJpaRepository.java:1)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.base/java.lang.reflect.Method.invoke(Method.java:568)
	at org.springframework.aop.support.AopUtils.invokeJoinpointUsingReflection(AopUtils.java:351)
	at org.springframework.data.repository.core.support.RepositoryMethodInvoker$RepositoryFragmentMethodInvoker.lambda$new$0(RepositoryMethodInvoker.java:277)
	at org.springframework.data.repository.core.support.RepositoryMethodInvoker.doInvoke(RepositoryMethodInvoker.java:170)
	at org.springframework.data.repository.core.support.RepositoryMethodInvoker.invoke(RepositoryMethodInvoker.java:158)
	at org.springframework.data.repository.core.support.RepositoryComposition$RepositoryFragments.invoke(RepositoryComposition.java:516)
	at org.springframework.data.repository.core.support.RepositoryComposition.invoke(RepositoryComposition.java:285)
	at org.springframework.data.repository.core.support.RepositoryFactorySupport$ImplementationMethodExecutionInterceptor.invoke(RepositoryFactorySupport.java:628)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.doInvoke(QueryExecutorMethodInterceptor.java:168)
	at org.springframework.data.repository.core.support.QueryExecutorMethodInterceptor.invoke(QueryExecutorMethodInterceptor.java:143)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184)
	at org.springframework.transaction.interceptor.TransactionInterceptor$1.proceedWithInvocation(TransactionInterceptor.java:123)
	at org.springframework.transaction.interceptor.TransactionAspectSupport.invokeWithinTransaction(TransactionAspectSupport.java:385)
	at org.springframework.transaction.interceptor.TransactionInterceptor.invoke(TransactionInterceptor.java:119)
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:184)
	at org.springframework.dao.support.PersistenceExceptionTranslationInterceptor.invoke(PersistenceExceptionTranslationInterceptor.java:137)
	... 11 more









package com.cognizant.entities;

import java.io.Serializable;
import java.util.Objects;

import jakarta.persistence.Column;
import jakarta.persistence.Embeddable;
import jakarta.persistence.EmbeddedId;
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.GenerationType;
import jakarta.persistence.Id;
import jakarta.persistence.IdClass;
import jakarta.persistence.JoinColumn;
import jakarta.persistence.ManyToOne;
import jakarta.persistence.Table;
import jakarta.validation.constraints.Min;
import jakarta.validation.constraints.NotEmpty;
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Size;
@Entity
@Table(name="Ride_Info" )
//@IdClass(RideInfoId.class)


public class RideInfo {


@Embeddable
public
class RideInfoVehicleRpId implements Serializable {
	String vechileNo;
	
	String Rp_Id;
	
	public RideInfoVehicleRpId() {
		System.out.println("--RideInfoVehicleRpId--");
	}

	public String getVechileNo() {
		return vechileNo;
	}

	public void setVechileNo(String vechileNo) {
		this.vechileNo = vechileNo;
	}

	public String getRp_Id() {
		return Rp_Id;
	}

	public void setRp_Id(String rp_Id) {
		Rp_Id = rp_Id;
	}

	@Override
	public String toString() {
		return "RideInfoVehicleRpId [vechileNo=" + vechileNo + ", Rp_Id=" + Rp_Id + "]";
	}
	
	
	
}

	
	/*
	@Id
	@jakarta.persistence.Column(name="Vechile_No")
	@NotNull
	private String vechileNo;

	@Id
	@jakarta.persistence.Column(name="rp_id")
	@NotNull
	private String rpId;
	*/
	@EmbeddedId RideInfo.RideInfoVehicleRpId rideInfoVehicleRpId;
	@jakarta.persistence.Column(name="Car_Type")
	@NotEmpty
	private String carType;
	
	
	
	public RideInfo.RideInfoVehicleRpId getRideInfoVehicleRpId() {
		return rideInfoVehicleRpId;
	}

	public void setRideInfoVehicleRpId(RideInfo.RideInfoVehicleRpId rideInfoVehicleRpId) {
		this.rideInfoVehicleRpId = rideInfoVehicleRpId;
	}

	public String getCarType() {
		return carType;
	}

	public void setCarType(String carType) {
		this.carType = carType;
	}

	public String getCarName() {
		return CarName;
	}

	public void setCarName(String carName) {
		CarName = carName;
	}

	public String getFuelType() {
		return fuelType;
	}

	public void setFuelType(String fuelType) {
		this.fuelType = fuelType;
	}

	public int getNoOfSeats() {
		return noOfSeats;
	}

	public void setNoOfSeats(int noOfSeats) {
		this.noOfSeats = noOfSeats;
	}

	public RideProvide getRideProvide() {
		return rideProvide;
	}

	public void setRideProvide(RideProvide rideProvide) {
		this.rideProvide = rideProvide;
	}

	@jakarta.persistence.Column(name="Car_Name")
	@NotEmpty
	private String CarName;
	
	@jakarta.persistence.Column(name="Fuel_Type")
	@NotEmpty
	private String fuelType;
	
	@jakarta.persistence.Column(name="No_Of_Seats")
	@NotNull
	@Min(value=0)
	private int noOfSeats;

	@ManyToOne
   @JoinColumn(name = "Rp_Id", referencedColumnName = "Rp_Id",insertable = false,updatable = false)
    private RideProvide rideProvide;
/*
	public String getVechileNo() {
		return vechileNo;
	}

	public void setVechileNo(String vechileNo) {
		this.vechileNo = vechileNo;
	}

	public String getRpId() {
		return rpId;
	}

	public void setRpId(String rpId) {
		this.rpId = rpId;
	}

	public String getCarType() {
		return carType;
	}

	public void setCarType(String carType) {
		this.carType = carType;
	}

	public String getCarName() {
		return CarName;
	}

	public void setCarName(String carName) {
		CarName = carName;
	}

	public String getFuelType() {
		return fuelType;
	}

	public void setFuelType(String fuelType) {
		this.fuelType = fuelType;
	}

	public int getNoOfSeats() {
		return noOfSeats;
	}

	public void setNoOfSeats(int noOfSeats) {
		this.noOfSeats = noOfSeats;
	}

	public RideProvide getRideProvide() {
		return rideProvide;
	}

	public void setRideProvide(RideProvide rideProvide) {
		this.rideProvide = rideProvide;
	}
*/



	@Override
	public String toString() {
		return "RideInfo [rideInfoVehicleRpId=" + rideInfoVehicleRpId + ", carType=" + carType + ", CarName=" + CarName
				+ ", fuelType=" + fuelType + ", noOfSeats=" + noOfSeats + ", rideProvide=" + rideProvide + "]";
	}
	
	
}
========================================================
package com.cognizant.test;
import static org.junit.jupiter.api.Assertions.assertTrue;

import java.util.ArrayList;
import java.util.Optional;

import org.junit.jupiter.api.Test;

import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.ContextConfiguration;

import com.cognizant.entities.RideInfo;
import com.cognizant.entities.RideProvide;
import com.cognizant.main.RideProviderModuleApplication;
import com.cognizant.repositories.RideInfoRepository;
import com.cognizant.repositories.RideProvideRepository;

import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager;

import java.time.LocalDate;
import java.util.Optional;

import static org.junit.jupiter.api.Assertions.*;
import java.util.Optional;

import static org.junit.jupiter.api.Assertions.*;

@DataJpaTest
@ContextConfiguration(classes = RideProviderModuleApplication.class)
public class TestRideInfoRepository {

    @Autowired
    private RideInfoRepository rideInfoRepository;

    @Autowired
    private TestEntityManager entityManager;

    @Test
    public void testFindAllPositive() {
        RideInfo RI = new RideInfo();
        RideInfo.RideInfoVehicleRpId vehiclerpid=  RI.new RideInfoVehicleRpId();
        vehiclerpid.setRp_Id("R1");
        vehiclerpid.setVechileNo("V1");
          System.out.println("--data set in embeddable--");
       RI.setRideInfoVehicleRpId(vehiclerpid);
        RI.setCarType("SUV");
        RI.setCarName("Toyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        RideProvide R= new RideProvide();
        R.setRpId("R1");
        R.setAdharcard(123456789012L); // Adjusted to fit within long data type
        R.setFirstName("John");
        R.setLastName("Doe");
        R.setEmailId("john@example.com");
        R.setPhone(1234567890); // Adjusted to fit within int data type
        R.setDlNo("DL12345678901234");
        R.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        R.setStatus("Registered");
        System.out.println("--before persist--");
        entityManager.persist(R);    
        System.out.println("--After persist--");
        RideProvide rideProvide=entityManager.find(RideProvide.class,"R1");
        RI.setRideProvide(rideProvide);
        System.out.println("--before persist RI--");
        entityManager.persist(RI); 
        System.out.println("--after persist RI--");
        
        System.out.println(RI);

       //Iterable<RideInfo> it = rideInfoRepository.findAll();
        Iterable<RideInfo.RideInfoVehicleRpId> iterable=new ArrayList<>();
        rideInfoRepository.findAllById(iterable);
        rideInfoRepository.existsById(vehiclerpid);
      Optional<RideInfo> optionalOfRideInfo= rideInfoRepository.findById(vehiclerpid);
      assertTrue(optionalOfRideInfo.isPresent());
        
        //assertTrue(it.iterator().hasNext());
    }

    @Test
    public void testFindAllNegative() {
        Iterable<RideInfo> it = rideInfoRepository.findAll();
        assertFalse(it.iterator().hasNext());
    }

    @Test
    public void testFindByVechileNoPositive() {
    	RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Toyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        RideProvide R= new RideProvide();
        R.setRpId("RP001");
        R.setAdharcard(123456789012L); // Adjusted to fit within long data type
        R.setFirstName("John");
        R.setLastName("Doe");
        R.setEmailId("john@example.com");
        R.setPhone(1234567890); // Adjusted to fit within int data type
        R.setDlNo("DL12345678901234");
        R.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        R.setStatus("Registered");
        
        entityManager.persist(R);        
        RideProvide rideProvide=entityManager.find(RideProvide.class,"RP001");
        RI.setRideProvide(rideProvide);
        
        entityManager.persist(RI);  
        //error The method findById(RideInfoId) in the type CrudRepository<RideInfo,RideInfoId> is not applicable for the arguments (String)
        Optional<RideInfo> foundRideInfo = rideInfoRepository.findById("ABC123");
        assertTrue(foundRideInfo.isPresent());
    }

    @Test
    public void testFindByVechileNoNegative() {
    	//error The method findById(RideInfoId) in the type CrudRepository<RideInfo,RideInfoId> is not applicable for the arguments (String)
        Optional<RideInfo> notFoundRideInfo = rideInfoRepository.findById("InvalidVechileNo");
        assertFalse(notFoundRideInfo.isPresent());
    }

    @Test
    public void testSavePositive() {
    	RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Toyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        RideProvide R= new RideProvide();
        R.setRpId("RP001");
        R.setAdharcard(123456789012L); // Adjusted to fit within long data type
        R.setFirstName("John");
        R.setLastName("Doe");
        R.setEmailId("john@example.com");
        R.setPhone(1234567890); // Adjusted to fit within int data type
        R.setDlNo("DL12345678901234");
        R.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        R.setStatus("Registered");
        
        entityManager.persist(R);        
        RideProvide rideProvide=entityManager.find(RideProvide.class,"RP001");
        RI.setRideProvide(rideProvide);
        
        entityManager.persist(RI); 
        rideInfoRepository.save(RI);

        //error The method findById(RideInfoId) in the type CrudRepository<RideInfo,RideInfoId> is not applicable for the arguments (String)
        Optional<RideInfo> savedRideInfo = rideInfoRepository.findById("ABC123");
        assertTrue(savedRideInfo.isPresent());
    }

    @Test
    public void testDeletePositive() {
    	RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Toyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        RideProvide R= new RideProvide();
        R.setRpId("RP001");
        R.setAdharcard(123456789012L); // Adjusted to fit within long data type
        R.setFirstName("John");
        R.setLastName("Doe");
        R.setEmailId("john@example.com");
        R.setPhone(1234567890); // Adjusted to fit within int data type
        R.setDlNo("DL12345678901234");
        R.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        R.setStatus("Registered");
        
        entityManager.persist(R);        
        RideProvide rideProvide=entityManager.find(RideProvide.class,"RP001");
        RI.setRideProvide(rideProvide);
        
        entityManager.persist(RI); 

        rideInfoRepository.delete(RI);
        
        //error The method findById(RideInfoId) in the type CrudRepository<RideInfo,RideInfoId> is not applicable for the arguments (String)

        Optional<RideInfo> deletedRideInfo = rideInfoRepository.findById("ABC123");
        assertFalse(deletedRideInfo.isPresent());
    }
}
==============================================================================================================================
