---
title: "Elemento &lt;cryptoClass&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptoClass> (elemento)"
  - "cryptoClass (elemento)"
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Elemento &lt;cryptoClass&gt;
Contiene una clase criptográfica que tiene una asignación a un nombre descriptivo en el elemento de [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) .  
  
## Sintaxis  
  
```  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`customClassName`|Atributo necesario.<br /><br /> Contiene la información de la clase de criptografía.  Utilice este atributo para proporcionar un nombre corto para la clase.  Debe especificar una cadena que cumpla los requisitos especificados en [Especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`cryptoClasses`|Contiene una lista de clases de criptografía que tienen una asignación a un nombre descriptivo en el elemento de [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) .|  
|`cryptographySettings`|Este elemento contiene la configuración de criptografía.|  
|`cryptoNameMapping`|Este elemento contiene las asignaciones de clases a nombres descriptivos.|  
|`mscorlib`|Contiene el elemento de [\<cryptographySettings\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) .|  
  
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