---
description: Más información acerca de la agrupación de datos (Visual Basic)
title: Agrupar datos
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: fa6dbcc22c7d991d48775c3974cfc529840ef933
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469804"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="c675f-103">Agrupar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c675f-103">Grouping Data (Visual Basic)</span></span>

<span data-ttu-id="c675f-104">El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.</span><span class="sxs-lookup"><span data-stu-id="c675f-104">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="c675f-105">La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c675f-105">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="c675f-106">La clave de cada grupo es el carácter.</span><span class="sxs-lookup"><span data-stu-id="c675f-106">The key for each group is the character.</span></span>  
  
 ![Diagrama que muestra una operación de agrupación de LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="c675f-108">Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="c675f-108">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c675f-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="c675f-109">Methods</span></span>  
  
|<span data-ttu-id="c675f-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="c675f-110">Method Name</span></span>|<span data-ttu-id="c675f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c675f-111">Description</span></span>|<span data-ttu-id="c675f-112">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="c675f-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="c675f-113">Más información</span><span class="sxs-lookup"><span data-stu-id="c675f-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="c675f-114">GroupBy</span><span class="sxs-lookup"><span data-stu-id="c675f-114">GroupBy</span></span>|<span data-ttu-id="c675f-115">Agrupa los elementos que comparten un atributo común.</span><span class="sxs-lookup"><span data-stu-id="c675f-115">Groups elements that share a common attribute.</span></span> <span data-ttu-id="c675f-116">Cada grupo se representa mediante un objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="c675f-116">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c675f-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="c675f-117">ToLookup</span></span>|<span data-ttu-id="c675f-118">Inserta elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="c675f-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="c675f-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="c675f-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="c675f-120">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="c675f-120">Query Expression Syntax Example</span></span>  

 <span data-ttu-id="c675f-121">El ejemplo de código siguiente usa la cláusula `Group By` para agrupar los enteros de una lista según sean pares o impares.</span><span class="sxs-lookup"><span data-stu-id="c675f-121">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```vb  
Dim numbers As New System.Collections.Generic.List(Of Integer)(  
     New Integer() {35, 44, 200, 84, 3987, 4, 199, 329, 446, 208})  
  
Dim query = From number In numbers
            Group By Remainder = (number Mod 2) Into Group  
  
Dim sb As New System.Text.StringBuilder()  
For Each group In query  
    sb.AppendLine(If(group.Remainder = 0, vbCrLf & "Even numbers:", vbCrLf & "Odd numbers:"))  
    For Each num In group.Group  
        sb.AppendLine(num)  
    Next  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' Odd numbers:  
' 35  
' 3987  
' 199  
' 329  
  
' Even numbers:  
' 44  
' 200  
' 84  
' 4  
' 446  
' 208  
```  
  
## <a name="see-also"></a><span data-ttu-id="c675f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c675f-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c675f-123">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c675f-123">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="c675f-124">Group by (cláusula)</span><span class="sxs-lookup"><span data-stu-id="c675f-124">Group By Clause</span></span>](../../../language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="c675f-125">Cómo: agrupar archivos por extensión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c675f-125">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="c675f-126">Cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c675f-126">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
