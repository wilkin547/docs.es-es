---
title: Filtrado de datos (C#)
description: El filtrado, también conocido como selección, restringe los resultados en función de una condición. Obtenga información sobre los métodos de operador de consulta estándar de LINQ en C# que realizan el filtrado.
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: f9f6d691da73b566e5135f6692c87ba3a8978005
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103929"
---
# <a name="filtering-data-c"></a><span data-ttu-id="54706-104">Filtrado de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="54706-104">Filtering Data (C#)</span></span>
<span data-ttu-id="54706-105">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="54706-105">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="54706-106">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="54706-106">It is also known as selection.</span></span>  
  
 <span data-ttu-id="54706-107">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="54706-107">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="54706-108">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="54706-108">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="54706-110">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="54706-110">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54706-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="54706-111">Methods</span></span>  
  
|<span data-ttu-id="54706-112">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="54706-112">Method Name</span></span>|<span data-ttu-id="54706-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="54706-113">Description</span></span>|<span data-ttu-id="54706-114">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="54706-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="54706-115">Más información</span><span class="sxs-lookup"><span data-stu-id="54706-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="54706-116">OfType</span><span class="sxs-lookup"><span data-stu-id="54706-116">OfType</span></span>|<span data-ttu-id="54706-117">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="54706-117">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="54706-118">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="54706-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="54706-119">Where</span><span class="sxs-lookup"><span data-stu-id="54706-119">Where</span></span>|<span data-ttu-id="54706-120">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="54706-120">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="54706-121">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="54706-121">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="54706-122">En el siguiente ejemplo se usa la cláusula `where` para filtrar de una matriz aquellas cadenas que tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="54706-122">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="54706-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54706-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="54706-124">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="54706-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="54706-125">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="54706-125">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="54706-126">Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="54706-126">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="54706-127">Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="54706-127">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="54706-128">Procedimiento para buscar archivos con un nombre o atributo especificados (C#)</span><span class="sxs-lookup"><span data-stu-id="54706-128">How to query for files with a specified attribute or name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="54706-129">Procedimiento para ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="54706-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
