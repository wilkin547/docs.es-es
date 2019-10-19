---
title: Filtrar datos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 27765247daa2155e685b1cd2bfccebb3216ca672
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582435"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="ca23e-102">Filtrar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca23e-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="ca23e-103">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="ca23e-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="ca23e-104">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="ca23e-104">It is also known as selection.</span></span>

<span data-ttu-id="ca23e-105">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ca23e-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="ca23e-106">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="ca23e-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="ca23e-108">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca23e-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="ca23e-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="ca23e-109">Methods</span></span>

|<span data-ttu-id="ca23e-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="ca23e-110">Method Name</span></span>|<span data-ttu-id="ca23e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca23e-111">Description</span></span>|<span data-ttu-id="ca23e-112">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="ca23e-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="ca23e-113">Más información</span><span class="sxs-lookup"><span data-stu-id="ca23e-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="ca23e-114">OfType</span><span class="sxs-lookup"><span data-stu-id="ca23e-114">OfType</span></span>|<span data-ttu-id="ca23e-115">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ca23e-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="ca23e-116">No disponible.</span><span class="sxs-lookup"><span data-stu-id="ca23e-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="ca23e-117">Where</span><span class="sxs-lookup"><span data-stu-id="ca23e-117">Where</span></span>|<span data-ttu-id="ca23e-118">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="ca23e-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="ca23e-119">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="ca23e-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="ca23e-120">En el ejemplo siguiente se usa el `Where` para filtrar de una matriz las cadenas que tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="ca23e-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ca23e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca23e-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ca23e-122">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca23e-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="ca23e-123">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ca23e-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="ca23e-124">Cómo: Filtrar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="ca23e-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="ca23e-125">Cómo: consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca23e-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="ca23e-126">Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca23e-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="ca23e-127">Cómo: ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca23e-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
