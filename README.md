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

-d D:\IntelliJ\lombok-examples\target\classes -classpath P:\Maven Repository\repo\org\mapstruct\mapstruct-processor\1.2.0.Final\mapstruct-processor-1.2.0.Final.jar; --module-path D:\IntelliJ\lombok-examples\target\classes;P:\Maven Repository\repo\org\projectlombok\lombok\1.18.2\lombok-1.18.2.jar; -sourcepath D:\IntelliJ\lombok-examples\src\main\java;D:\IntelliJ\lombok-examples\target\generated-sources\annotations; -s D:\IntelliJ\lombok-examples\target\generated-sources\annotations -g -verbose -deprecation -Werror --release 10 -encoding UTF-8 --processor-module-path P:\Maven Repository\repo\org\projectlombok\lombok\1.18.2\lombok-1.18.2.jar; -verbose -XprintRounds -XprintProcessorInfo -Xlint -J-verbose

--upgrade-module-path

javac -d "D:\IntelliJ\lombok-examples\target\classes2" -classpath "P:\Maven Repository\repo\org\mapstruct\mapstruct-processor\1.2.0.Final\mapstruct-processor-1.2.0.Final.jar;" --module-path "D:\IntelliJ\lombok-examples\target\classes;P:\Maven Repository\repo\org\projectlombok\lombok\1.18.2\lombok-1.18.2.jar;" -sourcepath "D:\IntelliJ\lombok-examples\src\main\java;D:\IntelliJ\lombok-examples\target\generated-sources\annotations;" -s "D:\IntelliJ\lombok-examples\target\generated-sources\annotations" -g -verbose -deprecation -Werror --release 10 -encoding UTF-8 --processor-module-path "P:\Maven Repository\repo\org\projectlombok\lombok\1.18.2\lombok-1.18.2.jar;" -verbose -XprintRounds -XprintProcessorInfo -Xlint -J-verbose
javac -d "D:\IntelliJ\lombok-examples\target\classes2" -classpath "P:\Maven Repository\repo\org\mapstruct\mapstruct-processor\1.2.0.Final\mapstruct-processor-1.2.0.Final.jar;" --module-path "D:\IntelliJ\lombok-examples\target\classes;P:\Maven Repository\repo\org\projectlombok\lombok\1.18.3\lombok-1.18.3.jar;" -sourcepath "D:\IntelliJ\lombok-examples\src\main\java;D:\IntelliJ\lombok-examples\target\generated-sources\annotations;" -s "D:\IntelliJ\lombok-examples\target\generated-sources\annotations" -g -verbose -deprecation -Werror --release 10 -encoding UTF-8 --processor-module-path "P:\Maven Repository\repo\org\projectlombok\lombok\1.18.3\lombok-1.18.3.jar;" -verbose -XprintRounds -XprintProcessorInfo -Xlint -J-verbose

1.18.3
P:\Java\jdk-11\bin\javac -d "D:\IntelliJ\lombok-examples\target\classes2" -classpath "P:\Maven Repository\repo\org\mapstruct\mapstruct-processor\1.2.0.Final\mapstruct-processor-1.2.0.Final.jar;" --module-path "D:\IntelliJ\lombok-examples\target\classes;P:\Maven Repository\repo\org\mapstruct\mapstruct-processor\1.2.0.Final\mapstruct-processor-1.2.0.Final.jar;P:\Maven Repository\repo\org\projectlombok\lombok\1.18.2\lombok-1.18.3.jar;" -sourcepath "D:\IntelliJ\lombok-examples\src\main\java;D:\IntelliJ\lombok-examples\target\generated-sources\annotations;" -s "D:\IntelliJ\lombok-examples\target\generated-sources\annotations" -g -verbose -deprecation -Werror --release 10 -encoding UTF-8 --processor-module-path "P:\Maven Repository\repo\org\projectlombok\lombok\1.18.3\lombok-1.18.3.jar;P:\Maven Repository\repo\org\mapstruct\mapstruct-processor\1.2.0.Final\mapstruct-processor-1.2.0.Final.jar;" -verbose -XprintRounds -XprintProcessorInfo -Xlint -J-verbose @javac.conf

-J--module-path="P:\Maven Repository\repo\org\projectlombok\lombok\1.18.3\lombok-1.18.3.jar"

P:\Java\jdk-11\bin\javac -verbose -XprintRounds -XprintProcessorInfo -Xlint -J-verbose --processor-module-path "P:\Maven Repository\repo\org\projectlombok\lombok\1.18.3\lombok-1.18.3.jar"