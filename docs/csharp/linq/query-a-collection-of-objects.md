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
# <a name="query-a-collection-of-objects"></a>Consultar una colección de objetos
En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`. Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones del alumno en cuatro exámenes.  
  
 Esta aplicación sirve de marco en muchos otros ejemplos de esta sección que usan el mismo origen de datos `students`.  
  
## <a name="example"></a>Ejemplo  
 La consulta siguiente devuelve los alumnos que reciben una puntuación de 90 o más en su primer examen.  
  
 [!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 Esta consulta es deliberadamente simple para permitirle experimentar. Por ejemplo, puede probar otras condiciones en la cláusula `where` o usar una cláusula `orderby` para ordenar los resultados.  
  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)

