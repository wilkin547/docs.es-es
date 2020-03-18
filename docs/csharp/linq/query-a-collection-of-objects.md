---
title: Consultar una colección de objetos (LINQ en C#)
description: Obtenga información sobre cómo consultar colecciones mediante LINQ en C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 9b2f5dd09c540800e9a2498d48883357f58c0116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659818"
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="1aa42-103">Consultar una colección de objetos</span><span class="sxs-lookup"><span data-stu-id="1aa42-103">Query a collection of objects</span></span>

<span data-ttu-id="1aa42-104">En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="1aa42-104">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="1aa42-105">Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="1aa42-105">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
<span data-ttu-id="1aa42-106">Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.</span><span class="sxs-lookup"><span data-stu-id="1aa42-106">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa42-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1aa42-107">Example</span></span>

<span data-ttu-id="1aa42-108">La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.</span><span class="sxs-lookup"><span data-stu-id="1aa42-108">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
<span data-ttu-id="1aa42-109">Esta consulta es deliberadamente simple para permitirle experimentar.</span><span class="sxs-lookup"><span data-stu-id="1aa42-109">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="1aa42-110">Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="1aa42-110">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa42-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aa42-111">See also</span></span>

- [<span data-ttu-id="1aa42-112">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="1aa42-112">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="1aa42-113">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="1aa42-113">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
