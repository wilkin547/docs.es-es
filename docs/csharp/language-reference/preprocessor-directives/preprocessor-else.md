---
description: '#else: Referencia de C#'
title: '#else: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168678"
---
# <a name="else-c-reference"></a>#else (Referencia de C#)

`#else` permite crear una directiva condicional compuesta, de modo que, si ninguna de las expresiones de las directivas [#if](./preprocessor-if.md) o [#elif](./preprocessor-elif.md) (opcional) anteriores se evalúan como `true`, el compilador evaluará todo el código entre `#else` y la directiva `#endif` siguiente.  
  
## <a name="remarks"></a>Comentarios  

 [#endif](./preprocessor-endif.md) debe ser la siguiente directiva de preprocesador después de `#else`. Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#else`.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
