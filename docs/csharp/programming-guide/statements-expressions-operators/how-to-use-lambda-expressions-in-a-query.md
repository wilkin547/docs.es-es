---
title: "C&#243;mo: Usar expresiones lambda en una consulta (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "expresiones lambda [C#], en LINQ"
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# C&#243;mo: Usar expresiones lambda en una consulta (Gu&#237;a de programaci&#243;n de C#)
Las expresiones lambda no se utilizan directamente en sintaxis de consulta, sino que se utilizan en llamadas a métodos, y las expresiones de consulta pueden contener llamadas a métodos.  De hecho, algunas operaciones de consulta sólo se pueden expresar en sintaxis de método.  Para obtener más información sobre la diferencia entre la sintaxis de consulta y la sintaxis de método, vea [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar una expresión lambda en una consulta basada en método utilizando el operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>.  Observe que el método <xref:System.Linq.Enumerable.Where%2A> de este ejemplo tiene un parámetro de entrada del tipo delegado <xref:System.Func%601>, y ese delegado toma un entero como entrada y devuelve un booleano.  La expresión lambda se puede convertir a ese delegado.  Si ésta fuera una consulta de [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] que utilizara el método <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>, el tipo de parámetro sería `Expression<Func\<int,bool>>`, pero la expresión lambda presentaría exactamente el mismo aspecto.  Para obtener más información sobre el tipo de la expresión, vea <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#1)]  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar una expresión lambda en una llamada a método de una expresión de consulta.  La expresión lambda es necesaria porque el operador de consulta estándar <xref:System.Linq.Enumerable.Sum%2A> no se puede invocar utilizando sintaxis de consulta.  
  
 La consulta agrupa primero los alumnos según el curso, tal como se define en la enumeración `GradeLevel`.  A continuación, para cada grupo suma las puntuaciones totales para cada alumno.  Esto requiere dos operaciones `Sum`.  La operación `Sum` interna calcula la puntuación total para cada alumno, mientras que la operación `Sum` exterior mantiene un total combinado continuo para todos los alumnos del grupo.  
  
 [!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csrefLINQHowTos.cs#2)]  
  
## Compilar el código  
 Para ejecutar este código, copie y pegue el método en la clase `StudentClass` que se incluye en [Cómo: Consultar una colección de objetos](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) y llámelo desde el método `Main`.  
  
## Vea también  
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)