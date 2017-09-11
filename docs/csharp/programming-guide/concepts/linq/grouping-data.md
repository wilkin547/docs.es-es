---
title: Agrupar datos (C#)
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
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
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
ms.openlocfilehash: 2cf1b228a5ff4120bdf3b97a7ec9308f11d7b8ee
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="grouping-data-c"></a><span data-ttu-id="2aab5-102">Agrupar datos (C#)</span><span class="sxs-lookup"><span data-stu-id="2aab5-102">Grouping Data (C#)</span></span>
<span data-ttu-id="2aab5-103">El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.</span><span class="sxs-lookup"><span data-stu-id="2aab5-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="2aab5-104">La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2aab5-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="2aab5-105">La clave de cada grupo es el carácter.</span><span class="sxs-lookup"><span data-stu-id="2aab5-105">The key for each group is the character.</span></span>  
  
 <span data-ttu-id="2aab5-106">![Operaciones de agrupamiento en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span><span class="sxs-lookup"><span data-stu-id="2aab5-106">![LINQ Grouping Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_group.png "LINQ_Group")</span></span>  
  
 <span data-ttu-id="2aab5-107">Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="2aab5-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2aab5-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="2aab5-108">Methods</span></span>  
  
|<span data-ttu-id="2aab5-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="2aab5-109">Method Name</span></span>|<span data-ttu-id="2aab5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aab5-110">Description</span></span>|<span data-ttu-id="2aab5-111">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="2aab5-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="2aab5-112">Más información</span><span class="sxs-lookup"><span data-stu-id="2aab5-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="2aab5-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="2aab5-113">GroupBy</span></span>|<span data-ttu-id="2aab5-114">Agrupa los elementos que comparten un atributo común.</span><span class="sxs-lookup"><span data-stu-id="2aab5-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="2aab5-115">Cada grupo se representa mediante un objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="2aab5-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="2aab5-116">O bien</span><span class="sxs-lookup"><span data-stu-id="2aab5-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="2aab5-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="2aab5-117">ToLookup</span></span>|<span data-ttu-id="2aab5-118">Inserta elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="2aab5-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="2aab5-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="2aab5-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="2aab5-120">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="2aab5-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="2aab5-121">El ejemplo de código siguiente usa la cláusula `group by` para agrupar los enteros de una lista según sean pares o impares.</span><span class="sxs-lookup"><span data-stu-id="2aab5-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="2aab5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aab5-122">See Also</span></span>  
 <span data-ttu-id="2aab5-123"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="2aab5-123"><xref:System.Linq></span></span>   
 <span data-ttu-id="2aab5-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="2aab5-124">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="2aab5-125">[group (cláusula)](../../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2aab5-125">[group clause](../../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 <span data-ttu-id="2aab5-126">[Cómo: Crear grupos anidados](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md) </span><span class="sxs-lookup"><span data-stu-id="2aab5-126">[How to: Create a Nested Group](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md) </span></span>  
 <span data-ttu-id="2aab5-127">[Cómo: Agrupar archivos por extensión (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span><span class="sxs-lookup"><span data-stu-id="2aab5-127">[How to: Group Files by Extension (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md) </span></span>  
 <span data-ttu-id="2aab5-128">[Cómo: Agrupar los resultados de consultas](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md) </span><span class="sxs-lookup"><span data-stu-id="2aab5-128">[How to: Group Query Results](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md) </span></span>  
 <span data-ttu-id="2aab5-129">[Cómo: Realizar una subconsulta en una operación de agrupación](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md) </span><span class="sxs-lookup"><span data-stu-id="2aab5-129">[How to: Perform a Subquery on a Grouping Operation](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md) </span></span>  
 [<span data-ttu-id="2aab5-130">Cómo: Dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2aab5-130">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)

