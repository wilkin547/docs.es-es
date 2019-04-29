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
ms.openlocfilehash: e035ff04a70a441f7f64bbc230ba6d8036fb2ace
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775783"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="8c2b4-102">Asignar identificadores de objeto a algoritmos de criptografía</span><span class="sxs-lookup"><span data-stu-id="8c2b4-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="8c2b4-103">Aseguran de firmas digitales que datos no se manipule cuando se envían desde un programa a otro.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="8c2b4-104">Normalmente, la firma digital se calcula aplicando una función matemática con el hash de los datos que se firmarán.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="8c2b4-105">Al dar formato a un valor hash que se va a firmar, algunos algoritmos de firma digital anexar ASN.1 identificador del objeto (OID) como parte de la operación de formato.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="8c2b4-106">El OID identifica el algoritmo que se usó para calcular el hash.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="8c2b4-107">Puede asignar los algoritmos a los identificadores de objeto para extender el mecanismo de criptografía para usar algoritmos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="8c2b4-108">El ejemplo siguiente muestra cómo asignar un identificador de objeto a un nuevo algoritmo de hash.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="8c2b4-109">El [ \<oidEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contiene dos atributos.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="8c2b4-110">El **OID** atributo es el número de identificador de objeto.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="8c2b4-111">El **nombre** atributo es el valor de la **nombre** atributo desde el [ \<nameEntry > elemento](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="8c2b4-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="8c2b4-112">Debe haber una asignación de un nombre de algoritmo a una clase antes de que se puede asignar un identificador de objeto a un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="8c2b4-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c2b4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c2b4-113">See also</span></span>

- [<span data-ttu-id="8c2b4-114">Configurar clases de criptografía</span><span class="sxs-lookup"><span data-stu-id="8c2b4-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="8c2b4-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="8c2b4-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
