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
ms.openlocfilehash: a5aebac2d392d4540581dfe7c7afff0819968ac0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912541"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="aa2ad-102">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="aa2ad-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="aa2ad-103">Las firmas digitales garantizan que no se manipulen los datos cuando se envían de un programa a otro.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="aa2ad-104">Normalmente, la firma digital se calcula aplicando una función matemática al hash de los datos que se van a firmar.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="aa2ad-105">Al dar formato a un valor hash que se va a firmar, algunos algoritmos de firma digital anexan un identificador de objeto (OID) ASN. 1 como parte de la operación de formato.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="aa2ad-106">El OID identifica el algoritmo que se usó para calcular el hash.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="aa2ad-107">Puede asignar algoritmos a identificadores de objeto para extender el mecanismo de criptografía para usar algoritmos personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="aa2ad-108">En el ejemplo siguiente se muestra cómo asignar un identificador de objeto a un nuevo algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="aa2ad-109">El [ \<oidEntry> elemento](./file-schema/cryptography/oidentry-element.md) contiene dos atributos.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-109">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="aa2ad-110">El atributo **OID** es el número del identificador de objeto.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="aa2ad-111">El atributo **Name** es el valor del atributo **Name** del [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="aa2ad-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="aa2ad-112">Debe haber una asignación desde un nombre de algoritmo a una clase antes de que un identificador de objeto pueda asignarse a un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="aa2ad-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2ad-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa2ad-113">See also</span></span>

- [<span data-ttu-id="aa2ad-114">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="aa2ad-114">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="aa2ad-115">Servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="aa2ad-115">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
