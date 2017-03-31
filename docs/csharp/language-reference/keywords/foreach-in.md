---
title: foreach, in (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- foreach
- foreach_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aa5408dbe214af2c21edd394f74fb8b675f2a099
ms.lasthandoff: 03/13/2017

---
# <a name="foreach-in-c-reference"></a>foreach, in (Referencia de C#)
La instrucción `foreach` repite un grupo de instrucciones incrustadas para cada elemento de una matriz o una colección de objetos que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>. La instrucción `foreach` se usa para recorrer en iteración la colección para obtener la información deseada, pero no puede usarse para agregar o quitar elementos de la colección de origen para evitar efectos secundarios imprevisibles. Si se necesitan agregar o quitar elementos de la colección de origen, se usa un bucle [for](../../../csharp/language-reference/keywords/for.md).  
  
 Las instrucciones incrustadas continúan ejecutándose para cada elemento de la matriz o la colección. Cuando la iteración se completa en todos los elementos de la colección, el control se transfiere a la instrucción que sigue al bloque `foreach`.  
  
 En cualquier punto del bloque `foreach`, se puede salir del bucle mediante la palabra clave [break](../../../csharp/language-reference/keywords/break.md), o bien se puede ir a la siguiente iteración del bucle mediante la palabra clave [continue](../../../csharp/language-reference/keywords/continue.md).  
  
 También se puede salir de un bucle `foreach` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 Para más información sobre la palabra clave `foreach` y obtener ejemplos de código, vea los temas siguientes:  
  
 [Utilizar foreach con matrices](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
 [Cómo: Obtener acceso a una clase de colección mediante Foreach](../../../csharp/programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente, se muestran tres ejemplos:  
  
-   un bucle `foreach` típico que muestra el contenido de una matriz de enteros  
  
-   un bucle [for](../../../csharp/language-reference/keywords/for.md) que hace lo mismo  
  
-   un bucle `foreach` que mantiene un recuento del número de elementos de la matriz  
  
 [!code-cs[csrefKeywordsIteration#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/foreach-in_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Iteration Statements](../../../csharp/language-reference/keywords/iteration-statements.md)  (Instrucciones de iteración)  
 [for](../../../csharp/language-reference/keywords/for.md)
