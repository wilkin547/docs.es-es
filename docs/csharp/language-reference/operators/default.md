---
title: 'Expresiones de valor predeterminado: referencia de C#'
description: Use las expresiones de valor predeterminado para obtener el valor predeterminado de un tipo
ms.date: 03/13/2020
f1_keywords:
- default_CSharpKeyword
- default
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: f03971efa87bf03967c79512e44d22134dd80c17
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916864"
---
# <a name="default-value-expressions-c-reference"></a>Expresiones de valor predeterminado (referencia de C#)

Una expresión de valor predeterminado genera el [valor predeterminado](../builtin-types/default-values.md) de un tipo. Hay dos tipos de expresiones de valor predeterminado: la llamada al [operador predeterminado](#default-operator) y un [literal predeterminado](#default-literal).

También se usa la palabra clave `default` como etiqueta de mayúsculas y minúsculas predeterminada dentro de una [instrucción `switch`](../keywords/switch.md).

## <a name="default-operator"></a>operador default

El argumento del operador `default` debe ser el nombre de un tipo o un parámetro de tipo, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[default of T](snippets/shared/DefaultOperator.cs#WithOperand)]

## <a name="default-literal"></a>Literal default

A partir C# de 7.1, puede usar el literal `default` para generar el valor predeterminado de un tipo cuando el compilador puede deducir el tipo de expresión. La expresión literal `default` genera el mismo valor que la expresión `default(T)` cuando se deduce el tipo `T`. Puede usar el literal `default` en cualquiera de los casos siguientes:

- En la asignación o inicialización de una variable.
- En la declaración del valor predeterminado de un [parámetro de método opcional](../../methods.md#optional-parameters-and-arguments).
- En una llamada al método para proporcionar un valor de argumento.
- En una [instrucción `return`](../keywords/return.md) o como una expresión de un [miembro con cuerpo de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

En el ejemplo siguiente se muestra el uso del literal `default`:

[!code-csharp-interactive[default literal](snippets/shared/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección [Expresiones de valor predeterminado](~/_csharplang/spec/expressions.md#default-value-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para más información sobre el literal `default`, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Valores predeterminados de los tipos de C#](../builtin-types/default-values.md)
- [Elementos genéricos en .NET](../../../standard/generics/index.md)
