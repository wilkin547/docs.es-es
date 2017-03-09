---
title: "where (Cl&#225;usula, Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "whereclause_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where (cláusula) [C#]"
  - "where (palabra clave) [C#]"
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# where (Cl&#225;usula, Referencia de C#)
La cláusula `where` se utiliza en una expresión de consulta para especificar qué elementos del origen de datos se devolverán en la expresión de consulta.  Aplica una condición Booleana \(*predicado*\) a cada elemento de origen \(al que se hace referencia mediante la variable de rango\) y devuelve aquéllos para los que la condición especificada es verdadera.  Una expresión de consulta única puede contener varias cláusulas `where`, y una cláusula única puede contener varias subexpresiones de predicado.  
  
## Ejemplo  
 En el ejemplo siguiente, la cláusula `where` deja fuera todos los números excepto aquéllos que son menores que cinco.  Si quita la cláusula `where`, se devolverían todos los números del origen de datos.  La expresión `num < 5` es el predicado que se aplica a cada elemento.  
  
 [!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Where.cs#5)]  
  
## Ejemplo  
 Dentro de una única cláusula `where` , puede especificar tantos predicados como sea necesario utilizando los operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md).  En el ejemplo siguiente, la consulta especifica dos predicados para seleccionar sólo los números pares menores que cinco.  
  
 [!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Where.cs#6)]  
  
## Ejemplo  
 Una cláusula `where` puede contener uno o más métodos que devuelven valores booleanos.  En el ejemplo siguiente, la cláusula `where` utiliza un método para determinar si el valor actual de la variable de rango es par o impar.  
  
 [!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/csharp/csquerykeywords/Where.cs#7)]  
  
## Comentarios  
 La cláusula `where` es un mecanismo de filtrado.  Se puede colocar prácticamente en cualquier parte en una expresión de consulta, pero no puede ser la primera o la última cláusula.  Una cláusula `where` puede aparecer antes o después de una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md) dependiendo de si tiene que filtrar los elementos de origen antes o después de agruparlos.  
  
 Si un predicado especificado no es válido para los elementos del origen de datos, se producirá un error en tiempo de compilación.  Ésta es una ventaja de la comprobación estricta de tipos que proporciona [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)].  
  
 En tiempo de compilación, la palabra clave `where` se convierte en una llamada a método para el operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A>.  
  
## Vea también  
 [Palabras clave para consultas \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [from \(cláusula\)](../../../csharp/language-reference/keywords/from-clause.md)   
 [select \(cláusula\)](../../../csharp/language-reference/keywords/select-clause.md)   
 [Filtering Data](../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Getting Started with LINQ in C\#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)