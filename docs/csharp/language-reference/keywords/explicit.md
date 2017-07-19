---
title: explicit (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
dev_langs:
- CSharp
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a5c842eba24f0a30d357afc24aeed10c1447345e
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="explicit-c-reference"></a>explicit (Referencia de C#)
La palabra clave `explicit` declara un operador de conversión de tipo definido por el usuario que se debe invocar con una conversión. Por ejemplo, este operador convierte una clase denominada Fahrenheit en una clase denominada Celsius:  
  
 [!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 Este operador de conversión se puede invocar de esta forma:  
  
 [!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 El operador de conversión convierte un tipo de origen en un tipo de destino. El tipo de origen proporciona el operador de conversión. A diferencia de la conversión implícita, los operadores de conversión explícitos deben invocarse mediante una conversión. Si una operación de conversión puede producir excepciones o pérdida de información, debe marcarse como `explicit`. Esto impide que el compilador invoque silenciosamente la operación de conversión con posibles consecuencias no deseadas.  
  
 Omitir la conversión produce el error en tiempo de compilación CS0266.  
  
 Para obtener más información, vea [Uso de operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se proporciona una clase `Fahrenheit` y una clase `Celsius`, y cada una proporciona un operador de conversión explícita a la otra clase.  
  
 [!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define una struct, `Digit`, que representa un único dígito decimal. Se define un operador para conversiones de `byte` a `Digit`, pero como no todos los bytes se pueden convertir a un `Digit`, la conversión es explícita.  
  
 [!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md)   
 [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384) (Conversiones explícitas encadenadas definidas por el usuario en C#)
