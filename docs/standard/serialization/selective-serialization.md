---
title: Serialización selectiva
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: cc5d7964d5f3268f08721593fefc07e3eff853ca
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159603"
---
# <a name="selective-serialization"></a><span data-ttu-id="6927a-102">Serialización selectiva</span><span class="sxs-lookup"><span data-stu-id="6927a-102">Selective serialization</span></span>
<span data-ttu-id="6927a-103">Una clase a menudo contiene campos que no se deberían serializar.</span><span class="sxs-lookup"><span data-stu-id="6927a-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="6927a-104">Por ejemplo, suponga que una clase almacena un Identificador de subproceso en una variable miembro.</span><span class="sxs-lookup"><span data-stu-id="6927a-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="6927a-105">Al deserializar la clase, es posible que el subproceso que ha almacenado el identificador al serializar la clase ya no se esté ejecutando; así, serializar este valor no tiene sentido.</span><span class="sxs-lookup"><span data-stu-id="6927a-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="6927a-106">Puede evitar que las variables miembro se serialicen si las marca con el atributo [NonSerialized](xref:System.NonSerializedAttribute) como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="6927a-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="6927a-107">Si es posible, haz que un objeto pueda contener datos seguros no serializables.</span><span class="sxs-lookup"><span data-stu-id="6927a-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="6927a-108">Si se debe serializar el objeto, aplique el atributo `NonSerialized` a campos concretos que almacenen datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="6927a-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="6927a-109">Si no excluye estos campos de la serialización, sea consciente de que los datos que almacenan se exponen a cualquier código que tenga permiso para serializar.</span><span class="sxs-lookup"><span data-stu-id="6927a-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="6927a-110">Para más información sobre cómo escribir código de serialización seguro, vea [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="6927a-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="6927a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6927a-111">See also</span></span>

- [<span data-ttu-id="6927a-112">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="6927a-112">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="6927a-113">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="6927a-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="6927a-114">Seguridad y serialización</span><span class="sxs-lookup"><span data-stu-id="6927a-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)
