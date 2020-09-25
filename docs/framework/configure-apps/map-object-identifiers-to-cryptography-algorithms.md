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
ms.openlocfilehash: 5416ddbb766dfde56fa28a3853ed448cc73f25a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189388"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="af114-103">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="af114-103">Mapping Object Identifiers to Cryptography Algorithms</span></span>

<span data-ttu-id="af114-104">Las firmas digitales garantizan que no se manipulen los datos cuando se envían de un programa a otro.</span><span class="sxs-lookup"><span data-stu-id="af114-104">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="af114-105">Normalmente, la firma digital se calcula aplicando una función matemática al hash de los datos que se van a firmar.</span><span class="sxs-lookup"><span data-stu-id="af114-105">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="af114-106">Al dar formato a un valor hash que se va a firmar, algunos algoritmos de firma digital anexan un identificador de objeto (OID) ASN. 1 como parte de la operación de formato.</span><span class="sxs-lookup"><span data-stu-id="af114-106">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="af114-107">El OID identifica el algoritmo que se usó para calcular el hash.</span><span class="sxs-lookup"><span data-stu-id="af114-107">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="af114-108">Puede asignar algoritmos a identificadores de objeto para extender el mecanismo de criptografía para usar algoritmos personalizados.</span><span class="sxs-lookup"><span data-stu-id="af114-108">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="af114-109">En el ejemplo siguiente se muestra cómo asignar un identificador de objeto a un nuevo algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="af114-109">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="af114-110">El [ \<oidEntry> elemento](./file-schema/cryptography/oidentry-element.md) contiene dos atributos.</span><span class="sxs-lookup"><span data-stu-id="af114-110">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="af114-111">El atributo **OID** es el número del identificador de objeto.</span><span class="sxs-lookup"><span data-stu-id="af114-111">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="af114-112">El atributo **Name** es el valor del atributo **Name** del [ \<nameEntry> elemento](./file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="af114-112">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="af114-113">Debe haber una asignación desde un nombre de algoritmo a una clase antes de que un identificador de objeto pueda asignarse a un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="af114-113">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af114-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af114-114">See also</span></span>

- [<span data-ttu-id="af114-115">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="af114-115">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="af114-116">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="af114-116">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
