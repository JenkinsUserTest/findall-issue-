package com.cognizant.entities;

import java.time.LocalDate;
import java.util.Date;
import java.util.Objects;

import jakarta.persistence.Column;
import jakarta.persistence.Entity;
import jakarta.persistence.Id;
import jakarta.persistence.Table;
import jakarta.persistence.Column;
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.GenerationType;
import jakarta.persistence.Id;
import jakarta.persistence.Table;
import jakarta.validation.constraints.NotEmpty;
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Size;
import jakarta.validation.constraints.Min; 
import jakarta.persistence.*;
import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.*;

@Entity
@Table(name="Ride_Provide" )
public class RideProvide {

	
	
	@Id
	@Column(name="Rp_Id")
	private  String  rpId;
	
	
	@Column(name="Adhar_Card")
	@NotNull
	private Long adharcard;
	
	
	@Column(name="Email_Id")
	@NotEmpty
	@Email
	private String emailId;
	
	@Column(name="Phone")
	@NotNull
	private long phone;
	
	@Column(name="First_Name")
	@NotEmpty
	@Size(min=3)
	private String firstName;
	
	@Column(name="Last_Name")
	@NotEmpty
	@Size(min=3)
	private String lastName;
	
	@Column(name="Dl_No")
	@NotNull
	@Size(min=16, max=16)
	private String dlNo;
	
	@Column(name="Valid_Upto")
	@NotNull
	@Future
	private LocalDate validUpto;
	
	@Column(name="Status")
	@NotEmpty
	private String status;

	public String getRpId() {
		return rpId;
	}

	public void setRpId(String rpId) {
		this.rpId = rpId;
	}

	public Long getAdharcard() {
		return adharcard;
	}

	public void setAdharcard(Long adharcard) {
		this.adharcard = adharcard;
	}

	public String getEmailId() {
		return emailId;
	}

	public void setEmailId(String emailId) {
		this.emailId = emailId;
	}

	public long getPhone() {
		return phone;
	}

	public void setPhone(long phone) {
		this.phone = phone;
	}

	public String getFirstName() {
		return firstName;
	}

	public void setFirstName(String firstName) {
		this.firstName = firstName;
	}

	public String getLastName() {
		return lastName;
	}

	public void setLastName(String lastName) {
		this.lastName = lastName;
	}

	public String getDlNo() {
		return dlNo;
	}

	public void setDlNo(String dlNo) {
		this.dlNo = dlNo;
	}

	public LocalDate getValidUpto() {
		return validUpto;
	}

	public void setValidUpto(LocalDate validUpto) {
		this.validUpto = validUpto;
	}

	public String getStatus() {
		return status;
	}

	public void setStatus(String status) {
		this.status = status;
	}

	@Override
	public int hashCode() {
		return Objects.hash(adharcard, dlNo, emailId, firstName, lastName, phone, rpId, status, validUpto);
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		RideProvide other = (RideProvide) obj;
		return adharcard == other.adharcard && Objects.equals(dlNo, other.dlNo)
				&& Objects.equals(emailId, other.emailId) && Objects.equals(firstName, other.firstName)
				&& Objects.equals(lastName, other.lastName) && phone == other.phone && Objects.equals(rpId, other.rpId)
				&& Objects.equals(status, other.status) && Objects.equals(validUpto, other.validUpto);
	}
	

	
	
	
	
	
	
	
	

}

===========================================================
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


===============================================================================

package com.cognizant.entities;

import java.util.Objects;

import jakarta.persistence.Column;
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.GenerationType;
import jakarta.persistence.Id;
import jakarta.persistence.JoinColumn;
import jakarta.persistence.ManyToOne;
import jakarta.persistence.Table;
import jakarta.validation.constraints.Min;
import jakarta.validation.constraints.NotEmpty;
import jakarta.validation.constraints.NotNull;
import jakarta.validation.constraints.Size;


@Entity
@Table(name="Simles" )
public class Simles {

	@Id
	@jakarta.persistence.Column(name="Smile_Id")
	private Integer smileId;
	
	@jakarta.persistence.Column(name="Rp_Id")
	@NotNull
	private String rpId;
	
	@jakarta.persistence.Column(name="Source")
	@NotEmpty
	private String source;
	
