# Description

First Voices Java Style Guide based on the [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)

# File Descriptions

- `java-fv-google-style-strict.xml`: Checks based on the official Google Style Guide
- `java/intellij-java-fv-google-style.xml`: IntelliJ code style schema. Works with IntelliJ.
- `java/eclipse-java-fv-google-style.xml`: Eclipse code style configuration, works with Eclipse code formatter plugins

# Installation

## Installing the coding style settings in Intellij

Download the xml file from `https://raw.githubusercontent.com/First-Peoples-Cultural-Council/fv-checkstyle/master/java/intellij-java-fv-google-style.xml`.

### Windows

Under File->Settings -> Editor -> Code Style, click on the little gear next to Scheme. Click on import Scheme and select the file you donwloaded as the current code style for your project. Finish it off by clicking Apply.

### Macintosh

Go to Preferences -> Editor -> Code Style. Click on Manage and import the downloaded file. Select `FV_GoogleStyle` as new coding style.

## Configuring Checkstyle Plugin in IntelliJ

Install the IntelliJ Checkstyle Plugin. It can be found via plug-in repository (Settings -> Plugins -> Browse repositories). Open the Settings. Go to Other Settings -> CheckStyle. Click on the plus and click "Use a checkstyle file accessible by HTTP". Paste the URL of the xml file: `https://raw.githubusercontent.com/First-Peoples-Cultural-Council/fv-checkstyle/master/java/java-fv-google-style-strict.xml`. Name it `FVCheckstyle`.

## Installing the coding style settings in Eclipse

Download the xml file from the `https://raw.githubusercontent.com/First-Peoples-Cultural-Council/fv-checkstyle/master/java/eclipse-java-fv-google-style.xml`. repo. Under Window/Preferences select Java/Code Style/Formatter. Import the settings file by selecting Import.

## To enforce strict checkstyle rules:

To enforce strict checkstyle rules, in the root `pom.xml` of project, add the following plugin and execution configuration to `<build>`:

```xml
 <plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-checkstyle-plugin</artifactId>
    <version>3.1.1</version>
    <configuration>
        <configLocation>https://raw.githubusercontent.com/First-Peoples-Cultural-Council/fv-checkstyle/master/java/java-fv-google-style-strict.xml</configLocation>
    </configuration>
    <executions>
        <execution>
        <goals>
            <goal>check</goal>
        </goals>
        </execution>
    </executions>
</plugin>
```

## Contributing to checkstyle rules:

These checkstyle rules act as a guideline for all developers on FirstVoices and similar products at FPCC. If a style does not suit your development needs, we encourage developers to contribute to the checkstyle rules by submitting a PR.

## TODO:

- Update Copyright Documentation
