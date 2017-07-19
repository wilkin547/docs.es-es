---
title: "Elemento &lt;cryptographySettings&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptographySettings> (elemento)"
  - "cryptographySettings (elemento)"
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Elemento &lt;cryptographySettings&gt;
Este elemento contiene la configuración de criptografía.  
  
## Sintaxis  
  
```  
  
      <cryptographySettings>   
</crytopgraphySettings>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<el cryptoNameMapping\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Este elemento contiene las asignaciones de clases a nombres descriptivos.|  
|[\<oidMap\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Este elemento contiene las asignaciones de identificadores de objetos \(OID\) a clases en formato ASN.1.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`mscorlib`|Contiene el elemento `cryptographySettings`.|  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar el elemento de **\<cryptographySettings\>** de contener asignaciones de nombre de criptografía y asignaciones de OID.  En este ejemplo se configura el tiempo de ejecución para que [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic) devuelva un objeto `MyHashClass` y la clase `MyCryptoClass` se asigne al identificador de objetos 1.3.36.2.1.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Esquema de la configuración de criptografía](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Servicios criptográficos](../../../../../docs/standard/security/cryptographic-services.md)