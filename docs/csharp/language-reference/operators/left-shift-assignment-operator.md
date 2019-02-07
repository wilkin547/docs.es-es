---
title: 'Operador <<=: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 0a005efa19be24f9adbf9031f562a30f9c1b0e34
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258739"
---
# <a name="-operator-c-reference"></a>Operador \<\<= (Referencia de C#)

Operador de asignación de desplazamiento a la izquierda.

## <a name="remarks"></a>Comentarios

Una expresión con el formato

```csharp
x <<= y
```

se evalúa como

```csharp
x = x << y
```

salvo que `x` solo se evalúa una vez. El [operador <<](left-shift-operator.md) desplaza `x` hacia la izquierda el número de bits especificado por `y`.

El operador `<<=` no se puede sobrecargar directamente, pero los tipos definidos por el usuario pueden sobrecargar el [operador <<](left-shift-operator.md) (vea [operator](../keywords/operator.md)).

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
