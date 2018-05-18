---
title: explicit (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: c8a05aef3318eb34242ed1268ea26663592e4d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-c-reference"></a>explicit (Referencia de C#)
La palabra clave `explicit` declara un operador de conversión de tipo definido por el usuario que se debe invocar con una conversión. Por ejemplo, este operador convierte una clase denominada Fahrenheit en una clase denominada Celsius:  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 Este operador de conversión se puede invocar de esta forma:  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 El operador de conversión convierte un tipo de origen en un tipo de destino. El tipo de origen proporciona el operador de conversión. A diferencia de la conversión implícita, los operadores de conversión explícitos deben invocarse mediante una conversión. Si una operación de conversión puede producir excepciones o pérdida de información, debe marcarse como `explicit`. Esto impide que el compilador invoque silenciosamente la operación de conversión con posibles consecuencias no deseadas.  
  
 Omitir la conversión produce el error en tiempo de compilación CS0266.  
  
 Para obtener más información, vea [Uso de operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se proporciona una clase `Fahrenheit` y una clase `Celsius`, y cada una proporciona un operador de conversión explícita a la otra clase.  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define una struct, `Digit`, que representa un único dígito decimal. Se define un operador para conversiones de `byte` a `Digit`, pero como no todos los bytes se pueden convertir a un `Digit`, la conversión es explícita.  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (Conversiones explícitas encadenadas definidas por el usuario en C#)
