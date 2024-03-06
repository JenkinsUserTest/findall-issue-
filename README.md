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
