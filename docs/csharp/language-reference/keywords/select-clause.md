---
title: "select (Cl&#225;usula, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "select_CSharpKeyword"
  - "select"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Select (cláusula) [C#]"
  - "select (palabra clave) [C#]"
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# select (Cl&#225;usula, Referencia de C#)
En una expresión de consulta, la cláusula `select` especifica el tipo de valores que se generarán al ejecutar la consulta.  El resultado se basa en la evaluación de todas las cláusulas anteriores y de cualquier expresión en la propia cláusula `select`.  Una expresión de consulta debe finalizar con una cláusula `select` o una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md).  
  
 En el ejemplo siguiente se muestra una cláusula `select` simple en una expresión de consulta.  
  
 [!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Select.cs#8)]  
  
 El tipo de la secuencia generada por la cláusula `select` determina el tipo de la variable de consulta `queryHighScores`.  En el caso más sencillo, la cláusula `select` simplemente especifica la variable de rango.  Esto hace que la secuencia devuelta contenga elementos del mismo tipo que el origen de datos.  Para obtener más información, consulte [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  Sin embargo, la cláusula `select` también proporciona un mecanismo eficaz para transformar \(o *proyectar*\) datos de origen en nuevos tipos.  Para obtener más información, vea [Transformaciones de datos con LINQ \(C\#\)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestran las distintas formas que puede adoptar una cláusula `select`.  En cada consulta, observe la relación entre la cláusula `select` y el tipo de la *variable de consulta* \(`studentQuery1`, `studentQuery2`, etc.\).  
  
 [!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Select.cs#9)]  
  
 Como se muestra en `studentQuery8` en el ejemplo anterior, en ocasiones puede que desee que los elementos de la secuencia devuelta sólo contengan un subconjunto de las propiedades de los elementos de origen.  Si se mantiene la secuencia devuelta lo menor posible, puede reducir los requisitos de memoria y aumentar la velocidad de ejecución de la consulta.  Esto se puede lograr creando un tipo anónimo en la cláusula `select` y utilizando un inicializador de objeto para inicializarlo con las propiedades adecuadas del elemento de origen.  Para obtener un ejemplo sobre la forma de realizar esta operación, vea [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Comentarios  
 En tiempo de compilación, la cláusula `select` se convierte en una llamada a método para el operador de consulta estándar <xref:System.Linq.Enumerable.Select%2A>.  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from \(cláusula\)](../../../csharp/language-reference/keywords/from-clause.md)   
 [Método parcial \(Referencia de C\#\)](../../../csharp/language-reference/keywords/partial-method.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)