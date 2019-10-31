---
title: value (Palabra clave contextual, Referencia de C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 34b192d17bd96b6b893c9f14f0d4a77274a32f78
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771741"
---
# <a name="value-c-reference"></a>value (Referencia de C#)

La palabra clave contextual `value` se usa en el descriptor de acceso `set` de las declaraciones [propiedad](../../programming-guide/classes-and-structs/properties.md) y [indizador](../../programming-guide/indexers/index.md). Es parecido a un parámetro de entrada de un método. El término `value` hace referencia al valor que el código de cliente intenta asignar a la propiedad o indizador. En el ejemplo siguiente, `MyDerivedClass` tiene una propiedad denominada `Name` que usa el parámetro `value` para asignar una nueva cadena al campo de respaldo `name`. Desde el punto de vista del código de cliente, la operación se escribe como una simple asignación.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Para obtener más información, consulte los artículos [Propiedades](../../programming-guide/classes-and-structs/properties.md) e [Indizadores](../../programming-guide/indexers/index.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
