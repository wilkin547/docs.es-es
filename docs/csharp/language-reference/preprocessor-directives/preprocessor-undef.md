---
description: '#undef: Referencia de C#'
title: '#undef: Referencia de C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: ecbf8f5793e70c7dd6e602a3992ee3783a76c7ca
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477977"
---
# <a name="undef-c-reference"></a>#undef (Referencia de C#)

`#undef` le permite anular la definición de un símbolo, de tal forma que, si se usa como la expresión en una directiva [#if](./preprocessor-if.md), la expresión se evaluará como `false`.  
  
 Un símbolo se puede definir con la directiva [#define](./preprocessor-define.md) o la [opción del compilador **DefineConstants**](../compiler-options/language.md#defineconstants). La directiva `#undef` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva.  
  
## <a name="example"></a>Ejemplo  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

**DEBUG está sin definirse**

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
