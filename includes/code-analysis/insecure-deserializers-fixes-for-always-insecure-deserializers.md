---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: cf944ae9ca200d34a1f0f32e68bf3aee73a9500a
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592139"
---
- <span data-ttu-id="149a5-101">Si es posible, use un serializador seguro en su lugar y **no permita que un atacante especifique un tipo arbitrario para deserializar**.</span><span class="sxs-lookup"><span data-stu-id="149a5-101">If possible, use a secure serializer instead, and **don't allow an attacker to specify an arbitrary type to deserialize**.</span></span> <span data-ttu-id="149a5-102">Algunos serializadores más seguros incluyen:</span><span class="sxs-lookup"><span data-stu-id="149a5-102">Some safer serializers include:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="149a5-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> : No usar nunca <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="149a5-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> - Never use <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>.</span></span> <span data-ttu-id="149a5-104">Si debe usar un solucionador de tipos, restrinja los tipos deserializados a una lista de espera.</span><span class="sxs-lookup"><span data-stu-id="149a5-104">If you must use a type resolver, restrict deserialized types to an expected list.</span></span>
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="149a5-105">Newtonsoft Json.NET: Use TypeNameHandling. None.</span><span class="sxs-lookup"><span data-stu-id="149a5-105">Newtonsoft Json.NET - Use TypeNameHandling.None.</span></span> <span data-ttu-id="149a5-106">Si debe usar otro valor para TypeNameHandling, restrinja los tipos deserializados a una lista de espera con un ISerializationBinder personalizado.</span><span class="sxs-lookup"><span data-stu-id="149a5-106">If you must use another value for TypeNameHandling, restrict deserialized types to an expected list with a custom ISerializationBinder.</span></span>
  - <span data-ttu-id="149a5-107">Búferes de protocolo</span><span class="sxs-lookup"><span data-stu-id="149a5-107">Protocol Buffers</span></span>

- <span data-ttu-id="149a5-108">Convierta la prueba de alteración de los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="149a5-108">Make the serialized data tamper-proof.</span></span> <span data-ttu-id="149a5-109">Después de la serialización, firme criptográficamente los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="149a5-109">After serialization, cryptographically sign the serialized data.</span></span> <span data-ttu-id="149a5-110">Antes de la deserialización, valide la firma criptográfica.</span><span class="sxs-lookup"><span data-stu-id="149a5-110">Before deserialization, validate the cryptographic signature.</span></span> <span data-ttu-id="149a5-111">Proteja la clave criptográfica para que no se revele y diseñe las rotaciones de clave.</span><span class="sxs-lookup"><span data-stu-id="149a5-111">Protect the cryptographic key from being disclosed and design for key rotations.</span></span>
