---
title: if-else (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
dev_langs:
- CSharp
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e4016ee35ed487fd2ca48074d2e483778719dff3
ms.lasthandoff: 03/13/2017

---
# <a name="if-else-c-reference"></a>if-else (Referencia de C#)
Una instrucción `if` identifica qué instrucción se debe ejecutar dependiendo del valor de una expresión `Boolean` . En el ejemplo siguiente, la variable `Boolean` `result` se establece en `true` y, a continuación, se comprueba en la instrucción `if` . El resultado es `The condition is true`  
  
 [!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]  
  
 Puede ejecutar los ejemplos de este tema situándolos en el método `Main` de una aplicación de consola.  
  
 Una instrucción `if` en C# puede tener dos formas, tal como se muestra en el ejemplo siguiente.  
  
```csharp  
  
// if-else statement  
if (condition)  
{  
    then-statement;  
}  
else  
{  
    else-statement;  
}  
// Next statement in the program.  
  
// if statement without an else  
if (condition)  
{  
    then-statement;  
}  
// Next statement in the program.  
```  
  
 En una instrucción `if-else` , si `condition` se evalúa como true, se ejecuta `then-statement` . Si `condition` es false, se ejecuta `else-statement` . Puesto que `condition` no puede ser simultáneamente true y false, la `then-statement` y la `else-statement` de una instrucción `if-else` nunca se podrán ejecutar a la vez. Después de ejecutar la `then-statement` o la `else-statement` , el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .  
  
 En una instrucción `if` que no incluya una instrucción `else` , si `condition` es true, se ejecutará la `then-statement` . Si `condition` es false, el control se transfiere a la siguiente instrucción situada después de la instrucción `if` .  
  
 Tanto la `then-statement` como la `else-statement` pueden constar de una única instrucción o de varias instrucciones entre llaves (`{}`). Para una única instrucción, las llaves son opcionales pero se recomiendan.  
  
 La instrucción o las instrucciones en la `then-statement` y la `else-statement` pueden ser de cualquier tipo, incluida otra instrucción `if` anidada dentro de la instrucción `if` . En instrucciones `if` anidadas, cada cláusula `else` pertenece a la última `if` que no tiene su `else`correspondiente. En el ejemplo siguiente, `Result1` aparece si `m > 10` y `n > 20` se evalúan como true. Si `m > 10` es true, pero `n > 20` es false, aparece `Result2` .  
  
 [!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]  
  
 En su lugar, si desea que `Result2` aparezca cuando `(m > 10)` es false, puede especificar dicha asociación mediante llaves para establecer el inicio y el fin de la instrucción `if` anidada, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]  
  
 `Result2` aparece si la condición `(m > 10)` se evalúa como false.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se escribe un carácter desde el teclado y el programa usa una instrucción `if` anidada para determinar si el carácter de entrada es un carácter alfabético. Si el carácter de entrada es un carácter alfabético, el programa comprueba si el carácter de entrada está en mayúsculas o minúsculas. Aparece un mensaje para cada caso.  
  
 [!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]  
  
## <a name="example"></a>Ejemplo  
 También puede anidar una instrucción `if` dentro de un bloque else, tal como se muestra en el siguiente código parcial. El ejemplo anida instrucciones `if` dentro de dos bloques más y, a continuación, un bloque. Los comentarios de especifican qué condiciones son true o false en cada bloque.  
  
 [!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente determina si un carácter de entrada es una letra minúscula, una letra mayúscula o un número. Si estas tres condiciones son false, el carácter no es un carácter alfanumérico. En el ejemplo se muestra un mensaje para cada caso.  
  
 [!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]  
  
 Puesto que puede ser válida tanto una instrucción del bloque else como del bloque then, puede usar cualquier expresión booleana válida para la condición. Puede usar operadores lógicos tales como [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) y [!](../../../csharp/language-reference/operators/logical-negation-operator.md) para hacer condiciones compuestas. En el código siguiente, se muestran algunos ejemplos:  
  
```csharp  
// NOT  
bool result = true;  
if (!result)  
{  
    Console.WriteLine("The condition is true (result is false).");  
}  
else  
{  
    Console.WriteLine("The condition is false (result is true).");  
}  
  
// Short-circuit AND  
int m = 9;  
int n = 7;  
int p = 5;  
if (m >= n && m >= p)  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// AND and NOT  
if (m >= n && !(p > m))  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// Short-circuit OR  
if (m > n || m > p)  
{  
    Console.WriteLine("m isn't the smallest.");  
}  
  
// NOT and OR  
m = 4;  
if (!(m >= n || m >= p))  
{  
    Console.WriteLine("Now m is the smallest.");  
}  
// Output:  
// The condition is false (result is true).  
// Nothing is larger than m.  
// Nothing is larger than m.  
// m isn't the smallest.  
// Now m is the smallest.  
```  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Operador ?:](../../../csharp/language-reference/operators/conditional-operator.md)   
 [if-else (Instrucción) (C++)](https://docs.microsoft.com/cpp/cpp/if-else-statement-cpp)   
 [switch](../../../csharp/language-reference/keywords/switch.md)
