---
description: '#elif: Referencia de C#'
title: '#elif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 383c143792a39bb3abcd255804360ad5e2f8ef74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168704"
---
# <a name="elif-c-reference"></a>#elif (Referencia de C#)

`#elif` permite crear una directiva condicional compuesta. La expresión `#elif` se evaluará si ninguna de las expresiones de las directivas [#if](./preprocessor-if.md) o `#elif` (opcional) precedentes se evalúan como `true`. Si una expresión `#elif` se evalúa como `true`, el compilador incluye en la compilación todo el código comprendido entre `#elif` y la siguiente directiva condicional. Por ejemplo:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 Se pueden usar los operadores `==` (igualdad), `!=` (desigualdad), `&&` (y), así como `||` (o), para evaluar varios símbolos. Es posible agrupar símbolos y operadores mediante paréntesis.  
  
## <a name="remarks"></a>Observaciones  

 `#elif` equivale a usar:  
  
```csharp
#else  
#if  
```  
  
 El uso de `#elif` es más simple ya que cada directiva `#if` requiere una directiva [#endif](./preprocessor-endif.md), mientras que una directiva `#elif` se puede usar sin la directiva `#endif` correspondiente.  
  
 Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#elif`.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
