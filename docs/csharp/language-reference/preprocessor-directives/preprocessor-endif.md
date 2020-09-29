---
description: '#endif: Referencia de C#'
title: '#endif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168639"
---
# <a name="endif-c-reference"></a>#endif (Referencia de C#)

`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](./preprocessor-if.md). Por ejemplo,  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Comentarios  

 Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`. Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
