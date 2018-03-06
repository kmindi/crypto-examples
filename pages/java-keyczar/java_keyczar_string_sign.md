---
title: String Signing in Java using keyczar
keywords: sample
summary: "Java based string signing with keyczar"
permalink: java_keyczar_string_sign.html
folder: Java Keyczar
tags: [Java, hash]
---

## Use cases

- verifying if a string has been changed

## Preparations

### Dependency on keyczar library

Currently, keyczar is not available via Maven or similar dependency management systems. Therefore the easiest way to include the library is to add the libraries' jar-file to the classpath.

### Key generation

Keyczar stores encryption/deryption/signing-keys in a specific JSON-format. 
They have to be generated by the included `KeyczarTool` like the following:

- java org.keyczar.KeyczarTool create --location=./rsaKey --purpose=crypt --asymmetric=rsa --name="RSA Key"
- java org.keyczar.KeyczarTool addkey --location=./rsaKey --size=4096
- java org.keyczar.KeyczarTool promote --location=./rsaKey --version=1

## Sample Code for Java based signing of a String using RSA

```java
{% include_relative java-keyczar-crypto-examples/src/main/java/com/cryptoexamples/java/keyczar/ExampleSignatureInOneMethod.java %}
```



{% include links.html %}