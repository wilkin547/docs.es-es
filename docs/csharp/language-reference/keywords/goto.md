---
description: 'Instrucción goto: Referencia de C#'
title: 'Instrucción goto: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: de95e477bd7e76f549130643c8d4b70a0e2f015c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128431"
---
# <a name="goto-c-reference"></a>goto (Referencia de C#)

La instrucción `goto` transfiere el control del programa directamente a una instrucción con etiqueta.

Un uso común de `goto` consiste en transferir el control a una etiqueta de switch case específica o a la etiqueta predeterminada en una instrucción `switch`.

La instrucción `goto` también es útil para salir de bucles demasiado anidados.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar `goto` en una instrucción [switch](switch.md).

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar `goto` para salir de bucles anidados.

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [goto (Instrucción) (C++)](/cpp/cpp/goto-statement-cpp)
