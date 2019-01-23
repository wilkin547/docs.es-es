---
title: 'Operador |: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 185ea3aabff4794ec08cca541773dbec3574ab4b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333517"
---
# <a name="-operator-c-reference"></a>Operador| (Referencia de C#)

Los operadores binarios `|` están predefinidos para los tipos enteros y `bool`. Para los tipos enteros, `|` calcula OR bit a bit de sus operandos. Para operandos `bool`, `|` calcula el OR lógico de sus operandos; es decir, el resultado es `false` si y solo si ambos operandos son `false`.

## <a name="remarks"></a>Comentarios

El operador `|` binario evalúa ambos operandos con independencia del valor del primero, a diferencia del [operador OR condicional](conditional-or-operator.md) `||`.

Los tipos definidos por el usuario pueden sobrecargar el operador `|` (vea [operator](../keywords/operator.md)).

## <a name="example"></a>Ejemplo

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)