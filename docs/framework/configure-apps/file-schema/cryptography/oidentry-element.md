---
title: "Elemento &lt;oidEntry&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidEntry> (elemento)"
  - "oidEntry (elemento)"
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Elemento &lt;oidEntry&gt;
Asigna un identificador de objeto \(OID\) en formato ASN.1 a un nombre descriptivo.  
  
## Sintaxis  
  
```  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**OID**|Atributo necesario.<br /><br /> Especifica el identificador de objeto \(OID\) en formato ASN.1 correspondiente al algoritmo implementado por la clase.|  
|**nombre**|Atributo necesario.<br /><br /> Especifica el valor del atributo de **name** en la etiqueta de [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) .|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`cryptographySettings`|Este elemento contiene la configuración de criptografía.|  
|`mscorlib`|Contiene el elemento `cryptographySettings`.|  
|`oidMap`|Este elemento contiene las asignaciones de identificadores de objetos \(OID\) a clases en formato ASN.1.|  
  
## Comentarios  
 Los identificadores de objetos en formato ASN.1 identifican algoritmos en algunos formatos criptográficos.  Asigne identificadores de objetos a los nombres descriptivos de los algoritmos que desee identificar.  Para obtener más información sobre identificadores de objetos, vea MSDN Library.  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar el elemento de **\<oidEntry\>** para asignar un identificador de objeto para el algoritmo hash RIPEMD\-160 a una implementación del algoritmo hash.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
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
 [Configurar clases de criptografía](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Asignar identificadores de objeto a algoritmos de criptografía](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)