	@jakarta.persistence.Column(name="Destination")
	@NotEmpty
	private String destination;	
	
	@jakarta.persistence.Column(name="Occupancy")
	@NotNull
	@Min(value=0)
	private int occupancy;

	@ManyToOne
   // @JoinColumn(name = "Rp_Id", referencedColumnName = "Rp_Id",insertable = false,updatable = false)
    private RideInfo rideInfo;

	public Integer getSmileId() {
		return smileId;
	}

	public void setSmileId(Integer smileId) {
		this.smileId = smileId;
	}

	public String getRpId() {
		return rpId;
	}

	public void setRpId(String rpId) {
		this.rpId = rpId;
	}

	public String getSource() {
		return source;
	}

	public void setSource(String source) {
		this.source = source;
	}

	public String getDestination() {
		return destination;
	}

	public void setDestination(String destination) {
		this.destination = destination;
	}

	public int getOccupancy() {
		return occupancy;
	}

	public void setOccupancy(int occupancy) {
		this.occupancy = occupancy;
	}

	public RideInfo getRideInfo() {
		return rideInfo;
	}

	public void setRideInfo(RideInfo rideInfo) {
		this.rideInfo = rideInfo;
	}

	@Override
	public int hashCode() {
		return Objects.hash(destination, occupancy, rideInfo, rpId, smileId, source);
	}

	@Override
	public boolean equals(Object obj) {
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Simles other = (Simles) obj;
		return Objects.equals(destination, other.destination) && occupancy == other.occupancy
				&& Objects.equals(rideInfo, other.rideInfo) && Objects.equals(rpId, other.rpId)
				&& Objects.equals(smileId, other.smileId) && Objects.equals(source, other.source);
	}

	
	
}
=====================================================================================

package com.cognizant.repositories;
import java.util.Optional;
import org.springframework.data.repository.CrudRepository;
import org.springframework.stereotype.Repository;

import com.cognizant.entities.RideProvide;


@Repository
public interface RideProvideRepository extends CrudRepository<RideProvide,String> {

    
}

=============================================================================================

package com.cognizant.repositories;
import org.springframework.data.repository.CrudRepository;
import org.springframework.stereotype.Repository;

import com.cognizant.entities.RideInfo;



@Repository
public interface RideInfoRepository extends CrudRepository<RideInfo,RideInfo.RideInfoVehicleRpId> {

    
}
====================================================================
package com.cognizant.repositories;

import java.util.Optional;

import org.springframework.data.repository.CrudRepository;
import org.springframework.stereotype.Repository;

import com.cognizant.entities.Simles;


@Repository
public interface SimlesRepository extends CrudRepository<Simles,Integer> {

	

    
}
=================================================================

h2 generated schema.sql

create table ride_info (no_of_seats integer not null check (no_of_seats>=0), car_name varchar(255), car_type varchar(255), fuel_type varchar(255), rp_id varchar(255) not null, vechile_no varchar(255) not null, primary key (rp_id, vechile_no));
create table ride_provide (valid_upto date not null, adhar_card bigint not null, phone bigint not null, dl_no varchar(16) not null, email_id varchar(255), first_name varchar(255), last_name varchar(255), rp_id varchar(255) not null, status varchar(255), primary key (rp_id));
create table simles (occupancy integer not null check (occupancy>=0), smile_id integer not null, destination varchar(255), ride_info_rp_id varchar(255), ride_info_vechile_no varchar(255), rp_id varchar(255) not null, source varchar(255), primary key (smile_id));
alter table if exists ride_info add constraint FK65lemwkl0192ybn6gf85bcq4q foreign key (rp_id) references ride_provide;
alter table if exists simles add constraint FKs7e8br32x0jmpjtm3yh3yiydd foreign key (ride_info_rp_id, ride_info_vechile_no) references ride_info;

==================================================================

package com.cognizant.test;

import static org.junit.jupiter.api.Assertions.assertTrue;

import java.util.Optional;

import org.junit.jupiter.api.Test;

import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.ContextConfiguration;

import com.cognizant.entities.RideProvide;
import com.cognizant.main.RideProviderModuleApplication;
import com.cognizant.repositories.RideProvideRepository;

import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager;

import java.time.LocalDate;
import java.util.Optional;

