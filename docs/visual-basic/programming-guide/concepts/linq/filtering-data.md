---
description: Más información acerca de cómo filtrar datos (Visual Basic)
title: Filtrado de datos
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 2e259209df35a89eb4730f79ffccfee7cb64b9e9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428602"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="2287d-103">Filtrar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2287d-103">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="2287d-104">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="2287d-104">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="2287d-105">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="2287d-105">It is also known as selection.</span></span>

<span data-ttu-id="2287d-106">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2287d-106">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="2287d-107">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="2287d-107">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="2287d-109">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="2287d-109">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="2287d-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="2287d-110">Methods</span></span>

|<span data-ttu-id="2287d-111">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="2287d-111">Method Name</span></span>|<span data-ttu-id="2287d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2287d-112">Description</span></span>|<span data-ttu-id="2287d-113">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="2287d-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="2287d-114">Más información</span><span class="sxs-lookup"><span data-stu-id="2287d-114">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="2287d-115">OfType</span><span class="sxs-lookup"><span data-stu-id="2287d-115">OfType</span></span>|<span data-ttu-id="2287d-116">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="2287d-116">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="2287d-117">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="2287d-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2287d-118">Where</span><span class="sxs-lookup"><span data-stu-id="2287d-118">Where</span></span>|<span data-ttu-id="2287d-119">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="2287d-119">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="2287d-120">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="2287d-120">Query Expression Syntax Example</span></span>

<span data-ttu-id="2287d-121">En el ejemplo siguiente `Where` se utiliza para filtrar de una matriz las cadenas que tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="2287d-121">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2287d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2287d-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="2287d-123">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2287d-123">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="2287d-124">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="2287d-124">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="2287d-125">Cómo: Filtrar los resultados de una consulta</span><span class="sxs-lookup"><span data-stu-id="2287d-125">How to: Filter Query Results</span></span>](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="2287d-126">Cómo: consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2287d-126">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="2287d-127">Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2287d-127">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="2287d-128">Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2287d-128">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
