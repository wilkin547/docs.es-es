---
title: 'Restricción new: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: de0798319d91032143cb806d6d39338c4f51ac8f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237849"
---
# <a name="new-constraint-c-reference"></a>Restricción new (Referencia de C#)

La restricción `new` especifica que cualquier tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público. Para usar la restricción new, el tipo no puede ser abstracto.

## <a name="example"></a>Ejemplo

Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

## <a name="example"></a>Ejemplo

Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

Para obtener más información, vea [Restricciones de tipos de parámetros](../../programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Palabras clave de operador](operator-keywords.md)
- [Genéricos](../../programming-guide/generics/index.md)