---
title: 'Operador ^: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333712"
---
# <a name="-operator-c-reference"></a>Operador ^ (Referencia de C#)

Los operadores binarios `^` están predefinidos para los tipos enteros y `bool`. Para los tipos enteros, `^` calcula OR exclusiva bit a bit de sus operandos. Para operandos `bool`, `^` calcula OR exclusiva lógica de sus operandos; es decir, el resultado es `true` si y solo si exactamente uno de sus operandos es `true`.

## <a name="remarks"></a>Comentarios

Los tipos definidos por el usuario pueden sobrecargar el operador `^` (vea [operator](../keywords/operator.md)). Las operaciones de tipos enteros suelen estar permitidas en la enumeración.

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

El cálculo de `0xf8 ^ 0x3f` en el ejemplo anterior realiza una operación OR exclusiva bit a bit de los siguientes dos valores binarios, que corresponden a los valores hexadecimales F8 y 3F:

`1111 1000`

`0011 1111`

El resultado de la OR exclusiva es `1100 0111`, que es C7 en hexadecimal.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
