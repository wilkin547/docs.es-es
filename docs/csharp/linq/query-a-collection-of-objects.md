---
title: Consultar una colección de objetos (LINQ en C#)
description: Obtenga información sobre cómo consultar colecciones mediante LINQ en C#.
ms.date: 11/30/2016
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: 87c7bbe789c165a6e189231df1979fc264a34dce
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403926"
---
# <a name="query-a-collection-of-objects"></a>Consultar una colección de objetos

En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`. Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.  
  
Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.  
  
## <a name="example"></a>Ejemplo

La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.  
  
[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
Esta consulta es deliberadamente simple para permitirle experimentar. Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.  
  
## <a name="see-also"></a>Vea también

[Language-Integrated Query (LINQ)](index.md)  
[Interpolación de cadenas](../language-reference/tokens/interpolated.md)