---
title: Asignar identificadores de objeto a algoritmos de criptografía
description: Vea cómo asignar un identificador de objeto (OID) a un algoritmo de criptografía en .NET mediante los elementos oidEntry y elemento nameEntry en un archivo de configuración XML.
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: e22510014071455b83ba28cd82690b5ecdce9bc9
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142009"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Asignar identificadores de objeto a algoritmos de criptografía
Las firmas digitales garantizan que no se manipulen los datos cuando se envían de un programa a otro. Normalmente, la firma digital se calcula aplicando una función matemática al hash de los datos que se van a firmar. Al dar formato a un valor hash que se va a firmar, algunos algoritmos de firma digital anexan un identificador de objeto (OID) ASN. 1 como parte de la operación de formato. El OID identifica el algoritmo que se usó para calcular el hash. Puede asignar algoritmos a identificadores de objeto para extender el mecanismo de criptografía para usar algoritmos personalizados. En el ejemplo siguiente se muestra cómo asignar un identificador de objeto a un nuevo algoritmo hash.  
  
```xml  
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
  
 El [ \<oidEntry> elemento](./file-schema/cryptography/oidentry-element.md) contiene dos atributos. El atributo **OID** es el número del identificador de objeto. El atributo **Name** es el valor del atributo **Name** del [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md). Debe haber una asignación desde un nombre de algoritmo a una clase antes de que un identificador de objeto pueda asignarse a un nombre simple.  
  
## <a name="see-also"></a>Consulte también:

- [Configurar clases de criptografía](configure-cryptography-classes.md)
- [Servicios criptográficos](../../standard/security/cryptographic-services.md)
