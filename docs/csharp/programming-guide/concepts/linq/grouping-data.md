---
title: Agrupar datos (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: e7f10b121a7a1c599d88731a806fe784eb1a7e66
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423418"
---
# <a name="grouping-data-c"></a><span data-ttu-id="da6af-102">Agrupar datos (C#)</span><span class="sxs-lookup"><span data-stu-id="da6af-102">Grouping Data (C#)</span></span>
<span data-ttu-id="da6af-103">El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.</span><span class="sxs-lookup"><span data-stu-id="da6af-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="da6af-104">La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="da6af-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="da6af-105">La clave de cada grupo es el carácter.</span><span class="sxs-lookup"><span data-stu-id="da6af-105">The key for each group is the character.</span></span>  
  
 ![Diagrama que muestra una operación de agrupación de LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="da6af-107">Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="da6af-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da6af-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="da6af-108">Methods</span></span>  
  
|<span data-ttu-id="da6af-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="da6af-109">Method Name</span></span>|<span data-ttu-id="da6af-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da6af-110">Description</span></span>|<span data-ttu-id="da6af-111">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="da6af-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="da6af-112">Más información</span><span class="sxs-lookup"><span data-stu-id="da6af-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="da6af-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="da6af-113">GroupBy</span></span>|<span data-ttu-id="da6af-114">Agrupa los elementos que comparten un atributo común.</span><span class="sxs-lookup"><span data-stu-id="da6af-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="da6af-115">Cada grupo se representa mediante un objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="da6af-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="da6af-116">O bien</span><span class="sxs-lookup"><span data-stu-id="da6af-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="da6af-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="da6af-117">ToLookup</span></span>|<span data-ttu-id="da6af-118">Inserta elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="da6af-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="da6af-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="da6af-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="da6af-120">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="da6af-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="da6af-121">El ejemplo de código siguiente usa la cláusula `group by` para agrupar los enteros de una lista según sean pares o impares.</span><span class="sxs-lookup"><span data-stu-id="da6af-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da6af-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="da6af-122">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="da6af-123">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="da6af-123">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="da6af-124">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="da6af-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="da6af-125">Cómo: Crear un grupo anidado</span><span class="sxs-lookup"><span data-stu-id="da6af-125">How to: Create a Nested Group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="da6af-126">Cómo: Agrupar archivos por extensión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="da6af-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="da6af-127">Cómo: Agrupar los resultados de consultas</span><span class="sxs-lookup"><span data-stu-id="da6af-127">How to: Group Query Results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="da6af-128">Cómo: Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="da6af-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="da6af-129">Cómo: Dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="da6af-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
