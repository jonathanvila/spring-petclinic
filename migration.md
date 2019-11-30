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
1. add Quarkus dependencies
2. Spring Actuator
   1. SmallRye metrics, health 
3. Spring Cache
   1. Using Infinispan embedded
4. Use of H2 in memory database
   1. Need to annotate Test classes in order to make the build compatible with GraalVM
   2. https://quarkus.io/guides/datasource#in-memory-databases

