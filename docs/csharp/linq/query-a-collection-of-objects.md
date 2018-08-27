---
title: Consultar una colección de objetos (LINQ en C#)
description: Obtenga información sobre cómo consultar colecciones mediante LINQ en C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 7bc59e7009f9ae8d8f66c24e9519d9100404c9c4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935546"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="e311d-103">Consultar una colección de objetos</span><span class="sxs-lookup"><span data-stu-id="e311d-103">Query a collection of objects</span></span>

<span data-ttu-id="e311d-104">En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="e311d-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="e311d-105">Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="e311d-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="e311d-106">Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.</span><span class="sxs-lookup"><span data-stu-id="e311d-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e311d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e311d-107">Example</span></span>

<span data-ttu-id="e311d-108">La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.</span><span class="sxs-lookup"><span data-stu-id="e311d-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="e311d-109">Esta consulta es deliberadamente simple para permitirle experimentar.</span><span class="sxs-lookup"><span data-stu-id="e311d-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="e311d-110">Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="e311d-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e311d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e311d-111">See also</span></span>

- [<span data-ttu-id="e311d-112">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="e311d-112">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="e311d-113">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="e311d-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)