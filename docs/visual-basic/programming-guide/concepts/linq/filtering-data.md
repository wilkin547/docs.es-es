---
title: Filtrado de datos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: d3f44d0b6478103a10fb731988aeebc005cde82e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644347"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="99b10-102">Filtrado de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b10-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="99b10-103">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="99b10-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="99b10-104">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="99b10-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="99b10-105">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="99b10-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="99b10-106">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="99b10-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="99b10-107">![Operación de filtrado en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="99b10-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="99b10-108">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="99b10-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99b10-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="99b10-109">Methods</span></span>  
  
|<span data-ttu-id="99b10-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="99b10-110">Method Name</span></span>|<span data-ttu-id="99b10-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="99b10-111">Description</span></span>|<span data-ttu-id="99b10-112">Sintaxis de expresiones de consulta de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99b10-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="99b10-113">Más información</span><span class="sxs-lookup"><span data-stu-id="99b10-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="99b10-114">OfType</span><span class="sxs-lookup"><span data-stu-id="99b10-114">OfType</span></span>|<span data-ttu-id="99b10-115">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="99b10-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="99b10-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="99b10-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="99b10-117">Where</span><span class="sxs-lookup"><span data-stu-id="99b10-117">Where</span></span>|<span data-ttu-id="99b10-118">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="99b10-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="99b10-119">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="99b10-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="99b10-120">En el ejemplo siguiente se usa el `Where` filtrar a partir de una matriz las cadenas que tienen una longitud concreta.</span><span class="sxs-lookup"><span data-stu-id="99b10-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99b10-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="99b10-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="99b10-122">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b10-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="99b10-123">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="99b10-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="99b10-124">Cómo: Filtrar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="99b10-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)  
 [<span data-ttu-id="99b10-125">Cómo: consultar los metadatos de un ensamblado mediante la reflexión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b10-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="99b10-126">Cómo: buscar archivos con un atributo especificado o el nombre (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b10-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="99b10-127">Cómo: ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b10-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
