---
title: "Consultar una colección de objetos"
description: "Cómo se consultan colecciones."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e08f2e5877ffe24f5a238ab19abb9760cb442f2
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="168e9-104">Consultar una colección de objetos</span><span class="sxs-lookup"><span data-stu-id="168e9-104">Query a collection of objects</span></span>
<span data-ttu-id="168e9-105">En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="168e9-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="168e9-106">Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="168e9-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="168e9-107">Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.</span><span class="sxs-lookup"><span data-stu-id="168e9-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="168e9-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="168e9-108">Example</span></span>  
 <span data-ttu-id="168e9-109">La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.</span><span class="sxs-lookup"><span data-stu-id="168e9-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 <span data-ttu-id="168e9-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="168e9-110">[!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="168e9-111">Esta consulta es deliberadamente simple para permitirle experimentar.</span><span class="sxs-lookup"><span data-stu-id="168e9-111">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="168e9-112">Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="168e9-112">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="168e9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="168e9-113">See also</span></span>  
 [<span data-ttu-id="168e9-114">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="168e9-114">LINQ Query Expressions</span></span>](index.md)

