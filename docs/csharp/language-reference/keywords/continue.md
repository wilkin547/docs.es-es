---
description: 'Instrucción continue: Referencia de C#'
title: 'Instrucción continue: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877657"
---
# <a name="continue-c-reference"></a>continue (Referencia de C#)

La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](./while.md), [do](./do.md), [for](./for.md) o [foreach](./foreach-in.md) en la que aparece.

## <a name="example"></a>Ejemplo

En este ejemplo se inicializa un contador para contar del 1 al 10. Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for` en las iteraciones donde `i` es menor que 9. En las dos últimas iteraciones del bucle `for` (donde i == 9 e i == 10), la instrucción `continue` no se ejecuta y el valor de `i` se imprime en la consola.

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Consulte también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [break (Instrucción)](/cpp/cpp/break-statement-cpp)
