---
title: "#if (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#if"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#if (directiva) [C#]"
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# #if (Referencia de C#)
Cuando el compilador de C\# detecta una directiva `#if`, seguida eventualmente de una directiva [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), compilará el código entre las directivas únicamente si se define el símbolo especificado.  A diferencia de C y C\+\+, no se puede asignar un valor numérico a un símbolo; la instrucción \#if en C\# es booleana y solo comprueba si se ha definido o no el símbolo.  Por ejemplo,  
  
```  
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 Los operadores [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) \(igualdad\), [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) \(desigualdad\) solo se pueden usar para comprobar si el valor es [true](../../../csharp/language-reference/keywords/true.md) o [false](../../../csharp/language-reference/keywords/false.md).  True significa que se ha definido el símbolo.  La instrucción `#if DEBUG` tiene el mismo significado que `#if (DEBUG == true)`.  Puede usar operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) \(y\), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) \(o\), y [\!](../../../csharp/language-reference/operators/logical-negation-operator.md) \(no\) evaluar si se han definido los símbolos.  Es posible agrupar símbolos y operadores mediante paréntesis.  
  
## Comentarios  
 `#if`, junto con las directivas [\#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) y [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), permite incluir o excluir código basándose en la existencia de uno o varios símbolos.  Esto puede ser de utilidad si se compila código para una versión de depuración o para una configuración específica.  
  
 Una directiva condicional que empieza con una directiva `#if` debe terminarse explícitamente con una directiva `#endif`.  
  
 `#define` permite definir un símbolo tal que, si se utiliza como expresión de la directiva `#if`, la expresión se evaluará como `true`.  
  
 También se puede definir un símbolo con la opción [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador.  La definición de un símbolo se puede anular mediante la directiva [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Un símbolo definido mediante `/define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.  Es decir, no se debería utilizar un nombre de variable en una directiva de preprocesador ni evaluar un símbolo \(constante simbólica\) fuera de una directiva de preprocesador.  
  
 El ámbito de un símbolo creado mediante `#define` corresponde al archivo en el que se ha definido.  
  
## Ejemplo  
  
```  
// preprocessor_if.cs  
#define DEBUG #define MYTEST  
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
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)