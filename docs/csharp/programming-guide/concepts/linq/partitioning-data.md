---
title: Realizar particiones de datos (C#)
description: Aprenda a crear particiones de los datos en LINQ. Vea una ilustración que muestra los resultados de las operaciones de creación de particiones.
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 3c85eaec2dc01b683234a27714750354982be440
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302612"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="ed1c4-104">Realizar particiones de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="ed1c4-104">Partitioning Data (C#)</span></span>
<span data-ttu-id="ed1c4-105">Partición en LINQ es la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos, y devolver después una de las secciones.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-105">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="ed1c4-106">En la siguiente ilustración se muestran los resultados de tres operaciones de partición diferentes en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-106">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="ed1c4-107">La primera operación devuelve los tres primeros elementos de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-107">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="ed1c4-108">La segunda operación omite los tres primeros elementos y devuelve los restantes.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-108">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="ed1c4-109">La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres siguientes.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-109">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![Ilustración que muestra tres operaciones de creación de particiones de LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="ed1c4-111">Los métodos de operador de consulta estándar que realizan particiones de las secuencias se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-111">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="ed1c4-112">Operadores</span><span class="sxs-lookup"><span data-stu-id="ed1c4-112">Operators</span></span>  
  
|<span data-ttu-id="ed1c4-113">Nombre de operador</span><span class="sxs-lookup"><span data-stu-id="ed1c4-113">Operator Name</span></span>|<span data-ttu-id="ed1c4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed1c4-114">Description</span></span>|<span data-ttu-id="ed1c4-115">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="ed1c4-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="ed1c4-116">Más información</span><span class="sxs-lookup"><span data-stu-id="ed1c4-116">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ed1c4-117">Skip</span><span class="sxs-lookup"><span data-stu-id="ed1c4-117">Skip</span></span>|<span data-ttu-id="ed1c4-118">Omite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-118">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="ed1c4-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ed1c4-120">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="ed1c4-120">SkipWhile</span></span>|<span data-ttu-id="ed1c4-121">Omite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-121">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="ed1c4-122">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ed1c4-123">Take</span><span class="sxs-lookup"><span data-stu-id="ed1c4-123">Take</span></span>|<span data-ttu-id="ed1c4-124">Admite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-124">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="ed1c4-125">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ed1c4-126">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="ed1c4-126">TakeWhile</span></span>|<span data-ttu-id="ed1c4-127">Admite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-127">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="ed1c4-128">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="ed1c4-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="ed1c4-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed1c4-129">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ed1c4-130">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="ed1c4-130">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
