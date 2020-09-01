---
description: '#define: Referencia de C#'
title: '#define: Referencia de C#'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: a37f883a249ec74b66769ee40b84b20e8568c451
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132344"
---
# <a name="define-c-reference"></a>#define (Referencia de C#)
Usa `#define` para definir un símbolo. Si usa el símbolo como expresión que se pasa a la directiva [#if](./preprocessor-if.md), la expresión se evaluará como `true`, como se muestra en el siguiente ejemplo:  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> La directiva `#define` no puede usarse para declarar valores constantes como suele hacerse en C y C++. En C#, las constantes se definen mejor como miembros estáticos de una clase o struct. Si tiene varias constantes de este tipo, puede considerar la posibilidad de crear una clase "Constants" independiente donde incluirlas.  
  
 Los símbolos se pueden usar para especificar condiciones de compilación. Puede comprobar el símbolo tanto con [#if](./preprocessor-if.md) como con [#elif](./preprocessor-elif.md). También se puede usar <xref:System.Diagnostics.ConditionalAttribute> para realizar una compilación condicional.  
  
 Es posible definir un símbolo, pero no asignar un valor a un símbolo. La directiva `#define` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva del preprocesador.  
  
 También se puede definir un símbolo con la opción del compilador [-define](../compiler-options/define-compiler-option.md). La definición de un símbolo se puede anular mediante [#undef](./preprocessor-undef.md).  
  
 Un símbolo definido mediante `-define` o `#define` no debe entrar en conflicto con una variable del mismo nombre. Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.  
  
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
  
 Para obtener un ejemplo de cómo anular la definición de un símbolo, vea [#undef](./preprocessor-undef.md).  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
- [const](../keywords/const.md)
- [Cómo: Compilación condicional con Trace y Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [#undef](./preprocessor-undef.md)
- [#if](./preprocessor-if.md)
