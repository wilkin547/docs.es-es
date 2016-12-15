---
title: "Expresiones de consultas LINQ (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "Lenguaje C#, expresiones de consulta LINQ"
  - "expresiones [C#], expresiones de consulta LINQ"
  - "LINQ [C#], expresiones de consulta"
  - "consultas [LINQ en C#], expresiones de consulta"
  - "expresiones de consulta [LINQ en C#]"
ms.assetid: 40638f19-fb46-4d26-a2d9-a383b48f5ed4
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Expresiones de consultas LINQ (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] es el nombre de un conjunto de tecnologías que consiste en la integración directa de funciones de consulta en el lenguaje C\# \(también en Visual Basic y potencialmente en cualquier otro lenguaje de .NET\).  Con [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], ahora una consulta es una construcción de lenguaje de primera clase, igual que las clases, los métodos, los eventos, etc.  
  
 Para un programador que escribe consultas, la parte integrada en el lenguaje más visible de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] es la expresión de consulta.  Las expresiones de consulta se escriben en la *sintaxis de consulta* declarativa que se introdujo en C\# 3.0.  Al usar sintaxis de consulta, se pueden realizar incluso operaciones complejas de filtrado, ordenación y agrupamiento en orígenes de datos con código mínimo.  Los mismos patrones de expresión de consulta básicos se usan para consultar y transformar datos de bases de datos SQL, conjuntos de datos de [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)], secuencias y documentos XML, y colecciones de .NET.  
  
 En el siguiente ejemplo se muestra la operación de consulta completa.  La operación completa incluye la creación de un origen de datos, la definición de la expresión de consulta y la ejecución de la consulta en una instrucción `foreach`.  
  
 [!code-cs[csProgGuideLINQ#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
 Para obtener más información acerca de los fundamentos de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] en C\#, vea [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
## Información general sobre las expresiones de consulta  
  
-   Las expresiones de consulta se pueden utilizar para consultar y transformar los datos de cualquier origen de datos compatible con [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].  Por ejemplo, una misma consulta puede recuperar datos de una base de datos SQL y generar una secuencia XML como resultado.  
  
-   Las expresiones de consulta son fáciles de controlar porque utilizan muchas construcciones de lenguaje de C\# familiares.  Para obtener más información, consulte [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
-   Todas las variables de una expresión de consulta están fuertemente tipadas, aunque en muchos casos no es necesario proporcionar el tipo explícitamente porque el compilador puede deducirlo.  Para obtener más información, consulte [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
-   Una consulta no se ejecuta hasta que se recorre en iteración la variable de consulta en una instrucción `foreach`.  Para obtener más información, vea [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   En tiempo de compilación, las expresiones de consulta se convierten en llamadas a métodos de operador de consulta estándar de acuerdo con las reglas establecidas en la especificación de C\#.  Cualquier consulta que se puede expresar con sintaxis de consulta también se puede expresar con sintaxis de método.  Sin embargo, en la mayoría de los casos, la sintaxis de consulta es más legible y concisa.  Para obtener más información, consulte [Especificación del lenguaje C\#](../../../csharp/language-reference/language-specification.md) y [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
-   Como norma, cuando escriba consultas [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], recomendamos que siempre que sea posible utilice la sintaxis de consulta y que utilice la sintaxis de método sólo cuando sea necesario.  No existe ninguna diferencia semántica o de rendimiento entre las dos formas.  Las expresiones de consulta suelen ser más legibles que las expresiones equivalentes escritas con sintaxis de método.  
  
-   Algunas operaciones de consulta, como <xref:System.Linq.Enumerable.Count%2A> o <xref:System.Linq.Enumerable.Max%2A>, no tienen ninguna cláusula de expresión de consulta equivalente y, por tanto, deben expresarse como una llamada a método.  La sintaxis de método se puede combinar con la sintaxis de consulta de varias maneras.  Para obtener más información, consulte [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
-   Las expresiones de consulta pueden compilarse en árboles de expresión o en delegados, dependiendo del tipo al que se aplique la consulta.  Las consultas <xref:System.Collections.Generic.IEnumerable%601> se compilan en delegados.  Las consultas <xref:System.Linq.IQueryable> y <xref:System.Linq.IQueryable%601> se compilan en árboles de expresión.  Para obtener más información, consulte [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md).  
  
 En la tabla siguiente se enumeran los temas en los que se proporciona información adicional sobre las consultas y ejemplos de código para realizar tareas comunes.  
  
|Tema|Descripción|  
|----------|-----------------|  
|[Conceptos básicos de las expresiones de consultas](../../../csharp/programming-guide/linq-query-expressions/query-expression-basics.md)|Presenta conceptos fundamentales de las consultas y proporciona ejemplos de sintaxis de consulta de C\#.|  
|[Cómo: Escribir consultas con LINQ en C\#](../../../csharp/programming-guide/linq-query-expressions/how-to-write-linq-queries.md)|Proporciona ejemplos de varios tipos básicos de expresiones de consulta.|  
|[Cómo: Controlar excepciones en expresiones de consulta](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)|Explica cómo y cuándo se debe mover el código que pueda provocar excepciones fuera de una expresión de consulta.|  
|[How to: Populate Object Collections from Multiple Sources \(LINQ\)](../Topic/How%20to:%20Populate%20Object%20Collections%20from%20Multiple%20Sources%20\(LINQ\).md)|Explica cómo utilizar la instrucción `select` para combinar datos de orígenes diferentes en un nuevo tipo.|  
|[Cómo: Agrupar los resultados de consultas](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)|Muestra maneras diferentes de utilizar la cláusula `group`.|  
|[Cómo: Crear grupos anidados](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)|Muestra cómo crear grupos anidados.|  
|[Cómo: Realizar una subconsulta en una operación de agrupación](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)|Muestra cómo utilizar una subexpresión de una consulta como un origen de datos para una nueva consulta.|  
|[Cómo: Agrupar resultados por claves contiguas](../../../csharp/programming-guide/linq-query-expressions/how-to-group-results-by-contiguous-keys.md)|Muestra cómo implementar un operador de consulta estándar seguro para subprocesos que pueda realizar operaciones de agrupación en orígenes de datos de transmisión por secuencias.|  
|[Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)|Muestra cómo proporcionar un número arbitrario de valores para utilizarlo en comparaciones de igualdad en una cláusula `where`.|  
|[Cómo: Almacenar los resultados de una consulta en la memoria](../../../csharp/programming-guide/linq-query-expressions/how-to-store-the-results-of-a-query-in-memory.md)|Muestra cómo materializar y almacenar los resultados de consulta sin usar necesariamente un bucle `foreach`.|  
|[Cómo: Devolver una consulta de un método](../../../csharp/programming-guide/linq-query-expressions/how-to-return-a-query-from-a-method.md)|Muestra cómo devolver variables de consulta desde métodos y cómo pasarlas a métodos como parámetros de entrada.|  
|[Cómo: Realizar operaciones de combinación personalizadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)|Muestra cómo realizar operaciones de combinación basadas en cualquier tipo de función de predicado.|  
|[Cómo: Realizar una unión usando claves compuestas](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)|Muestra cómo combinar dos orígenes basándose en más de una clave coincidente.|  
|[Cómo: Ordenar los resultados de una cláusula join](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)|Muestra cómo ordenar una secuencia generada en una operación de combinación.|  
|[Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)|Muestra cómo realizar una combinación interna en [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].|  
|[Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)|Muestra cómo generar una combinación agrupada en [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].|  
|[Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)|Muestra cómo generar una combinación externa izquierda en [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].|  
|[Cómo: Controlar valores Null en expresiones de consultas](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-null-values-in-query-expressions.md)|Muestra cómo administrar los valores nulos en consultas de [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Walkthrough: Writing Queries in C\#](../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Basic LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)   
 [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [How Linq to Objects Queries Work](http://go.microsoft.com/fwlink/?LinkId=112389)   
 [Reading and Writing Queries](http://go.microsoft.com/fwlink/?LinkId=112391)   
 [What is a collection?](http://go.microsoft.com/fwlink/?LinkId=112394)   
 [Link to Everything: A List of LINQ Providers](http://go.microsoft.com/fwlink/?LinkId=112411)