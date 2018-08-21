# jdeps-error-with-lombok

Replicates the following [jdeps](https://docs.oracle.com/javase/9/tools/jdeps.htm) (Java class dependency analyzer) error caused by [Lombok](https://projectlombok.org).

```
java.lang.module.ResolutionException: Module lombok does not read a module that exports org.mapstruct.ap.spi
```

A problem was reported in the [Lombok GitHub issue](https://github.com/rzwitserloot/lombok/issues/1806).

## Steps to reproduce

```bash
$ git clone https://github.com/tzieleniewski/jdeps-error-with-lombok.git
$ cd jdeps-error-with-lombok
$ mvn clean package
$ jdeps --module-path target/dependency -R target/jdeps-error-with-lombok-1.0.0-SNAPSHOT.jar
```