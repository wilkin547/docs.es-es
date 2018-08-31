---
title: Palabra clave operator (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929877"
---
# <a name="operator-c-reference"></a>operator (Referencia de C#)

Use la palabra clave `operator` para sobrecargar un operador integrado o proporcionar una conversión definida por el usuario en una declaración de clase o estructura.

## <a name="example"></a>Ejemplo

La siguiente es una clase muy simplificada para números fraccionarios. Sobrecarga los operadores `+` y `*` para realizar multiplicaciones y sumas fraccionarias, y también proporciona un operador de conversión que convierte un tipo `Fraction` en un tipo `double`.

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [Cómo: Implementar conversiones definidas por el usuario entre structs](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
