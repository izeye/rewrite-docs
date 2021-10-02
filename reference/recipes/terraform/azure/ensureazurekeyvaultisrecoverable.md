# Ensure Azure key vault is recoverable

 **org.openrewrite.terraform.azure.EnsureAzureKeyVaultIsRecoverable** _Ensure Azure key vault is recoverable._

### Tags

* Azure
* CKV\_AZURE\_42
* terraform

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
    activeRecipe("org.openrewrite.terraform.azure.EnsureAzureKeyVaultIsRecoverable")
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
            <recipe>org.openrewrite.terraform.azure.EnsureAzureKeyVaultIsRecoverable</recipe>
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

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.terraform.azure.EnsureAzureKeyVaultIsRecoverable`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Terraform configuration](../addconfiguration.md)
  * resourceName: `azurerm_key_vault`
  * content: `soft_delete_enabled = true`
* [Add Terraform configuration](../addconfiguration.md)
  * resourceName: `azurerm_key_vault`
  * content: `purge_protection_enabled = true`
{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.terraform.azure.EnsureAzureKeyVaultIsRecoverable
displayName: Ensure Azure key vault is recoverable
description: Ensure Azure key vault is recoverable.
tags:
  - Azure
  - CKV_AZURE_42
  - terraform
recipeList:
  - org.openrewrite.terraform.AddConfiguration:
      resourceName: azurerm_key_vault
      content: soft_delete_enabled = true
  - org.openrewrite.terraform.AddConfiguration:
      resourceName: azurerm_key_vault
      content: purge_protection_enabled = true
```
{% endtab %}
{% endtabs %}
