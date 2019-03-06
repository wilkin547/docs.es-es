---
title: '* operador: Referencia de C#'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977349"
---
# <a name="-operator-c-reference"></a>Operador * (Referencia de C#)

El operador `*` se admite de dos formas: un operador de direccionamiento indirecto del puntero unario o un operador de multiplicación binario.

## <a name="pointer-indirection-operator"></a>Operador de direccionamiento indirecto del puntero

Use el operador unario `*` para obtener la variable a la que apunta un operando de un tipo de puntero. Para obtener más información, vea [Cómo: Obtener el valor de una variable de puntero](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).

El operador de direccionamiento indirecto del puntero `*` requiere el contexto [unsafe](../keywords/unsafe.md).

## <a name="multiplication-operator"></a>Operador de multiplicación

En tipos numéricos, el operador `*` calcula la suma de sus operandos:

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) un operador `*` binario. Cuando se sobrecarga un operador `*` binario, el [operador de asignación de multiplicación](multiplication-assignment-operator.md) `*=` también se sobrecarga de modo implícito.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte las secciones de [direccionamiento indirecto del puntero](~/_csharplang/spec/unsafe-code.md#pointer-indirection) y del [operador de multiplicación](~/_csharplang/spec/expressions.md#multiplication-operator) de la [especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)