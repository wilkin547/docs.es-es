---
title: 'Conversiones de puntero: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 81b2110e6a571e174693fd272d1c6b4bf44dbae3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588221"
---
# <a name="pointer-conversions-c-programming-guide"></a>Conversiones de puntero (Guía de programación de C#)
En la tabla siguiente se muestran las conversiones de puntero implícitas predefinidas. Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.  
  
## <a name="implicit-pointer-conversions"></a>Conversiones de puntero implícitas  
  
|De|En|  
|----------|--------|  
|Cualquier tipo de puntero|void*|  
|nulo|Cualquier tipo de puntero|  
  
 La conversión de puntero explícita se usa para realizar conversiones, donde no existe ninguna conversión implícita, mediante una expresión de conversión. En la siguiente tabla se muestran estas conversiones.  
  
## <a name="explicit-pointer-conversions"></a>Conversiones de puntero explícitas  
  
|De|En|  
|----------|--------|  
|Cualquier tipo de puntero|Cualquier otro tipo de puntero|  
|sbyte, byte, short, ushort, int, uint, long o ulong|Cualquier tipo de puntero|  
|Cualquier tipo de puntero|sbyte, byte, short, ushort, int, uint, long o ulong|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, un puntero a `int` se convierte en un puntero a `byte`. Tenga en cuenta que el puntero señala al byte dirigido más bajo de la variable. Cuando incrementa el resultado sucesivamente, hasta el tamaño de `int` (4 bytes), puede mostrar los bytes restantes de la variable.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Tipos de puntero](./pointer-types.md)
- [Tipos](../../language-reference/keywords/types.md)
- [unsafe](../../language-reference/keywords/unsafe.md)
- [fixed (instrucción)](../../language-reference/keywords/fixed-statement.md)
- [stackalloc](../../language-reference/operators/stackalloc.md)
