---
title: Crear un grupo anidado (LINQ en C#)
description: Obtenga información sobre cómo crear un grupo anidado en una expresión de consulta LINQ en C#.
ms.date: 12/1/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: c973048d0859f61596c62c294131b8c00d0039f8
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404754"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="cc941-103">Crear un grupo anidado</span><span class="sxs-lookup"><span data-stu-id="cc941-103">Create a nested group</span></span>

<span data-ttu-id="cc941-104">En el ejemplo siguiente se muestra cómo crear grupos anidados en una expresión de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="cc941-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="cc941-105">Cada grupo creado a partir del nivel académico o del año de los estudiantes se subdivide en grupos según sus nombres.</span><span class="sxs-lookup"><span data-stu-id="cc941-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>

## <a name="example"></a><span data-ttu-id="cc941-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc941-106">Example</span></span>

> [!NOTE]
> <span data-ttu-id="cc941-107">Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos).</span><span class="sxs-lookup"><span data-stu-id="cc941-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

<span data-ttu-id="cc941-108">Tenga en cuenta que se necesitan tres bucles `foreach` anidados para recorrer en iteración los elementos internos de un grupo anidado.</span><span class="sxs-lookup"><span data-stu-id="cc941-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc941-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc941-109">See also</span></span>

[<span data-ttu-id="cc941-110">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cc941-110">Language Integrated Query (LINQ)</span></span>](index.md)
