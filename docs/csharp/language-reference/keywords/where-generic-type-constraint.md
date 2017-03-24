---
title: "where (restricci&#243;n de tipo gen&#233;rico) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "whereconstraint"
  - "whereconstraint_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where (restricción de tipo genérico) [C#]"
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# where (restricci&#243;n de tipo gen&#233;rico) (Referencia de C#)
En una definición de tipo genérico, la cláusula `where` se utiliza para especificar restricciones sobre los tipos que se pueden utilizar como argumentos para un parámetro de tipo definido en una declaración genérica.  Por ejemplo, puede declarar una clase genérica, `MyGenericClass`, de modo que el parámetro de tipo `T` implemente la interfaz <xref:System.IComparable%601>:  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!NOTE]
>  Para obtener más información sobre la cláusula where en una expresión de consulta, vea [where \(cláusula\)](../../../csharp/language-reference/keywords/where-clause.md).  
  
 Además de las restricciones de interfaz, una cláusula `where` puede incluir una restricción de clase base, que establece que un tipo debe tener la clase especificada como clase base \(o ser la propia clase\) para poder utilizarlo como argumento de tipo para ese tipo genérico.  Si se utiliza una restricción semejante, debe aparecer antes que cualquier otra restricción sobre ese parámetro de tipo.  
  
 [!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 La cláusula `where` también puede incluir una restricción de constructor.  Es posible crear una instancia de un parámetro de tipo utilizando el operador new; sin embargo, para ello el parámetro de tipo debe estar restringido por la restricción de constructor, `new()`.  La [restricción new\(\)](../../../csharp/language-reference/keywords/new-constraint.md) permite que el compilador sepa que cualquier argumento de tipo que se proporcione debe tener un constructor sin parámetros accesible, o predeterminado.  Por ejemplo:  
  
 [!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 La restricción `new()` aparece en último lugar en la cláusula `where`.  
  
 Con varios parámetros de tipo, utilice una cláusula `where` para cada parámetro de tipo, por ejemplo:  
  
 [!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 También puede adjuntar restricciones a parámetros de tipo de métodos genéricos, como el siguiente:  
  
```  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 Observe que la sintaxis para describir las restricciones de parámetros de tipo en delegados es igual que la sintaxis de métodos.  
  
```  
delegate T MyDelegate<T>() where T : new()  
```  
  
 Para obtener información sobre delegados genéricos, vea [Delegados genéricos \(Guía de programación de C\#\)](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
 Para obtener información detallada sobre la sintaxis y el uso de restricciones, vea [Restricciones de tipos de parámetros \(Guía de programación de C\#\)](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Restricción new](../../../csharp/language-reference/keywords/new-constraint.md)   
 [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)