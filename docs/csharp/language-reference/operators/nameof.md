---
title: 'Operador nameof: referencia de C#'
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: ffbc801acf61bf72db1c88912dc2142a478fa280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846277"
---
# <a name="nameof-operator-c-reference"></a>Operador nameof (referencia de C#)

El operador `nameof` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:

[!code-csharp-interactive[nameof operator](snippets/NameOfOperator.cs#Examples)]

Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

El operador `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.

Puede usar el operador `nameof` para hacer que el código de comprobación de argumentos sea más fácil de mantener:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

El operador `nameof` está disponible en C# 6 y versiones posteriores.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
