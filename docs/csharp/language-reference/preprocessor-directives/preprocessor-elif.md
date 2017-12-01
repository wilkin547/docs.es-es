---
title: '#<a name="elif-c-reference"></a>elif (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#elif'
helpviewer_keywords: '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1512bbbc46ce15570507c8b51540eef607d55dc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="elif-c-reference"></a>#elif (Referencia de C#)
`#elif` permite crear una directiva condicional compuesta. La expresión `#elif` se evaluará si ninguna de las expresiones de las directivas [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) o `#elif` (opcional) precedentes se evalúan como `true`. Si una expresión `#elif` se evalúa como `true`, el compilador incluye en la compilación todo el código comprendido entre `#elif` y la siguiente directiva condicional. Por ejemplo:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 Se pueden usar los operadores `==` (igualdad), `!=` (desigualdad), `&&` (y), así como `||` (o), para evaluar varios símbolos. Es posible agrupar símbolos y operadores mediante paréntesis.  
  
## <a name="remarks"></a>Comentarios  
 `#elif` equivale a usar:  
  
```csharp
#else  
#if  
```  
  
 El uso de `#elif` es más simple ya que cada directiva `#if` requiere una directiva [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), mientras que una directiva `#elif` se puede usar sin la directiva `#endif` correspondiente.  
  
 Vea [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para obtener un ejemplo de cómo usar `#elif`.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
