---
title: Asignar identificadores de objeto a algoritmos de criptografía
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7801c55cf6b3334347788013d9052038d5d2f3ec
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756623"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Asignar identificadores de objeto a algoritmos de criptografía
Las firmas digitales garantizan que los datos no se manipulación con cuando se envía desde un programa a otro. Normalmente, la firma digital se calcula aplicando una función matemática al hash de los datos debe estar firmado. Al dar formato a un valor hash que se va a firmar, algunos algoritmos de firma digital anexar ASN.1 identificador del objeto (OID) como parte de la operación de formato. El OID identifica el algoritmo que se usó para calcular el hash. Puede asignar algoritmos a identificadores de objeto para extender el mecanismo de criptografía para usar algoritmos personalizados. En el ejemplo siguiente se muestra cómo asignar un identificador de objeto a un nuevo algoritmo de hash.  
  
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
  
 El [ \<oidEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contiene dos atributos. El **OID** atributo es el número de identificador de objeto. El **nombre** atributo es el valor de la **nombre** de atributo de la [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md). Debe haber una asignación de un nombre de algoritmo a una clase antes de que se puede asignar un identificador de objeto a un nombre simple.  
  
## <a name="see-also"></a>Vea también  
 [Configurar clases de criptografía](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
