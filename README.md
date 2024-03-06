
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
