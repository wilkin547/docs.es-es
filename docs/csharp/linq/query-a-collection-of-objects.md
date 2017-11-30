---
title: "Consultar una colección de objetos"
description: "Cómo se consultan colecciones."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 74d6c1f080c3e70867f5d2f074315bd1d8486bf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="21da7-104">Consultar una colección de objetos</span><span class="sxs-lookup"><span data-stu-id="21da7-104">Query a collection of objects</span></span>
<span data-ttu-id="21da7-105">En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="21da7-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="21da7-106">Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="21da7-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="21da7-107">Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.</span><span class="sxs-lookup"><span data-stu-id="21da7-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21da7-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21da7-108">Example</span></span>  
 <span data-ttu-id="21da7-109">La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.</span><span class="sxs-lookup"><span data-stu-id="21da7-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="21da7-110">Esta consulta es deliberadamente simple para permitirle experimentar.</span><span class="sxs-lookup"><span data-stu-id="21da7-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="21da7-111">Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="21da7-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="21da7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="21da7-112">See also</span></span>  
 [<span data-ttu-id="21da7-113">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="21da7-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="21da7-114">Cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="21da7-114">Interpolated Strings</span></span>](../language-reference/keywords/interpolated-strings.md)
