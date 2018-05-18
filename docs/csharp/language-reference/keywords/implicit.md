---
title: implicit (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 160d9f7c0d58abd685bf1d799b53cc96a26aebe8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implicit-c-reference"></a>implicit (Referencia de C#)
La palabra clave `implicit` se usa para declarar un operador de conversión de tipo implícito definido por el usuario. Úsela para permitir conversiones implícitas entre un tipo definido por el usuario y otro tipo, si existen garantías de que la conversión no provocará la pérdida de datos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 Si se eliminan las conversiones innecesarias, las conversiones implícitas pueden mejorar la legibilidad del código fuente. En cambio, como las conversiones implícitas no requieren que los programadores conviertan explícitamente un tipo en otro, deben tomarse las medidas adecuadas para impedir que se produzcan resultados imprevistos. En general, los operadores de conversión implícita nunca deberían producir excepciones ni pérdida de información, de modo que puedan usarse de manera segura sin intervención del programador. Si un operador de conversión no cumple esos criterios, debería marcarse como `explicit`. Para obtener más información, vea [Usar operadores de conversión (Guía de programación de C#)](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)  
 [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
