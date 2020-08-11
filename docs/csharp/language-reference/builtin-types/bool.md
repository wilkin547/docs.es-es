---
title: 'bool (tipo): Referencia de C#'
ms.date: 11/26/2019
f1_keywords:
- bool
- bool_CSharpKeyword
- "true"
- "false"
- true_CSharpKeyword
- false_CSharpKeyword
helpviewer_keywords:
- bool data type [C#]
- Boolean [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 4623dc7d6c8c6c437c78aee45f0eeee8a92e3200
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854885"
---
# <a name="bool-c-reference"></a>bool (Referencia de C#)

La palabra clave de tipo `bool` es un alias para el tipo de estructura de .NET <xref:System.Boolean?displayProperty=nameWithType> que representa un valor booleano que puede ser `true` o `false`.

Para realizar operaciones lógicas con valores del tipo `bool`, use operadores [lógicos booleanos](../operators/boolean-logical-operators.md). El tipo `bool` es el tipo de resultado de los operadores de [comparación](../operators/comparison-operators.md) e [igualdad](../operators/equality-operators.md). Una expresión `bool` puede ser una expresión condicional de control en las instrucciones [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md) y [for](../keywords/for.md), así como en el [operador condicional `?:`](../operators/conditional-operator.md).

El valor predeterminado del tipo `bool` es `false`.

## <a name="literals"></a>Literales

Puede usar los literales `true` y `false` para inicializar una variable `bool` o para pasar un valor `bool`:

[!code-csharp-interactive[bool literals](snippets/BoolType.cs#Literals)]

## <a name="three-valued-boolean-logic"></a>Lógica booleana de tres valores

Use el tipo `bool?` que acepta valores NULL si tiene que admitir la lógica de tres valores (por ejemplo, si trabaja con bases de datos que admiten un tipo booleano de tres valores). En el caso de los operandos `bool?`, los operadores predefinidos `&` y `|` admiten la lógica de tres valores. Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](../operators/boolean-logical-operators.md).

Para más información sobre los tipos de valor que admiten un valor NULL, consulte [Tipos de valor que admiten un valor NULL](nullable-value-types.md).

## <a name="conversions"></a>Conversiones

C# solo proporciona dos conversiones que implican al tipo `bool`. Son una conversión implícita al tipo `bool?` que acepta valores NULL correspondiente y una conversión explícita del tipo `bool?`. Sin embargo, .NET proporciona métodos adicionales que se pueden usar para realizar una conversión al tipo `bool`, o bien revertirla. Para obtener más información, vea la sección [Convertir a y desde valores booleanos](/dotnet/api/system.boolean#converting-to-and-from-boolean-values) de la página de referencia de la API <xref:System.Boolean?displayProperty=nameWithType>.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección [Tipo bool](~/_csharplang/spec/types.md#the-bool-type) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de valor](value-types.md)
- [Operadores true y false](../operators/true-false-operators.md)
