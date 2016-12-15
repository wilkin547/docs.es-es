---
title: "C&#243;mo: Realizar una consulta en una colecci&#243;n de objetos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "consultas en colecciones de objetos [C#]"
  - "consultas [LINQ en C#], colecciones de objetos"
  - "expresiones de consulta [LINQ en C#], colecciones de objetos"
ms.assetid: 122d1e3b-1604-4add-b6b4-b84530a77b6b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Realizar una consulta en una colecci&#243;n de objetos (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En este ejemplo se muestra cómo realizar una consulta simple en una lista de objetos `Student`.  Cada objeto `Student` contiene información básica sobre el alumno y una lista que representa las puntuaciones de éste en cuatro exámenes.  
  
 Esta aplicación actúa como marco de trabajo de muchos otros ejemplos de esta sección que utilizan el mismo origen de datos `students` .  
  
## Ejemplo  
 La consulta siguiente devuelve los alumnos que obtuvieron una puntuación de 90 o más en su primer examen.  
  
 [!code-cs[csProgGuideLINQ#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-query-a-collection-of-objects_1.cs)]  
  
 Esta consulta es deliberadamente simple para permitirle experimentar.  Por ejemplo, puede probar más predicados en la cláusula `where` o utiliza una cláusula `orderby` para ordenar los resultados.  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)