# Ensure AWS Elasticsearch has node-to-node encryption enabled

 **org.openrewrite.terraform.aws.EnsureAWSElasticsearchHasNodeToNodeEncryptionEnabled** _Ensure AWS Elasticsearch has node-to-node encryption enabled._

### Tags

* CKV\_AWS\_6
* terraform
* AWS

## Source

[Github](https://github.com/openrewrite/rewrite-terraform), [Issue Tracker](https://github.com/openrewrite/rewrite-terraform/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-terraform/0.6.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-terraform
* version: 0.6.0

## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-terraform:0.6.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.10.0")
}

rewrite {
    activeRecipe("org.openrewrite.terraform.aws.EnsureAWSElasticsearchHasNodeToNodeEncryptionEnabled")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-terraform:0.6.0")
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
        <version>4.12.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.terraform.aws.EnsureAWSElasticsearchHasNodeToNodeEncryptionEnabled</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-terraform</artifactId>
            <version>0.6.0</version>
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

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.terraform.aws.EnsureAWSElasticsearchHasNodeToNodeEncryptionEnabled`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Terraform configuration](../addconfiguration.md)
  * resourceName: `aws_elasticsearch_domain`
  * content: \`node\_to\_node\_encryption {

    enabled = true

    }\`
{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.terraform.aws.EnsureAWSElasticsearchHasNodeToNodeEncryptionEnabled
displayName: Ensure AWS Elasticsearch has node-to-node encryption enabled
description: Ensure AWS Elasticsearch has node-to-node encryption enabled.
tags:
  - CKV_AWS_6
  - terraform
  - AWS
recipeList:
  - org.openrewrite.terraform.AddConfiguration:
      resourceName: aws_elasticsearch_domain
      content: node_to_node_encryption {
  enabled = true
}
```
{% endtab %}
{% endtabs %}
