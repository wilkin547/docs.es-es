---
title: '#define (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ae72a1b6c19421c51348a0d93691ba3fe29a191c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="define-c-reference"></a>#define (Referencia de C#)
Usa `#define` para definir un símbolo. Si usa el símbolo como expresión que se pasa a la directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), la expresión se evaluará como `true`, como se muestra en el siguiente ejemplo:  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  La directiva `#define` no puede usarse para declarar valores constantes como suele hacerse en C y C++. En C#, las constantes se definen mejor como miembros estáticos de una clase o struct. Si tiene varias constantes de este tipo, puede considerar la posibilidad de crear una clase "Constants" independiente donde incluirlas.  
  
 Los símbolos se pueden usar para especificar condiciones de compilación. Puede comprobar el símbolo tanto con [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) como con [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md). También se puede usar el atributo `conditional` para realizar una compilación condicional.  
  
 Es posible definir un símbolo, pero no asignar un valor a un símbolo. La directiva `#define` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva del preprocesador.  
  
 También puede definir un símbolo con la opción [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador. La definición de un símbolo se puede anular mediante [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
 Un símbolo definido mediante `/define` o `#define` no debe entrar en conflicto con una variable del mismo nombre. Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.  
  
 El ámbito de un símbolo que se ha creado mediante `#define` corresponde al archivo en el que se ha definido.  
  
 Como se muestra en el siguiente ejemplo, debe colocar directivas `#define` en la parte superior del archivo.  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Para obtener un ejemplo de cómo anular la definición de un símbolo, vea [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [const](../../../csharp/language-reference/keywords/const.md)  
 [Cómo: realizar compilación condicional con Trace y Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)  
 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
