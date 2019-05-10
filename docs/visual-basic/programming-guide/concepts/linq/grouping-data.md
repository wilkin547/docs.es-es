---
title: Agrupar datos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8f3a0871-6958-4aef-8f6f-493e189fd57d
ms.openlocfilehash: b5a6a3795e02e0638b81824701ad0cbacbcca91a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754464"
---
# <a name="grouping-data-visual-basic"></a><span data-ttu-id="a87a2-102">Agrupar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a87a2-102">Grouping Data (Visual Basic)</span></span>
<span data-ttu-id="a87a2-103">El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.</span><span class="sxs-lookup"><span data-stu-id="a87a2-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="a87a2-104">La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a87a2-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="a87a2-105">La clave de cada grupo es el carácter.</span><span class="sxs-lookup"><span data-stu-id="a87a2-105">The key for each group is the character.</span></span>  
  
 ![Diagrama que muestra una operación de agrupamiento de LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="a87a2-107">Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="a87a2-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a87a2-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="a87a2-108">Methods</span></span>  
  
|<span data-ttu-id="a87a2-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="a87a2-109">Method Name</span></span>|<span data-ttu-id="a87a2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a87a2-110">Description</span></span>|<span data-ttu-id="a87a2-111">Sintaxis de expresión de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a87a2-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="a87a2-112">Más información</span><span class="sxs-lookup"><span data-stu-id="a87a2-112">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="a87a2-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="a87a2-113">GroupBy</span></span>|<span data-ttu-id="a87a2-114">Agrupa los elementos que comparten un atributo común.</span><span class="sxs-lookup"><span data-stu-id="a87a2-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="a87a2-115">Cada grupo se representa mediante un objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="a87a2-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`Group … By … Into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="a87a2-116">ToLookup</span><span class="sxs-lookup"><span data-stu-id="a87a2-116">ToLookup</span></span>|<span data-ttu-id="a87a2-117">Inserta elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="a87a2-117">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="a87a2-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="a87a2-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="a87a2-119">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="a87a2-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="a87a2-120">El ejemplo de código siguiente usa la cláusula `Group By` para agrupar los enteros de una lista según sean pares o impares.</span><span class="sxs-lookup"><span data-stu-id="a87a2-120">The following code example uses the `Group By` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a87a2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a87a2-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="a87a2-122">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a87a2-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="a87a2-123">Group By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a87a2-123">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
- [<span data-ttu-id="a87a2-124">Cómo: Agrupar archivos por extensión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a87a2-124">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="a87a2-125">Cómo: Dividir un archivo en varios mediante el uso de grupos (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a87a2-125">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
