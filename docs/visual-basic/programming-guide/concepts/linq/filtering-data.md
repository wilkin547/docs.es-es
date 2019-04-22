---
title: Filtrado de datos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: a673126d928a97bf522783e73fc254debe2a9de8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837452"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="3237f-102">Filtrado de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3237f-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="3237f-103">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="3237f-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="3237f-104">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="3237f-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="3237f-105">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="3237f-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="3237f-106">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="3237f-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="3237f-108">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3237f-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3237f-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="3237f-109">Methods</span></span>  
  
|<span data-ttu-id="3237f-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="3237f-110">Method Name</span></span>|<span data-ttu-id="3237f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3237f-111">Description</span></span>|<span data-ttu-id="3237f-112">Sintaxis de expresión de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3237f-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3237f-113">Más información</span><span class="sxs-lookup"><span data-stu-id="3237f-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="3237f-114">OfType</span><span class="sxs-lookup"><span data-stu-id="3237f-114">OfType</span></span>|<span data-ttu-id="3237f-115">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="3237f-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="3237f-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="3237f-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3237f-117">Where</span><span class="sxs-lookup"><span data-stu-id="3237f-117">Where</span></span>|<span data-ttu-id="3237f-118">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="3237f-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="3237f-119">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="3237f-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="3237f-120">En el ejemplo siguiente se usa el `Where` filtrar a partir de una matriz aquellas cadenas que tienen una longitud concreta.</span><span class="sxs-lookup"><span data-stu-id="3237f-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a><span data-ttu-id="3237f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3237f-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3237f-122">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3237f-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="3237f-123">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="3237f-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="3237f-124">Cómo: Filtrar los resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="3237f-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="3237f-125">Cómo: Consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3237f-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="3237f-126">Cómo: Buscar archivos con un atributo especificado o el nombre (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3237f-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="3237f-127">Cómo: Ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3237f-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
