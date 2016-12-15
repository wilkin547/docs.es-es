---
title: "C&#243;mo: Ordenar los resultados de una cl&#225;usula join (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "join (cláusula) [C#]"
  - "combinaciones [C#], ordenar resultados"
  - "consultas [LINQ en C#], combinaciones"
  - "expresiones de consulta [LINQ en C#], combinaciones"
ms.assetid: 83f36f16-2ba3-453f-8b9f-7d02b415610e
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Ordenar los resultados de una cl&#225;usula join (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo muestra cómo ordenar los resultados de una operación de unión \(join\).  Observe que la ordenación se realiza después de la unión.  Aunque puede utilizar una cláusula `orderby` con una o más de las secuencias de origen antes de la unión, generalmente no es recomendable.  Algunos proveedores de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] podrían no conservar esa ordenación después de la unión.  
  
## Ejemplo  
 Esta consulta crea una unión de grupos y, a continuación, ordena los grupos según el elemento categoría, que todavía está dentro del ámbito.  Dentro del inicializador de tipo anónimo, una subconsulta ordena todos los elementos coincidentes de la secuencia de productos.  
  
 [!code-cs[csProgGuideLINQ#81](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-order-the-results-of-a-join-clause_1.cs)]  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [orderby \(cláusula\)](../../../csharp/language-reference/keywords/orderby-clause.md)   
 [join \(cláusula\)](../../../csharp/language-reference/keywords/join-clause.md)   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)