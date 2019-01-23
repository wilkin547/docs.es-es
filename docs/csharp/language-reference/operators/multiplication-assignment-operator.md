---
title: 'Operador *=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333439"
---
# <a name="-operator-c-reference"></a>Operador \*= (Referencia de C#)

El operador de asignación y multiplicación binaria.

## <a name="remarks"></a>Comentarios

Una expresión que use el operador de asignación `*=`, como

```csharp
x *= y
```

es equivalente a

```csharp
x = x * y
```

salvo que `x` solo se evalúa una vez. El [operador \*](multiplication-operator.md) está predefinido en tipos numéricos para realizar la multiplicación.

El operador `*=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador \*](multiplication-operator.md) (consulte [operator](../keywords/operator.md)).

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
