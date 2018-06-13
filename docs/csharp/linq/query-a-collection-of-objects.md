---
title: Consultar una colección de objetos
description: Cómo se consultan colecciones.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: c690da2ae59d2a9b34a5bd403bc54797c4e95fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282397"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="bd8c5-103">Consultar una colección de objetos</span><span class="sxs-lookup"><span data-stu-id="bd8c5-103">Query a collection of objects</span></span>
<span data-ttu-id="bd8c5-104">En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="bd8c5-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="bd8c5-105">Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="bd8c5-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="bd8c5-106">Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.</span><span class="sxs-lookup"><span data-stu-id="bd8c5-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd8c5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd8c5-107">Example</span></span>  
 <span data-ttu-id="bd8c5-108">La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.</span><span class="sxs-lookup"><span data-stu-id="bd8c5-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="bd8c5-109">Esta consulta es deliberadamente simple para permitirle experimentar.</span><span class="sxs-lookup"><span data-stu-id="bd8c5-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="bd8c5-110">Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="bd8c5-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="bd8c5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd8c5-111">See also</span></span>  
 [<span data-ttu-id="bd8c5-112">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="bd8c5-112">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="bd8c5-113">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="bd8c5-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
