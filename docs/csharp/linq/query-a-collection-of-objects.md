---
title: Consultar una colección de objetos
description: Cómo se consultan colecciones.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="query-a-collection-of-objects"></a><span data-ttu-id="a0476-104">Consultar una colección de objetos</span><span class="sxs-lookup"><span data-stu-id="a0476-104">Query a collection of objects</span></span>
<span data-ttu-id="a0476-105">En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.</span><span class="sxs-lookup"><span data-stu-id="a0476-105">This example shows how to perform a simple query over a list of `Student` objects.</span></span> <span data-ttu-id="a0476-106">Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.</span><span class="sxs-lookup"><span data-stu-id="a0476-106">Each `Student` object contains some basic information about the student, and a list that represents the student's scores on four examinations.</span></span>  
  
 <span data-ttu-id="a0476-107">Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.</span><span class="sxs-lookup"><span data-stu-id="a0476-107">This application serves as the framework for many other examples in this section that use the same `students` data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0476-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0476-108">Example</span></span>  
 <span data-ttu-id="a0476-109">La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.</span><span class="sxs-lookup"><span data-stu-id="a0476-109">The following query returns the students who received a score of 90 or greater on their first exam.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 <span data-ttu-id="a0476-110">Esta consulta es deliberadamente simple para permitirle experimentar.</span><span class="sxs-lookup"><span data-stu-id="a0476-110">This query is intentionally simple to enable you to experiment.</span></span> <span data-ttu-id="a0476-111">Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="a0476-111">For example, you can try more conditions in the `where` clause, or use an `orderby` clause to sort the results.</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="a0476-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0476-112">See also</span></span>  
 [<span data-ttu-id="a0476-113">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="a0476-113">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="a0476-114">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="a0476-114">String interpolation</span></span>](../language-reference/tokens/interpolated.md)
