---
title: '#<a name="if-c-reference"></a>if (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#if'
helpviewer_keywords: '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4e3b79f64f5190d48d7248726ecdf031ad685e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="if-c-reference"></a>#if (Referencia de C#)
Cuando el compilador de C# encuentra una directiva `#if`, seguida finalmente por una directiva [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), compilará el código entre las directivas solo si se ha definido el símbolo especificado.  A diferencia de C y C++, no puede asignar un valor numérico a un símbolo; la instrucción #if en C# es booleana y solo comprueba si el símbolo se ha definido o no. Por ejemplo,  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 Puede usar los operadores [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (igualdad), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (desigualdad) solo para comprobar los valores [true](../../../csharp/language-reference/keywords/true.md) o [false](../../../csharp/language-reference/keywords/false.md) . True significa que el símbolo está definido. La instrucción `#if DEBUG` tiene el mismo significado que `#if (DEBUG == true)`. Puede usar los operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (y), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (o) y [!](../../../csharp/language-reference/operators/logical-negation-operator.md) (no) para evaluar si se han definido varios símbolos. Es posible agrupar símbolos y operadores mediante paréntesis.  
  
## <a name="remarks"></a>Comentarios  
 `#if`, junto con las directivas [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) y [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), permite incluir o excluir código basado en la existencia de uno o varios símbolos. Esto puede resultar útil al compilar código para una compilación de depuración o al compilar para una configuración específica.  
  
 Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.  
  
 `#define` permite definir un símbolo, de tal forma que, si se usa como la expresión pasada a la directiva `#if`, la expresión se evaluará el valor `true`.  
  
 También puede definir un símbolo con la opción [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador. La definición de un símbolo se puede anular mediante [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Un símbolo definido mediante `/define` o `#define` no debe entrar en conflicto con una variable del mismo nombre. Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.  
  
 El ámbito de un símbolo creado con `#define` es el archivo en que se ha definido.  
  
## <a name="example"></a>Ejemplo  
  
```csharp
// preprocessor_if.cs  
#define DEBUG
#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 **Se definen DEBUG y MYTEST**  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
