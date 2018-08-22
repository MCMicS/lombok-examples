# lombok-issue-1806-jdeps-error-non-modular-jar

Refers to an [1806 issue](https://github.com/rzwitserloot/lombok/issues/1806) reported in the [Lombok GitHub](https://github.com/rzwitserloot/lombok/issues). 

Considers the following [jdeps](https://docs.oracle.com/javase/9/tools/jdeps.htm) (Java class dependency analyzer) error caused by [Lombok](https://projectlombok.org).

```
java.lang.module.ResolutionException: Module lombok does not read a module that exports org.mapstruct.ap.spi
```

## Steps to reproduce

```bash
$ git clone https://github.com/tzieleniewski/lombok-examples.git
$ cd lombok-examples
$ git checkout lombok-issue-1806-jdeps-error-non-modular-jar
$ mvn clean package
$ jdeps --module-path target/dependency -R target/lombok-examples-1.0.0-SNAPSHOT.jar
```