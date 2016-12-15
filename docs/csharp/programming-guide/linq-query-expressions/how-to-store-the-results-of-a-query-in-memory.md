---
title: "C&#243;mo: Almacenar los resultados de una consulta en la memoria (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
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
  - "almacenamiento de resultados de consultas [LINQ en C#]"
  - "expresiones de consulta [LINQ en C#], almacenamiento de resultados"
ms.assetid: 7271597f-3523-4f7b-b088-1eeffe913b2d
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Almacenar los resultados de una consulta en la memoria (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una consulta es básicamente un conjunto de instrucciones sobre cómo recuperar y organizar datos.  Para ejecutarse, la consulta requiere una llamada a su método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.  Esta llamada se realiza al utilizar un bucle `foreach` para procesar una iteración en los elementos.  Para evaluar una consulta y almacenar los resultados sin ejecutar un bucle de `foreach`, simplemente llame a uno de los métodos siguientes en la variable de consulta:  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 Cuando almacene los resultados de la consulta, se recomienda que asigne el objeto de colección devuelto a una nueva variable, como se muestra en el ejemplo siguiente:  
  
## Ejemplo  
 [!code-cs[csProgGuideLINQ#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  
## Compilar el código  
  
-   Cree un proyecto de [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] para la versión 3.5 de .NET Framework.  De manera predeterminada, el proyecto incluye una referencia a System.Core.dll y una directiva `using` para el espacio de nombres System.Linq.  
  
-   Copie el código en el proyecto.  
  
-   Presione F5 para compilar y ejecutar el programa.  
  
-   Presione cualquier tecla para salir de la ventana de consola.  
  
## Vea también  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)