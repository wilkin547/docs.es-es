---
title: Cómo determinar si un objeto .NET Standard es serializable
description: Muestra cómo determinar si un tipo de .NET Standard se puede serializar en tiempo de ejecución.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159902"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="93984-103">Cómo determinar si un objeto .NET Standard es serializable</span><span class="sxs-lookup"><span data-stu-id="93984-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="93984-104">El .NET Standard es una especificación que define los tipos y miembros que deben estar presentes en implementaciones de .NET específicas que se ajusten a esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="93984-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="93984-105">Sin embargo, el .NET Standard no define si un tipo es serializable.</span><span class="sxs-lookup"><span data-stu-id="93984-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="93984-106">Los tipos definidos en la biblioteca .NET Standard no están marcados con el atributo <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="93984-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="93984-107">En su lugar, las implementaciones de .NET específicas, como la .NET Framework y .NET Core, son gratuitas para determinar si un tipo determinado es serializable.</span><span class="sxs-lookup"><span data-stu-id="93984-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="93984-108">Si ha desarrollado una biblioteca que tiene como destino el .NET Standard, la biblioteca puede utilizarla cualquier implementación de .NET que admita la .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="93984-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="93984-109">Esto significa que no puede saber de antemano si un tipo determinado es serializable; solo puede determinar si es serializable en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="93984-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="93984-110">Puede determinar si un objeto es serializable en tiempo de ejecución recuperando el valor de la propiedad <xref:System.Type.IsSerializable> de un objeto <xref:System.Type> que representa el tipo de ese objeto.</span><span class="sxs-lookup"><span data-stu-id="93984-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="93984-111">En el ejemplo siguiente se proporciona una implementación de.</span><span class="sxs-lookup"><span data-stu-id="93984-111">The following example provides one implementation.</span></span> <span data-ttu-id="93984-112">Define un método de extensión `IsSerializable(Object)` que indica si se puede serializar cualquier instancia de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="93984-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="93984-113">Después, puede pasar cualquier objeto al método para determinar si se puede serializar y deserializar en la implementación actual de .NET, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="93984-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="93984-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="93984-114">See also</span></span>

- [<span data-ttu-id="93984-115">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="93984-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
