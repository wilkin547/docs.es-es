---
title: '#endif (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 1686e706ce5cae3b2eaa28a7e1c89b5694b2be88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="endif-c-reference"></a>#endif (Referencia de C#)
`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md). Por ejemplo,  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Comentarios  
 Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`. Vea [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
