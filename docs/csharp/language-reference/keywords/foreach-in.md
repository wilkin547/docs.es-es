---
title: foreach, in (Referencia de C#)
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: f00ae873e615f653d3e760f82b157a57fdaef6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="foreach-in-c-reference"></a>foreach, in (Referencia de C#)
La instrucción `foreach` repite un grupo de instrucciones insertadas por cada elemento de una matriz o una colección de objetos que implementa la interfaz <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. La instrucción `foreach` se usa para recorrer en iteración la colección para obtener la información deseada, pero no puede usarse para agregar o quitar elementos de la colección de origen para evitar efectos secundarios imprevisibles. Si se necesitan agregar o quitar elementos de la colección de origen, se usa un bucle [for](for.md).
  
 Las instrucciones incrustadas continúan ejecutándose para cada elemento de la matriz o la colección. Cuando la iteración se completa en todos los elementos de la colección, el control se transfiere a la instrucción que sigue al bloque `foreach`.
  
 En cualquier punto del bloque `foreach`, se puede salir del bucle mediante la palabra clave [break](break.md), o bien se puede ir a la siguiente iteración del bucle mediante la palabra clave [continue](continue.md).

 También se puede salir de un bucle `foreach` mediante las instrucciones [goto](goto.md), [return](return.md) o [throw](throw.md).

 Para más información sobre la palabra clave `foreach` y obtener ejemplos de código, vea los temas siguientes:  

 [Utilizar foreach con matrices](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [Cómo: Obtener acceso a una clase de colección mediante Foreach](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>Ejemplo
 En el siguiente código se muestran tres ejemplos.

> [!TIP]
> Puede modificar los ejemplos para probar la sintaxis y tantear distintos usos que se acerquen más a su caso particular. Presione "Ejecutar" para ejecutar el código, cámbielo y vuelva a presionar "Ejecutar".

-   un bucle `foreach` típico que muestra el contenido de una matriz de enteros

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   un bucle [for](../../../csharp/language-reference/keywords/for.md) que hace lo mismo

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   un bucle `foreach` que mantiene un recuento del número de elementos de la matriz

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>Especificación del lenguaje C#
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también  

[Referencia de C#](../index.md)

[Guía de programación de C#](../../programming-guide/index.md)

[Palabras clave de C#](index.md)

[Instrucciones de iteración](iteration-statements.md)

[for](for.md)
