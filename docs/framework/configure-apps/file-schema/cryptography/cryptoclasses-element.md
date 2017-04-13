---
title: "Elemento &lt;cryptoClasses&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptoClasses> (elemento)"
  - "cryptoClasses (elemento)"
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Elemento &lt;cryptoClasses&gt;
Contiene una lista de clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento de [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) .  
  
## Sintaxis  
  
```  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Contiene una clase criptográfica que tiene una asignación a un nombre descriptivo en el elemento de **\<nameEntry\>** .|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`cryptographySettings`|Este elemento contiene la configuración de criptografía.|  
|`cryptoNameMapping`|Este elemento contiene las asignaciones de clases a nombres descriptivos.|  
|`mscorlib`|Contiene el elemento `cryptographySettings`.|  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar el elemento de **\<cryptoClass\>** de hacer referencia a una clase criptográfica y configurar el tiempo de ejecución.  A continuación, puede pasar la cadena "RSA" al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> y utilizar el método <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> para devolver un objeto `MyCryptoRSAClass`.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Security.Cryptography>   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Esquema de la configuración de criptografía](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Servicios criptográficos](../../../../../docs/standard/security/cryptographic-services.md)   
 [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic)   
 [Configurar clases de criptografía](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)