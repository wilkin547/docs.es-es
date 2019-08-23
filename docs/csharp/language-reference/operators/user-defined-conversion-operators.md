---
title: Operadores de conversión definidos por el usuario - referencia de C#
description: Obtenga información sobre cómo definir conversiones de tipos implícitas y explícitas personalizadas en C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: 8788883a6c60032de2ffab658fcf2721654fc6f7
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566677"
---
# <a name="user-defined-conversion-operators-c-reference"></a>Operadores de conversión definidos por el usuario (referencia de C#)

Un tipo definido por el usuario puede definir una conversión implícita o explícita personalizada desde o a otro tipo.

Las conversiones implícitas no requieren que se invoque una sintaxis especial y pueden producirse en diversas situaciones, por ejemplo, en las invocaciones de métodos y asignaciones. Las conversiones implícitas predefinidas en C# siempre se realizan correctamente y nunca producen una excepción o pérdida de información. Las conversiones implícitas definidas por el usuario deben comportarse de esta manera. Si una conversión personalizada puede producir una excepción o perder información, se define como una conversión explícita.

Los operadores [is](type-testing-and-cast.md#is-operator) y [as](type-testing-and-cast.md#as-operator) no tienen en cuenta las conversiones definidas por el usuario. Use el [operador de conversión ()](type-testing-and-cast.md#cast-operator-) para invocar una conversión explícita definida por el usuario.

Use las palabras clave `operator` y `implicit` o `explicit` para definir una conversión implícita o explícita, respectivamente. El tipo que define una conversión debe ser un tipo de origen o un tipo de destino de dicha conversión. Una conversión entre dos tipos definidos por el usuario se puede definir en cualquiera de los dos tipos.

En el ejemplo siguiente se muestra cómo se define una conversión implícita y explícita:

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

Use también la palabra clave `operator` para sobrecargar un operador predefinido en C#. Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Operadores de conversión](~/_csharplang/spec/classes.md#conversion-operators)
- [Conversiones definidas por el usuario](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [Conversiones implícitas](~/_csharplang/spec/conversions.md#implicit-conversions)
- [Conversiones explícitas](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Sobrecarga de operadores](operator-overloading.md)
- [Operadores de conversión y prueba de tipos](type-testing-and-cast.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
- [Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (Conversiones explícitas encadenadas definidas por el usuario en C#)
