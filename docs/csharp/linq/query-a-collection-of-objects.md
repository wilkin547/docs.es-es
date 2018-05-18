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
---
# <a name="query-a-collection-of-objects"></a>Consultar una colección de objetos
En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`. Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.  
  
 Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.  
  
## <a name="example"></a>Ejemplo  
 La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 Esta consulta es deliberadamente simple para permitirle experimentar. Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.  
  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)  
 [Interpolación de cadenas](../language-reference/tokens/interpolated.md)
