---
title: '#endif: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 13b43919b666dcc8c5adfc3490eaad73960547ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243912"
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

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
