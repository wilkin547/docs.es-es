---
title: Cómo determinar si un objeto de .NET Standard es serializable
description: Se muestra cómo determinar si un tipo de .NET Standard se puede serializar en tiempo de ejecución.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079895"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="88479-103">Cómo determinar si un objeto de .NET Standard es serializable</span><span class="sxs-lookup"><span data-stu-id="88479-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="88479-104">.NET Standard es una especificación que define los tipos y miembros que deben estar presentes en implementaciones específicas de .NET que cumplen con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="88479-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="88479-105">Sin embargo, .NET Standard no define si un tipo es serializable.</span><span class="sxs-lookup"><span data-stu-id="88479-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="88479-106">Los tipos definidos en la biblioteca .NET Standard no están marcados con el <xref:System.SerializableAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="88479-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="88479-107">En su lugar, las implementaciones de .NET concretas, como .NET Framework y .NET Core, son gratis determinar si un tipo determinado es serializable.</span><span class="sxs-lookup"><span data-stu-id="88479-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="88479-108">Si ha desarrollado una biblioteca que tiene como destino .NET Standard, la biblioteca puede usarse en cualquier implementación de .NET que admita .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="88479-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="88479-109">Esto significa que no se conoce de antemano si un tipo determinado es serializable; solo puede determinar si es serializable en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="88479-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="88479-110">Puede determinar si un objeto es serializable en tiempo de ejecución al recuperar el valor de la <xref:System.Type.IsSerializable> propiedad de un <xref:System.Type> objeto que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="88479-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="88479-111">El ejemplo siguiente proporciona una implementación.</span><span class="sxs-lookup"><span data-stu-id="88479-111">The following example provides one implementation.</span></span> <span data-ttu-id="88479-112">Define un `IsSerializable(Object)` método de extensión que indica si algún <xref:System.Object> se puede serializar la instancia.</span><span class="sxs-lookup"><span data-stu-id="88479-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="88479-113">A continuación, puede pasar cualquier objeto al método para determinar si se puede serializar y deserializar en la implementación actual. NET, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88479-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="88479-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="88479-114">See also</span></span>

- [<span data-ttu-id="88479-115">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="88479-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
