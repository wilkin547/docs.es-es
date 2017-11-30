---
title: "Conversiones de puntero (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 36589d139c91e04d9e3d8b31281a91c26b85a5d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pointer-conversions-c-programming-guide"></a>Conversiones de puntero (Guía de programación de C#)
En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas. Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.  
  
## <a name="implicit-pointer-conversions"></a>Conversiones de puntero implícitas  
  
|De|Para|  
|----------|--------|  
|Cualquier tipo de puntero|void*|  
|nulo|Cualquier tipo de puntero|  
  
 La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión. En la siguiente tabla se muestran estas conversiones.  
  
## <a name="explicit-pointer-conversions"></a>Conversiones de puntero explícitas  
  
|De|Para|  
|----------|--------|  
|Cualquier tipo de puntero|Cualquier otro tipo de puntero|  
|sbyte, byte, short, ushort, int, uint, long o ulong|Cualquier tipo de puntero|  
|Cualquier tipo de puntero|sbyte, byte, short, ushort, int, uint, long o ulong|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`. Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable. Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Expresiones de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Tipos](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed (instrucción)](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
