---
title: "Cómo: determinar si un objeto .NET estándar es serializable"
description: "Muestra cómo determinar si se puede serializar un tipo de .NET estándar en tiempo de ejecución."
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0460fe27228fb9e17bde2d10652164707cd47a8b
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="96258-103">Cómo: determinar si un objeto .NET estándar es serializable</span><span class="sxs-lookup"><span data-stu-id="96258-103">How to: Determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="96258-104">El estándar de .NET es una especificación que define los tipos y miembros que deben estar presentes en las implementaciones específicas de .NET que se ajustan a esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="96258-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="96258-105">Sin embargo, el estándar de .NET no define si un tipo es serializable.</span><span class="sxs-lookup"><span data-stu-id="96258-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="96258-106">Los tipos definidos en la biblioteca estándar de .NET no están marcados con el <xref:System.SerializableAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="96258-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="96258-107">En su lugar, las implementaciones específicas. NET, como .NET Framework y .NET Core, son gratuitas determinar si un tipo determinado es serializable.</span><span class="sxs-lookup"><span data-stu-id="96258-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="96258-108">Si ha desarrollado una biblioteca que tiene como destino .NET Standard, la biblioteca se puede utilizar en cualquier implementación de .NET que admita el estándar. NET.</span><span class="sxs-lookup"><span data-stu-id="96258-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="96258-109">Esto significa que no se conoce de antemano si un tipo determinado es serializable; solo puede determinar si es serializable en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="96258-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="96258-110">Puede determinar si un objeto es serializable en tiempo de ejecución al recuperar el valor de la <xref:System.Type.IsSerializable> propiedad de un <xref:System.Type> objeto que representa el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="96258-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="96258-111">En el ejemplo siguiente se proporciona una implementación.</span><span class="sxs-lookup"><span data-stu-id="96258-111">The following example provides one implementation.</span></span> <span data-ttu-id="96258-112">Define un `IsSerializable(Object)` método de extensión que indica si alguno <xref:System.Object> se puede serializar la instancia.</span><span class="sxs-lookup"><span data-stu-id="96258-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="96258-113">A continuación, puede pasar cualquier objeto al método para determinar si se puede serializar y deserializar en la implementación actual. NET, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96258-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a><span data-ttu-id="96258-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="96258-114">See also</span></span>

<span data-ttu-id="96258-115">[Serialización binaria](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="96258-115">[Binary serialization](binary-serialization.md) </span></span>  
<span data-ttu-id="96258-116"><xref:System.SerializableAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="96258-116"><xref:System.SerializableAttribute?displayProperty=fullName></span></span>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
