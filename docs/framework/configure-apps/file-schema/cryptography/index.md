---
title: "Esquema de la configuraci&#243;n de criptograf&#237;a | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "esquema de configuración [.NET Framework], criptografía"
  - "secciones de configuración [.NET Framework]"
  - "valores de configuración [.NET Framework], criptografía"
  - "criptografía, asignar nombres de algoritmo"
  - "criptografía, esquema de configuración"
  - "elementos [.NET Framework], criptografía"
  - "valores de configuración del esquema"
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Esquema de la configuraci&#243;n de criptograf&#237;a
El esquema de configuración de criptografía contiene elementos que especifican cómo asignar nombres descriptivos de algoritmo a las clases que implementan los algoritmos de criptografía.  
  
 [\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<mscorlib\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [\<el cryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [\<cryptoClasses\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<cryptoClasses\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|Contiene una lista de clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento de **\<nameEntry\>** .|  
|[\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Contiene una clase criptográfica que tiene una asignación a un nombre descriptivo en el elemento de **\<nameEntry\>** .|  
|[\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|Este elemento contiene la configuración de criptografía.|  
|[\<el cryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Este elemento contiene las asignaciones de clases a nombres descriptivos.|  
|[\<mscorlibelement\>por valores de criptografía](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|Contiene el elemento de **\<cryptographySettings\>**.|  
|[\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|Asigna un nombre de clase a un nombre de algoritmo descriptivo y, de este modo, una clase puede tener varios nombres descriptivos.|  
|[\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Asigna un identificador de objeto \(OID\) en formato ASN.1 a un nombre descriptivo.|  
|[\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Contiene las asignaciones de identificadores de objetos \(OID\) en formato ASN.1 a clases.|  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Servicios criptográficos](../../../../../docs/standard/security/cryptographic-services.md)