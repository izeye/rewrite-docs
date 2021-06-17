# Kubernetes best practices

** org.openrewrite.kubernetes.KubernetesBestPractices**
_Applies best practices to Kubernetes manifests._

### Tags

* kubernetes

## Source

Maven Central [entry](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-kubernetes/1.1.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-kubernetes
* version: 1.1.0

## Recipe list

* [Ensure liveness probe is configured](../kubernetes/missingpodlivenessprobe.md)
* [Ensure readiness probe is configured](../kubernetes/missingpodreadinessprobe.md)
* [Ensure CPU request is set](../kubernetes/missingcpurequest.md)
* [Ensure CPU limits are set](../kubernetes/missingcpulimits.md)
* [Ensure memory request is set](../kubernetes/missingmemoryrequest.md)
* [Ensure memory limits are set](../kubernetes/missingmemorylimits.md)
* [No privileged containers](../kubernetes/noprivilegedcontainers.md)
* [Ensure lifecycle rule on `StorageBucket`](../kubernetes/lifecycleruleonstoragebucket.md)
* [No host process ID sharing](../kubernetes/nohostprocessidsharing.md)
* [No host IPC sharing](../kubernetes/nohostipcsharing.md)
* [No root containers](../kubernetes/norootcontainers.md)
* [Ensure image pull policy is `Always`](../kubernetes/imagepullpolicyalways.md)
* [No privilege escalation](../kubernetes/noprivilegeescalation.md)
* [No host network sharing](../kubernetes/nohostnetworksharing.md)
* [Read-only root filesystem](../kubernetes/readonlyrootfilesystem.md)
* [Limit root capabilities in a container](../kubernetes/limitcontainercapabilities.md)

## Usage
This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-kubernetes:1.1.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.1.0")
}

rewrite {
    activeRecipe("org.openrewrite.kubernetes.KubernetesBestPractices")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-kubernetes:1.1.0")
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
            <recipe>org.openrewrite.kubernetes.KubernetesBestPractices</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-kubernetes</artifactId>
            <version>1.1.0</version>
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

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.kubernetes.KubernetesBestPractices`