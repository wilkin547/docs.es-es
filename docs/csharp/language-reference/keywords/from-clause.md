---
title: "from (Cl&#225;usula, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "from_CSharpKeyword"
  - "from"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "from (cláusula) [C#]"
  - "from (palabra clave) [C#]"
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# from (Cl&#225;usula, Referencia de C#)
Una expresión de consulta debe comenzar con una cláusula `from`.  Además, una expresión de consulta puede contener subconsultas, que también comienzan con una cláusula `from`.  La cláusula `from` especifica lo siguiente:  
  
-   El origen de datos en el que se ejecutará la consulta o subconsulta.  
  
-   Una *variable de rango* local que representa cada elemento en la secuencia de origen.  
  
 La variable de rango y el origen de datos están fuertemente tipados.  El origen de datos al que se hace referencia en la cláusula `from` debe tener un tipo <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> o un tipo derivado, como <xref:System.Linq.IQueryable%601>.  
  
 En el ejemplo siguiente, `numbers` es el origen de datos y `num` es la variable de rango.  Observe que ambas variables están fuertemente tipadas aunque se use la palabra clave [var](../../../csharp/language-reference/keywords/var.md).  
  
 [!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_1.cs)]  
  
## Variable de rango \(Range\)  
 El compilador deduce el tipo de la variable de rango cuando el origen de datos implementa <xref:System.Collections.Generic.IEnumerable%601>.  Por ejemplo, si el origen tiene un tipo `IEnumerable<Customer>`, se deduce que la variable de rango es `Customer`.  La única ocasión en que se debe especificar explícitamente el tipo es cuando el origen es un tipo `IEnumerable` no genérico, como <xref:System.Collections.ArrayList>.  Para obtener más información, vea [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md).  
  
 En el ejemplo anterior, se deduce que `num` es de tipo `int`.  Dado que la variable de rango está fuertemente tipada, se puede llamar a métodos en ella o usar en otras operaciones.  Por ejemplo, en lugar de escribir `select num`, podría escribir `select num.ToString()` para hacer que la expresión de consulta devuelva una secuencia de cadenas en lugar de enteros.  También podría escribir `select n + 10` para hacer que la expresión devuelva la secuencia 14, 11, 13, 12, 10.  Para obtener más información, vea [select \(cláusula\)](../../../csharp/language-reference/keywords/select-clause.md).  
  
 La variable de rango es como una variable de iteración en una instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md), salvo por una diferencia muy importante: una variable de rango nunca almacena realmente los datos del origen.  Es simplemente una comodidad sintáctica que permite a la consulta describir lo que ocurrirá cuando se ejecute.  Para obtener más información, vea [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
## Cláusulas From compuestas  
 En algunos casos, cada elemento de la secuencia de origen puede ser en sí mismo una secuencia o contenerla.  Por ejemplo, el origen de datos puede ser un `IEnumerable<Student>`, donde cada objeto de estudiante de la secuencia contiene una lista de puntuaciones de exámenes.  Para tener acceso a la lista interna de cada elemento `Student`, puede utilizar cláusulas `from` compuestas.  La técnica es como utilizar instrucciones [foreach](../../../csharp/language-reference/keywords/foreach-in.md) anidadas.  Puede agregar cláusulas [where](../../../csharp/language-reference/keywords/partial-method.md) u [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) a cualquier cláusula `from` para filtrar los resultados.  En el ejemplo siguiente se muestra una secuencia de objetos `Student`, cada uno de los cuales contiene un objeto `List` interno de enteros que representan las puntuaciones de los exámenes.  Para tener acceso a la lista interna, utilice una cláusula `from` compuesta.  Puede insertar cláusulas entre las dos cláusulas `from` si es necesario.  
  
 [!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_2.cs)]  
  
## Utilizar varias cláusulas From para realizar combinaciones  
 Para tener acceso a las colecciones internas de un origen de datos único, se utiliza una cláusula `from` compuesta.  Sin embargo, una consulta también puede contener varias cláusulas `from` que generen consultas complementarias de orígenes de datos independientes.  Esta técnica permite realizar ciertos tipos de operaciones de combinación que no son posibles con la [cláusula Join](../../../csharp/language-reference/keywords/join-clause.md).  
  
 En el ejemplo siguiente se muestra cómo usar dos cláusulas `from` para formar una combinación cruzada completa de dos orígenes de datos.  
  
 [!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/from-clause_3.cs)]  
  
 Para obtener más información sobre las operaciones de combinación que utilizan varias cláusulas `from`, vea [Cómo: Realizar operaciones de combinación personalizadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## Vea también  
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)