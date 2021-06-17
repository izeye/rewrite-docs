# Use `SimpleAnnotationValueVisitor9`

** org.openrewrite.java.migrate.javax.MigrateSimpleAnnotationValueVisitor6To9**
_`SimpleAnnotationValueVisitor6` was deprecated in Java 9._

## Source

Maven Central [entry](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-migrate-java/0.2.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 0.2.0

## Recipe list

* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.lang.model.util.SimpleAnnotationValueVisitor6`
  * newFullyQualifiedTypeName: `javax.lang.model.util.SimpleAnnotationValueVisitor9`

## Usage
This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-migrate-java:0.2.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.1.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.javax.MigrateSimpleAnnotationValueVisitor6To9")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:0.2.0")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.5.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.javax.MigrateSimpleAnnotationValueVisitor6To9</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>0.2.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.java.migrate.javax.MigrateSimpleAnnotationValueVisitor6To9`