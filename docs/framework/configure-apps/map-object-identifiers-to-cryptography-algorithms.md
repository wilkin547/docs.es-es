---
title: "Asignar identificadores de objeto a algoritmos de criptograf&#237;a | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "algoritmos criptográficos"
  - "criptografía, asignar identificadores de objetos"
  - "firmas digitales"
  - "identificadores, asignar identificadores de objetos"
  - "asignar identificadores de objetos"
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Asignar identificadores de objeto a algoritmos de criptograf&#237;a
Las firmas digitales garantizan que los datos no se han manipulado cuando se envían de un programa a otro.  Normalmente, la firma digital se calcula aplicando una función matemática al hash de los datos que se van a firmar.  Al dar formato a un valor hash que se va a firmar, algunos algoritmos de firma digital agregan un Identificador de objeto \(OID\) ASN.1 como parte de la operación de formato.  El OID identifica el algoritmo que se utilizó para calcular el hash.  Se puede asignar algoritmos a identificadores de objetos para extender el mecanismo de criptografía y que utilice algoritmos personalizados.  En el ejemplo siguiente se describe cómo se asigna un identificador de objeto a un nuevo algoritmo de hash.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 [\<oidEntry\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contiene dos atributos.  El atributo **OID** es el número del identificador de objeto.  El atributo de **name** es el valor del atributo de **name** de [\<nameEntry\> elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).  Debe haber una asignación de un nombre de algoritmo a una clase para poder asignar un identificador de objeto a un nombre sencillo.  
  
## Vea también  
 [Configurar clases de criptografía](../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Servicios criptográficos](../../../docs/standard/security/cryptographic-services.md)