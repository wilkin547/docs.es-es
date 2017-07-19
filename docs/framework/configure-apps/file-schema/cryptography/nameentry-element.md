---
title: "Elemento &lt;nameEntry&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<nameEntry> (elemento)"
  - "nameEntry (elemento)"
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Elemento &lt;nameEntry&gt;
Asigna un nombre de clase a un nombre de algoritmo descriptivo y, de este modo, una clase puede tener varios nombres descriptivos.  
  
## Sintaxis  
  
```  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**nombre**|Atributo necesario.<br /><br /> Especifica el nombre descriptivo del algoritmo que implementa la clase de criptografía.|  
|**clase**|Atributo necesario.<br /><br /> Especifica el valor del atributo de **name** en el elemento de [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) .|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.web`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## Comentarios  
 El atributo **name** puede ser el nombre de una de las clases abstractas del espacio de nombres <xref:System.Security.Cryptography>.  Cuando se llama al método **Create** en una clase abstracta de criptografía, el nombre de la clase abstracta se pasa al método [Security.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic).  **CreateFromName** devuelve una instancia del tipo indicado en el atributo **class**.  Si el atributo **name** es un nombre corto, como RSA, se puede utilizar ese nombre al llamar al método **CreateFromName**.  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar el elemento de **\<nameEntry\>** para hacer referencia a una clase criptográfica y configurar el tiempo de ejecución.  A continuación, puede pasar la cadena "RSA" al método <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> y utilizar el método <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> para devolver un objeto `MyCryptoRSAClass`.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Esquema de la configuración de criptografía](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [Servicios criptográficos](../../../../../docs/standard/security/cryptographic-services.md)   
 [Configurar clases de criptografía](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)