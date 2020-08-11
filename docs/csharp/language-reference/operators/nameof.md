---
title: 'Expresión nameof: referencia de C#'
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916778"
---
# <a name="nameof-expression-c-reference"></a>Expresión nameof (referencia de C#)

Una expresión `nameof` genera el nombre de una variable, un tipo o un miembro como constante de cadena:

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

En el caso de [identificadores textuales](../tokens/verbatim.md), el carácter `@` no es parte de un nombre, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

La expresión `nameof` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.

Puede usar una expresión `nameof` para facilitar el mantenimiento del código de comprobación de argumentos:

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

Una expresión `nameof` está disponible en C# 6 y versiones posteriores.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección [Expresiones Nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
