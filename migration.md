# Migration of Spring Pet Clinic to Quarkus

## Libraries used

1. Spring
   1. actuator
   2. cache
   3. data-jpa
   4. web
   5. thymeleaf
   6. test
   7. devtools
2. hsqldb
3. mysql
4. cache-api
5. ehcache
6. jquery
7. jquery-ui
8. bootstrap

## Steps

1. Add Quarkus dependencies
2. Spring Actuator
   1. SmallRye metrics, health 
3. Spring Cache
   1. Using Infinispan embedded
4. Use of H2 in memory database
   1. Need to annotate Test classes in order to make the build compatible with GraalVM
   2. https://quarkus.io/guides/datasource#in-memory-databases
5. Replace Spring Data
   1. Using Quarkus Hibernate Panache
   2. removing use of @Param in find methods
6. Replace Spring PropertyComparator and MutableSortDefinition
   1. Using a Java Stream lambda
7. Replace Spring ToStringCreator
   1. Using StringBuilder
8. Replace Find methods of Spring Repository
   1. Using PanacheRepository
   2. Putting the Query inside the method
   3. Converting the interface into a Class
9. Converting Entity to PanacheEntity
10. When we want to implement a cacheable *findAll* method we have issues
    1. because findAll is already implemented and doesnt have a List\<T\> as return type
    2. for the moment renamed to find_All
11. Added JUnit 5


