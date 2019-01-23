---
title: 'Operador -=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333335"
---
# <a name="--operator-c-reference"></a>Operador -= (Referencia de C#)

Operador de asignación y resta.

## <a name="remarks"></a>Comentarios

Una expresión que use el operador de asignación `-=`, como

```csharp
x -= y
```

 es equivalente a

```csharp
x = x - y
```

salvo que `x` solo se evalúa una vez. El significado del [operador -](subtraction-operator.md) depende de los tipos de `x` e `y` (resta de operandos numéricos, eliminación de delegados en operandos de delegado, etc.).

El operador `-=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador -](subtraction-operator.md) (vea [operator](../keywords/operator.md) [Operador]).

El operador -= también se usa en C# para cancelar la suscripción a un evento. Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
