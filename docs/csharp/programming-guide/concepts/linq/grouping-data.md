---
title: Agrupar datos (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: 7ef3d3c9097d7a9478605565518ac8975feb9fe2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635748"
---
# <a name="grouping-data-c"></a><span data-ttu-id="043b2-102">Agrupar datos (C#)</span><span class="sxs-lookup"><span data-stu-id="043b2-102">Grouping Data (C#)</span></span>
<span data-ttu-id="043b2-103">El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.</span><span class="sxs-lookup"><span data-stu-id="043b2-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="043b2-104">La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="043b2-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="043b2-105">La clave de cada grupo es el carácter.</span><span class="sxs-lookup"><span data-stu-id="043b2-105">The key for each group is the character.</span></span>  
  
 ![Diagrama que muestra una operación de agrupación de LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="043b2-107">Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="043b2-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="043b2-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="043b2-108">Methods</span></span>  
  
|<span data-ttu-id="043b2-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="043b2-109">Method Name</span></span>|<span data-ttu-id="043b2-110">Description</span><span class="sxs-lookup"><span data-stu-id="043b2-110">Description</span></span>|<span data-ttu-id="043b2-111">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="043b2-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="043b2-112">Más información</span><span class="sxs-lookup"><span data-stu-id="043b2-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="043b2-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="043b2-113">GroupBy</span></span>|<span data-ttu-id="043b2-114">Agrupa los elementos que comparten un atributo común.</span><span class="sxs-lookup"><span data-stu-id="043b2-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="043b2-115">Cada grupo se representa mediante un objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="043b2-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="043b2-116">o bien</span><span class="sxs-lookup"><span data-stu-id="043b2-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="043b2-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="043b2-117">ToLookup</span></span>|<span data-ttu-id="043b2-118">Inserta elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="043b2-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="043b2-119">No disponible.</span><span class="sxs-lookup"><span data-stu-id="043b2-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="043b2-120">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="043b2-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="043b2-121">El ejemplo de código siguiente usa la cláusula `group by` para agrupar los enteros de una lista según sean pares o impares.</span><span class="sxs-lookup"><span data-stu-id="043b2-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="043b2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="043b2-122">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="043b2-123">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="043b2-123">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="043b2-124">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="043b2-124">group clause</span></span>](../../../language-reference/keywords/group-clause.md)
- [<span data-ttu-id="043b2-125">Crear grupos anidados</span><span class="sxs-lookup"><span data-stu-id="043b2-125">Create a nested group</span></span>](../../../linq/create-a-nested-group.md)
- [<span data-ttu-id="043b2-126">Procedimiento para agrupar archivos por extensión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="043b2-126">How to group files by extension (LINQ) (C#)</span></span>](./how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="043b2-127">Agrupar los resultados de consultas</span><span class="sxs-lookup"><span data-stu-id="043b2-127">Group query results</span></span>](../../../linq/group-query-results.md)
- [<span data-ttu-id="043b2-128">Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="043b2-128">Perform a subquery on a grouping operation</span></span>](../../../linq/perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="043b2-129">Procedimiento para dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="043b2-129">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
