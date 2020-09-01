---
description: 'Restricción new: Referencia de C#'
title: 'Restricción new: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: f7b097729fe973aba7b85c48e1b1033aade83080
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139455"
---
# <a name="new-constraint-c-reference"></a>Restricción new (Referencia de C#)

La restricción `new` especifica que un tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público. Para usar la restricción `new`, el tipo no puede ser abstracto.

Aplique la restricción `new` a un tipo de parámetro cuando una clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).

También puede usar la palabra clave `new` para [crear una instancia de un tipo](../operators/new-operator.md) o como un [modificador de declaración de miembro](new-modifier.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Restricciones de parámetros de tipo](~/_csharplang/spec/classes.md#type-parameter-constraints) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Genéricos](../../programming-guide/generics/index.md)
