# lombok-issue-1572-jdk10-sources-not-generated

Refers to an [1572 issue](https://github.com/rzwitserloot/lombok/issues/1572) reported in the [Lombok GitHub](https://github.com/rzwitserloot/lombok/issues). 

Considers the following problem:

```
[INFO] -------------------------------------------------------------
[ERROR] COMPILATION ERROR :
[INFO] -------------------------------------------------------------
[ERROR] /C:/Users/tomasz.zieleniewski/Desktop/tmp/jdeps-error-with-lombok/src/main/java/com/intive/Main.java:[14,16] cannot find symbol
  symbol:   method setUrl(java.lang.String)
  location: variable company of type com.intive.Company
[ERROR] /C:/Users/tomasz.zieleniewski/Desktop/tmp/jdeps-error-with-lombok/src/main/java/com/intive/Main.java:[15,35] cannot find symbol
  symbol:   method getUrl()
  location: variable company of type com.intive.Company
```

## Steps to reproduce

```bash
$ git clone https://github.com/tzieleniewski/lombok-examples.git
$ cd lombok-examples
$ git checkout lombok-issue-1572-jdk10-sources-not-generated
$ mvn clean package
```