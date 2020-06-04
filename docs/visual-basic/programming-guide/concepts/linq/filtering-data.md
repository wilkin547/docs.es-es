---
title: Filtrado de datos
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: f7a1aa76dc93cc03952e55f5f8fc3f75176a3f9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383422"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="1c35b-102">Filtrar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c35b-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="1c35b-103">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="1c35b-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="1c35b-104">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="1c35b-104">It is also known as selection.</span></span>

<span data-ttu-id="1c35b-105">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="1c35b-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="1c35b-106">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="1c35b-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="1c35b-108">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="1c35b-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="1c35b-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c35b-109">Methods</span></span>

|<span data-ttu-id="1c35b-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="1c35b-110">Method Name</span></span>|<span data-ttu-id="1c35b-111">Description</span><span class="sxs-lookup"><span data-stu-id="1c35b-111">Description</span></span>|<span data-ttu-id="1c35b-112">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="1c35b-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="1c35b-113">Más información</span><span class="sxs-lookup"><span data-stu-id="1c35b-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="1c35b-114">OfType</span><span class="sxs-lookup"><span data-stu-id="1c35b-114">OfType</span></span>|<span data-ttu-id="1c35b-115">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1c35b-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="1c35b-116">No disponible.</span><span class="sxs-lookup"><span data-stu-id="1c35b-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="1c35b-117">Where</span><span class="sxs-lookup"><span data-stu-id="1c35b-117">Where</span></span>|<span data-ttu-id="1c35b-118">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="1c35b-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="1c35b-119">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="1c35b-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="1c35b-120">En el ejemplo siguiente `Where` se utiliza para filtrar de una matriz las cadenas que tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="1c35b-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1c35b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c35b-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="1c35b-122">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c35b-122">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="1c35b-123">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="1c35b-123">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="1c35b-124">Cómo: Filtrar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="1c35b-124">How to: Filter Query Results</span></span>](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="1c35b-125">Cómo: consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c35b-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="1c35b-126">Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c35b-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="1c35b-127">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c35b-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
