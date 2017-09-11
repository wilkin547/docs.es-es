---
title: Crear un grupo anidado
description: "Cómo crear un grupo anidado."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 361ac1f224c6eef292fcf8434c7e465c9448b19c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-nested-group"></a><span data-ttu-id="59209-104">Crear un grupo anidado</span><span class="sxs-lookup"><span data-stu-id="59209-104">Create a nested group</span></span>

<span data-ttu-id="59209-105">En el ejemplo siguiente se muestra cómo crear grupos anidados en una expresión de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="59209-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="59209-106">Cada grupo creado a partir del nivel académico o del año de los estudiantes se subdivide en grupos según sus nombres.</span><span class="sxs-lookup"><span data-stu-id="59209-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59209-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59209-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="59209-108">Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos).</span><span class="sxs-lookup"><span data-stu-id="59209-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 <span data-ttu-id="59209-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="59209-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span></span>  
  
 <span data-ttu-id="59209-110">Tenga en cuenta que se necesitan tres bucles `foreach` anidados para recorrer en iteración los elementos internos de un grupo anidado.</span><span class="sxs-lookup"><span data-stu-id="59209-110">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59209-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="59209-111">See also</span></span>  
 [<span data-ttu-id="59209-112">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="59209-112">LINQ Query Expressions</span></span>](index.md)