import static org.junit.jupiter.api.Assertions.*;

@DataJpaTest
@ContextConfiguration(classes = RideProviderModuleApplication.class)
public class TestRideProvideRepository {

    @Autowired
    private RideProvideRepository rideProvideRepository;

    @Autowired
    private TestEntityManager entityManager;

    @Test
    public void testFindAllPositive() {
        RideProvide rideProvide = new RideProvide();
        rideProvide.setRpId("RP001");
        rideProvide.setFirstName("John");
        rideProvide.setLastName("Doe");
        rideProvide.setEmailId("john@example.com");
        rideProvide.setAdharcard(123456789012L); // Adjusted to fit within long data type
        rideProvide.setPhone(1234567890); // Adjusted to fit within int data type
        rideProvide.setDlNo("DL12345678901234");
        rideProvide.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        rideProvide.setStatus("Registered");
        entityManager.persist(rideProvide);

        Iterable<RideProvide> it = rideProvideRepository.findAll();
        assertTrue(it.iterator().hasNext());
    }

    @Test
    public void testFindAllNegative() {
        Iterable<RideProvide> it = rideProvideRepository.findAll();
        assertFalse(it.iterator().hasNext());
    }

    @Test
    public void testFindByIdPositive() {
        RideProvide rideProvide = new RideProvide();
        rideProvide.setRpId("RP001");
        rideProvide.setAdharcard(123456789012L); // Adjusted to fit within long data type
        rideProvide.setFirstName("John");
        rideProvide.setLastName("Doe");
        rideProvide.setEmailId("john@example.com");
        rideProvide.setPhone(1234567890); // Adjusted to fit within int data type
        rideProvide.setDlNo("DL12345678901234");
        rideProvide.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        rideProvide.setStatus("Registered");
        entityManager.persist(rideProvide);

        Optional<RideProvide> foundRideProvide = rideProvideRepository.findById("RP001");
        assertTrue(foundRideProvide.isPresent());
    }

    @Test
    public void testFindByIdNegative() {
        Optional<RideProvide> notFoundRideProvide = rideProvideRepository.findById("InvalidRpId");
        assertFalse(notFoundRideProvide.isPresent());
    }

    @Test
    public void testSavePositive() {
        RideProvide rideProvide = new RideProvide();
        rideProvide.setRpId("RP001");
        rideProvide.setAdharcard(123456789012L); // Adjusted to fit within long data type
        rideProvide.setFirstName("John");
        rideProvide.setLastName("Doe");
        rideProvide.setEmailId("john@example.com");
        rideProvide.setPhone(1234567890); // Adjusted to fit within int data type
        rideProvide.setDlNo("DL12345678901234");
        rideProvide.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        rideProvide.setStatus("Registered");
        rideProvideRepository.save(rideProvide);

        Optional<RideProvide> savedRideProvide = rideProvideRepository.findById("RP001");
        assertTrue(savedRideProvide.isPresent());
    }

    @Test
    public void testDeletePositive() {
        RideProvide rideProvide = new RideProvide();
        rideProvide.setRpId("RP001");
        rideProvide.setFirstName("John");
        rideProvide.setLastName("Doe");
        rideProvide.setEmailId("john@example.com");
        rideProvide.setAdharcard(123456789012L); // Adjusted to fit within long data type
        rideProvide.setPhone(1234567890); // Adjusted to fit within int data type
        rideProvide.setDlNo("DL12345678901234");
        rideProvide.setValidUpto(LocalDate.now().plusDays(31)); // Valid upto 30 days from current date
        rideProvide.setStatus("Registered");
        entityManager.persist(rideProvide);

        rideProvideRepository.delete(rideProvide);

        Optional<RideProvide> deletedRideProvide = rideProvideRepository.findById("RP001");
        assertFalse(deletedRideProvide.isPresent());
    }
}

==================================================================
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
=============================================================
package com.cognizant.test;

import static org.junit.jupiter.api.Assertions.assertTrue;

import java.util.Optional;

import org.junit.jupiter.api.Test;

import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.ContextConfiguration;

import com.cognizant.entities.RideInfo;
import com.cognizant.entities.RideProvide;
import com.cognizant.main.RideProviderModuleApplication;
import com.cognizant.repositories.RideProvideRepository;

