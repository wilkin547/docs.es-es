---
title: Filtrado de datos (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: 61d80674fd858063e77749342a33d714e3a57c6e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826072"
---
# <a name="filtering-data-c"></a><span data-ttu-id="75a14-102">Filtrado de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="75a14-102">Filtering Data (C#)</span></span>
<span data-ttu-id="75a14-103">El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada.</span><span class="sxs-lookup"><span data-stu-id="75a14-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="75a14-104">También se conoce como selección.</span><span class="sxs-lookup"><span data-stu-id="75a14-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="75a14-105">En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="75a14-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="75a14-106">El predicado de la operación de filtrado especifica que el carácter debe ser "A".</span><span class="sxs-lookup"><span data-stu-id="75a14-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="75a14-108">Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="75a14-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75a14-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="75a14-109">Methods</span></span>  
  
|<span data-ttu-id="75a14-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="75a14-110">Method Name</span></span>|<span data-ttu-id="75a14-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="75a14-111">Description</span></span>|<span data-ttu-id="75a14-112">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="75a14-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="75a14-113">Más información</span><span class="sxs-lookup"><span data-stu-id="75a14-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="75a14-114">OfType</span><span class="sxs-lookup"><span data-stu-id="75a14-114">OfType</span></span>|<span data-ttu-id="75a14-115">Selecciona valores en función de su capacidad para convertirse en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="75a14-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="75a14-116">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="75a14-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="75a14-117">Where</span><span class="sxs-lookup"><span data-stu-id="75a14-117">Where</span></span>|<span data-ttu-id="75a14-118">Selecciona valores basados en una función de predicado.</span><span class="sxs-lookup"><span data-stu-id="75a14-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="75a14-119">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="75a14-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="75a14-120">En el siguiente ejemplo se usa la cláusula `where` para filtrar de una matriz aquellas cadenas que tienen una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="75a14-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75a14-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="75a14-121">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="75a14-122">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="75a14-122">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="75a14-123">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="75a14-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)
- [<span data-ttu-id="75a14-124">Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="75a14-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="75a14-125">Cómo: Consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="75a14-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="75a14-126">Cómo: Buscar archivos con un nombre o atributo especificados (C#)</span><span class="sxs-lookup"><span data-stu-id="75a14-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="75a14-127">Cómo: Ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="75a14-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
