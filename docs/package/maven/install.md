---
title: Install Maven packages from your feed using the Maven client
description: Successfully install Maven packages from VSTS or Team Foundation Server
ms.prod: vs-devops-alm
ms.technology: vs-devops-package
ms.assetid: 0f66e727-e76a-4a72-be12-3fa1775b9e2c
ms.manager: jenp
ms.author: rossav
ms.date: 09/01/2017
---

# Install Maven packages in VSTS and TFS

[!INCLUDE [](../_shared/availability-maven.md)]

[!INCLUDE [](../_shared/maven/install.md)]

	
**Sample `pom.xml`:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
   <modelVersion>4.0.0</modelVersion>
   <groupId>MyGroup</groupId>
   <artifactId>myFirstApp</artifactId>
   <packaging>jar</packaging>
   <version>1.0-SNAPSHOT</version>
   <name>myFirstApp</name>
   <url>http://maven.apache.org</url>
   <dependencies>
      <dependency>
         <groupId>junit</groupId>
         <artifactId>junit</artifactId>
         <version>3.8.1</version>
         <scope>test</scope>
      </dependency>
   </dependencies>
   <repositories>
    <!-- Copy this section from the Maven section of the “Connect to Feed” dialog” -->
      <repository>
         <id>mseng-visualstudio.com-zcalvinmaven</id>
         <url>https://mseng.pkgs.visualstudio.com/_packaging/zCalvinMaven2/maven/v1</url>
         <releases>
            <enabled>true</enabled>
         </releases>
         <snapshots>
            <enabled>true</enabled>
         </snapshots>
      </repository>
   </repositories>
   <distributionManagement>
    <!-- Copy this section from the Maven section of the “Connect to Feed” dialog” -->
      <repository>
         <id>mseng-visualstudio.com-zcalvinmaven</id>
         <url>https://mseng.pkgs.visualstudio.com/_packaging/zCalvinMaven2/maven/v1</url>
         <releases>
            <enabled>true</enabled>
         </releases>
         <snapshots>
            <enabled>true</enabled>
         </snapshots>
      </repository>
   </distributionManagement>
</project>
```