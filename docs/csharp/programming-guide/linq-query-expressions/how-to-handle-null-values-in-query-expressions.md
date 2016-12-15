---
title: "C&#243;mo: Controlar valores Null en expresiones de consultas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "valores null [LINQ en C#]"
  - "consultas [LINQ en C#], valores nulos"
  - "expresiones de consulta [LINQ en C#], valores nulos"
ms.assetid: cb34f7a1-7ef5-466a-90ba-91da30ab525d
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Controlar valores Null en expresiones de consultas (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Este ejemplo muestra cómo tratar los posibles valores nulos \(null\) en colecciones de origen.  Una colección de objetos tal como un <xref:System.Collections.Generic.IEnumerable%601> puede contener elementos cuyo valor es [null](../../../csharp/language-reference/keywords/null.md).  Si una colección de origen es nula o contiene algún elemento cuyo valor es nulo, y la consulta no controla los valores nulos, se iniciará una excepción <xref:System.NullReferenceException> al ejecutar la consulta.  
  
## Ejemplo  
 Puede escribir el código adecuado para evitar una excepción de referencia nula como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideLINQ#82](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 En el ejemplo anterior, la cláusula `where` deja fuera del filtro todos los elementos nulos de la secuencia de categorías.  Esta técnica es independiente de la comprobación de valores nulos de la cláusula join.  La expresión condicional con null de este ejemplo funciona porque `Products.CategoryID` es de tipo `int?`, que es una forma abreviada de `Nullable<int>`.  
  
## Ejemplo  
 En una cláusula join, si sólo una de las claves de comparación es de un tipo de valor que acepta valores null, puede convertir el otro a un tipo que acepte valores null en la expresión de consulta.  En el ejemplo siguiente, suponga que `EmployeeID` es una columna que contiene valores de tipo `int?`:  
  
 [!code-cs[csProgGuideLINQ#83](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## Vea también  
 <xref:System.Nullable%601>   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)