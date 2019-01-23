---
title: 'Operador &gt;&gt;=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333699"
---
# <a name="gtgt-operator-c-reference"></a>Operador &gt;&gt;= (Referencia de C#)

Operador de asignación de desplazamiento a la derecha.

## <a name="remarks"></a>Comentarios

Una expresión con el formato

```csharp
x >>= y
```

se evalúa como

```csharp
x = x >> y
```

salvo que `x` solo se evalúa una vez. El [operador >>](right-shift-operator.md) desplaza `x` hacia la derecha una cantidad especificada por `y`.

El operador >>= no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador >>](right-shift-operator.md) (vea [operator](../keywords/operator.md)).

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)