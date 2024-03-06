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
