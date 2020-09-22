---
title: Operadores de conversión definidos por el usuario - referencia de C#
description: Obtenga información sobre cómo definir conversiones de tipos implícitas y explícitas personalizadas en C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
- explicit
- implicit
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: ab977408ed891bd7c996ce3644b22ea984425664
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536384"
---
# <a name="user-defined-conversion-operators-c-reference"></a>Operadores de conversión definidos por el usuario (referencia de C#)

Un tipo definido por el usuario puede definir una conversión implícita o explícita personalizada desde o a otro tipo.

Las conversiones implícitas no requieren que se invoque una sintaxis especial y pueden producirse en diversas situaciones, por ejemplo, en las invocaciones de métodos y asignaciones. Las conversiones implícitas predefinidas en C# siempre se realizan correctamente y nunca inician una excepción. Las conversiones implícitas definidas por el usuario deben comportarse de esta manera. Si una conversión personalizada puede producir una excepción o perder información, se define como una conversión explícita.

Los operadores [is](type-testing-and-cast.md#is-operator) y [as](type-testing-and-cast.md#as-operator) no tienen en cuenta las conversiones definidas por el usuario. Use una [expresión Cast](type-testing-and-cast.md#cast-expression) para invocar una conversión explícita definida por el usuario.

Use las palabras clave `operator` y `implicit` o `explicit` para definir una conversión implícita o explícita, respectivamente. El tipo que define una conversión debe ser un tipo de origen o un tipo de destino de dicha conversión. Una conversión entre dos tipos definidos por el usuario se puede definir en cualquiera de los dos tipos.

En el ejemplo siguiente se muestra cómo se define una conversión implícita y explícita:

[!code-csharp[implicit an explicit conversions](snippets/shared/UserDefinedConversions.cs)]

Use también la palabra clave `operator` para sobrecargar un operador predefinido en C#. Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Operadores de conversión](~/_csharplang/spec/classes.md#conversion-operators)
- [Conversiones definidas por el usuario](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [Conversiones implícitas](~/_csharplang/spec/conversions.md#implicit-conversions)
- [Conversiones explícitas](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Sobrecarga de operadores](operator-overloading.md)
- [Operadores de conversión y prueba de tipos](type-testing-and-cast.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
- [Directrices de diseño: operadores de conversión](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [Chained user-defined explicit conversions in C#](/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c) (Conversiones explícitas encadenadas definidas por el usuario en C#)
