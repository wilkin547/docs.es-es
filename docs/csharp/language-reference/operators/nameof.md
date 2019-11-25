---
title: 'Operador nameof: referencia de C#'
ms.custom: seodec18
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: fa858db918cdaf04c757f2741265e359acb74f7b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036349"
---
# <a name="nameof-operator-c-reference"></a>Operador nameof (referencia de C#)

El operador `nameof` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

El operador `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.

Puede usar el operador `nameof` para hacer que el código de comprobación de argumentos sea más fácil de mantener:

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

El operador `nameof` está disponible en C# 6 y versiones posteriores.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