import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager;

import java.time.LocalDate;
import java.util.Optional;

import static org.junit.jupiter.api.Assertions.*;

import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager;

import com.cognizant.entities.Simles;
import com.cognizant.repositories.SimlesRepository;

import java.util.Optional;

import static org.junit.jupiter.api.Assertions.*;



import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.orm.jpa.DataJpaTest;
import org.springframework.boot.test.autoconfigure.orm.jpa.TestEntityManager;

import java.util.Optional;

import static org.junit.jupiter.api.Assertions.*;

@DataJpaTest
@ContextConfiguration(classes = RideProviderModuleApplication.class)
public class TestSimlesRepository {

    @Autowired
    private SimlesRepository simlesRepository;

    @Autowired
    private TestEntityManager entityManager;

    @Test
    public void testFindAllPositive() {
    	
        Simles simles = new Simles();
        simles.setSmileId(1);
        simles.setRpId("RP001"); // Assuming RP001 exists as a valid foreign key
        simles.setSource("Source");
        simles.setDestination("Destination");
        simles.setOccupancy(3);
        
        //ride info
        RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Tgoyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        //ride provide
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
        RideInfo rideInfo=entityManager.find(RideInfo.class,"ABC123" );
        simles.setRideInfo(rideInfo);
        
        
        entityManager.persist(simles);

        Iterable<Simles> it = simlesRepository.findAll();
        assertTrue(it.iterator().hasNext());
    }

    @Test
    public void testFindAllNegative() {
        Iterable<Simles> it = simlesRepository.findAll();
        assertFalse(it.iterator().hasNext());
    }

    @Test
    public void testFindBySmileIdPositive() {
    	Simles simles = new Simles();
        simles.setSmileId(1);
        simles.setRpId("RP001"); // Assuming RP001 exists as a valid foreign key
        simles.setSource("Source");
        simles.setDestination("Destination");
        simles.setOccupancy(3);
        
        //ride info
        RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Tgoyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        //ride provide
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
        RideInfo rideInfo=entityManager.find(RideInfo.class,"ABC123" );
        simles.setRideInfo(rideInfo);
        
        
        entityManager.persist(simles);


        Optional<Simles> foundSimles = simlesRepository.findById(1);
        assertTrue(foundSimles.isPresent());
    }

    @Test
    public void testFindBySmileIdNegative() {
        Optional<Simles> notFoundSimles = simlesRepository.findById(9999);
        assertFalse(notFoundSimles.isPresent());
    }

    @Test
    public void testSavePositive() {
    	Simles simles = new Simles();
        simles.setSmileId(1);
        simles.setRpId("RP001"); // Assuming RP001 exists as a valid foreign key
        simles.setSource("Source");
        simles.setDestination("Destination");
        simles.setOccupancy(3);
        
        //ride info
        RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Tgoyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        //ride provide
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
        RideInfo rideInfo=entityManager.find(RideInfo.class,"ABC123" );
        simles.setRideInfo(rideInfo);
        
        
        entityManager.persist(simles);

        simlesRepository.save(simles);

        Optional<Simles> savedSimles = simlesRepository.findById(1);
        assertTrue(savedSimles.isPresent());
    }

    @Test
    public void testDeletePositive() {
    	Simles simles = new Simles();
        simles.setSmileId(1);
        simles.setRpId("RP001"); // Assuming RP001 exists as a valid foreign key
        simles.setSource("Source");
        simles.setDestination("Destination");
        simles.setOccupancy(3);
        
        //ride info
        RideInfo RI = new RideInfo();
        RI.setVechileNo("ABC123");
        RI.setRpId("RP001");
        RI.setCarType("SUV");
        RI.setCarName("Tgoyota RAV4");
        RI.setFuelType("Petrol");
        RI.setNoOfSeats(5);
        
        //ride provide
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
        RideInfo rideInfo=entityManager.find(RideInfo.class,"ABC123" );
        simles.setRideInfo(rideInfo);
        
        
        entityManager.persist(simles);


        simlesRepository.delete(simles);

        Optional<Simles> deletedSimles = simlesRepository.findById(1);
        assertFalse(deletedSimles.isPresent());
    }

   
}
===============================================================

