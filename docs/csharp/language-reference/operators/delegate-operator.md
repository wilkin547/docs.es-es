---
description: 'Operador delegate: referencia de C#'
title: 'Operador delegate: referencia de C#'
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247662"
---
# <a name="delegate-operator-c-reference"></a>Operador delegate (referencia de C#)

El operador `delegate` crea un método anónimo que se puede convertir en un tipo delegado:

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> A partir de C# 3, las expresiones lambda proporcionan una manera más concisa y expresiva de crear una función anónima. Use el [operador =>](lambda-operator.md) para construir una expresión lambda:
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> Para más información sobre las características de las expresiones lambda, como capturar las variables externas, consulte [Expresiones lambda](lambda-expressions.md).

Al usar el operador `delegate`, puede omitir la lista de parámetros. Si lo hace, el método anónimo creado se puede convertir en un tipo delegado con cualquier lista de parámetros, tal como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

Esta es la única funcionalidad de los métodos anónimos que las expresiones lambda no admiten. En todos los demás casos, una expresión lambda es una de las maneras preferidas de escribir código alineado.

A partir de C# 9.0, puede usar [descartes](../../discards.md) para especificar dos o más parámetros de entrada de un método anónimo que no usa el método:

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

Por compatibilidad con versiones anteriores, si solo un parámetro se denomina `_`, `_` se trata como el nombre de ese parámetro dentro de un método anónimo.

También a partir de C# 9.0, puede usar el modificador `static` en la declaración de un método anónimo:

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

Un método anónimo estático no puede capturar variables locales ni el estado de la instancia desde el ámbito de inclusión.

También puede usar la palabra clave `delegate` para declarar un [tipo delegado](../builtin-types/reference-types.md#the-delegate-type).

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para obtener más información, vea la sección [Expresiones de función anónima](~/_csharplang/spec/expressions.md#anonymous-function-expressions) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Operador =>](lambda-operator.md)
