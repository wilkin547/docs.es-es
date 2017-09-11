---
title: Realizar particiones de datos (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2f1690dac93d5e74f1305bd457f8bc749bec5449
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="partitioning-data-c"></a><span data-ttu-id="e0efc-102">Realizar particiones de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="e0efc-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="e0efc-103">Partición en LINQ es la operación de dividir una secuencia de entrada en dos secciones, sin reorganizar los elementos, y devolver después una de las secciones.</span><span class="sxs-lookup"><span data-stu-id="e0efc-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="e0efc-104">En la siguiente ilustración se muestran los resultados de tres operaciones de partición diferentes en una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e0efc-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="e0efc-105">La primera operación devuelve los tres primeros elementos de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="e0efc-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="e0efc-106">La segunda operación omite los tres primeros elementos y devuelve los restantes.</span><span class="sxs-lookup"><span data-stu-id="e0efc-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="e0efc-107">La tercera operación omite los dos primeros elementos de la secuencia y devuelve los tres siguientes.</span><span class="sxs-lookup"><span data-stu-id="e0efc-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="e0efc-108">![Operaciones de partición en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="e0efc-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="e0efc-109">Los métodos de operador de consulta estándar que realizan particiones de las secuencias se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0efc-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="e0efc-110">Operadores</span><span class="sxs-lookup"><span data-stu-id="e0efc-110">Operators</span></span>  
  
|<span data-ttu-id="e0efc-111">Nombre de operador</span><span class="sxs-lookup"><span data-stu-id="e0efc-111">Operator Name</span></span>|<span data-ttu-id="e0efc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0efc-112">Description</span></span>|<span data-ttu-id="e0efc-113">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="e0efc-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="e0efc-114">Más información</span><span class="sxs-lookup"><span data-stu-id="e0efc-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="e0efc-115">Skip</span><span class="sxs-lookup"><span data-stu-id="e0efc-115">Skip</span></span>|<span data-ttu-id="e0efc-116">Omite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="e0efc-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="e0efc-117">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0efc-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName>|  
|<span data-ttu-id="e0efc-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="e0efc-118">SkipWhile</span></span>|<span data-ttu-id="e0efc-119">Omite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="e0efc-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="e0efc-120">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0efc-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName>|  
|<span data-ttu-id="e0efc-121">Take</span><span class="sxs-lookup"><span data-stu-id="e0efc-121">Take</span></span>|<span data-ttu-id="e0efc-122">Admite los elementos hasta una determinada posición de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="e0efc-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="e0efc-123">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0efc-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=fullName>|  
|<span data-ttu-id="e0efc-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="e0efc-124">TakeWhile</span></span>|<span data-ttu-id="e0efc-125">Admite los elementos según una función de predicado hasta que un elemento no satisface la condición.</span><span class="sxs-lookup"><span data-stu-id="e0efc-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="e0efc-126">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="e0efc-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="e0efc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0efc-127">See Also</span></span>  
 <span data-ttu-id="e0efc-128"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="e0efc-128"><xref:System.Linq></span></span>   
 <span data-ttu-id="e0efc-129">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="e0efc-129">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>

