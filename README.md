# Quarkus jOOQ extension

This is a https://github.com/quarkusio/quarkus extension for https://github.com/jOOQ/jOOQ.

Updated version of this prior work https://github.com/leotu/quarkus-ext-jooq

**Warning - this should not be considered production ready!**

```sh
git clone https://github.com/itboy87/quarkus-ext-jooq.git
cd quarkus-ext-jooq
mvn clean install
```

This will make the following dependency available:

```xml
<dependency>
    <groupId>io.quarkus.ext</groupId>
    <artifactId>quarkus-ext-jooq</artifactId>
    <version>1.9.2-SNAPSHOT</version>
</dependency>
```
Or for gradle something like:

```sh
compile 'io.quarkus.ext:quarkus-ext-jooq:1.0-SNAPSHOT'
```
You also need quarkus-agroal:

```sh
./gradlew addExtension --extensions="io.quarkus:quarkus-agroal"

# or for maven users

./mvnw quarkus:add-extension -Dextensions="io.quarkus:quarkus-agroal"
```
The minimum required configuration after adding you chosen database drivers (in this case postgres) would be:

```properties
quarkus.jooq.dialect=PostgresSQL

quarkus.datasource.url=jdbc:postgresql:db_name
quarkus.datasource.driver=org.postgresql.Driver
quarkus.datasource.username=postgres
quarkus.datasource.password=********
```

The DSL context can then be injected with:

```java
@Inject
DSLContext dsl; // default
```