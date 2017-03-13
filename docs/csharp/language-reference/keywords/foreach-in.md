---
title: "foreach, in (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "foreach"
  - "foreach_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "foreach (palabra clave) [C#]"
  - "foreach (instrucción) [C#]"
  - "in (palabra clave) [C#]"
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# foreach, in (Referencia de C#)
La instrucción `foreach` repite un grupo de instrucciones incrustadas para cada elemento de una matriz o colección de objetos que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.  La instrucción `foreach` se utiliza para recorrer la colección en iteración y obtener la información deseada, pero no se puede utilizar para agregar o quitar elementos de la colección de origen, ya que se pueden producir efectos secundarios imprevisibles.  Si necesita agregar o quitar elementos de la colección de origen, utilice un bucle [for](../../../csharp/language-reference/keywords/for.md).  
  
 Las instrucciones del bucle siguen ejecutándose para cada elemento de la matriz o la colección.  Cuando ya se han recorrido todos los elementos de la colección, el control se transfiere a la siguiente instrucción fuera del bloque `foreach`.  
  
 En cualquier punto dentro del bloque `foreach`, puede salir del bucle utilizando la palabra clave [break](../../../csharp/language-reference/keywords/break.md) o pasando directamente a la iteración siguiente del bucle mediante la palabra clave [continue](../../../csharp/language-reference/keywords/continue.md).  
  
 También se puede salir de un bucle `foreach` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 Para obtener más información acerca de la palabra clave `foreach`, incluidos ejemplos de código, vea los temas siguientes:  
  
 [Utilizar foreach con matrices](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [Cómo: Obtener acceso a una clase de colección mediante Foreach](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## Ejemplo  
 El código siguiente muestra tres ejemplos:  
  
-   un bucle `foreach` típico que muestra el contenido de una matriz de enteros  
  
-   un bucle [for](../../../csharp/language-reference/keywords/for.md) que hace lo mismo  
  
-   un bucle `foreach` que mantiene el número de elementos de la matriz  
  
 [!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)   
 [for](../../../csharp/language-reference/keywords/for.md)