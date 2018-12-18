---
title: 'Instrucción goto: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: bfc997631cc147bf5718ec91a57e2995cead052f
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236770"
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
- [Instrucciones de salto](jump-statements.md)  
