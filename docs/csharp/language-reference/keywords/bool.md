---
title: bool (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 1045a459491b0d0d6a84c60f6e820297b47efd5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215976"
---
# <a name="bool-c-reference"></a>bool (Referencia de C#)
La palabra clave `bool` es un alias de <xref:System.Boolean?displayProperty=nameWithType>. Se usa para declarar variables que almacenan los valores booleanos [true](../../../csharp/language-reference/keywords/true.md) y [false](../../../csharp/language-reference/keywords/false.md).  
  
> [!NOTE]
>  Si necesita una variable booleana que también pueda tener un valor de `null`, use `bool?`. Para más información, consulte [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL).  
  
## <a name="literals"></a>Literales  
 Se puede asignar un valor booleano a una variable `bool`. También se puede asignar una expresión que se evalúe como `bool` a una variable `bool`.  
  
 [!code-csharp[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 El valor predeterminado de una variable `bool` es `false`. El valor predeterminado de una variable `bool?` es `null`.  
  
## <a name="conversions"></a>Conversiones  
 En C++, un valor de tipo `bool` se puede convertir en un valor de tipo `int`, es decir, `false` equivale a cero y `true` equivale a valores distintos de cero. En C#, no hay ninguna conversión entre el tipo `bool` y otros tipos. Por ejemplo, la siguiente instrucción `if` no es válida en C#:  
  
 [!code-csharp[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 Para probar una variable del tipo `int`, tendrá que compararla explícitamente con un valor, como cero, del modo siguiente:  
  
 [!code-csharp[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se escribe un carácter desde el teclado y el programa comprueba si el carácter de entrada es una letra. Si es una letra, comprueba si está en mayúsculas o minúsculas. Estas comprobaciones se realizan con <xref:System.Char.IsLetter%2A> y <xref:System.Char.IsLower%2A>; ambos devuelven el tipo `bool`:  
  
 [!code-csharp[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
