---
title: 'Instrucción break: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 02d12ef92e1361bc8d46603d803a1b8b7c06a0a0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243209"
---
# <a name="break-c-reference"></a>break (Referencia de C#)

La instrucción `break` finaliza la ejecución del bucle contenedor más próximo o de la instrucción [switch](../../../csharp/language-reference/keywords/switch.md) en la que aparezca. El control se pasa a la instrucción que hay a continuación de la instrucción finalizada, si existe.

## <a name="example"></a>Ejemplo

En este ejemplo, la instrucción condicional contiene un contador que se supone que cuenta de 1 a 100. Pero la instrucción `break` finaliza el bucle después de cuatro recuentos.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Ejemplo

En este ejemplo, se usa la instrucción `break` para salir de un bucle anidado interno y devolver el control al bucle externo.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Ejemplo

En este ejemplo se muestra el uso de `break` en una instrucción [switch](../../../csharp/language-reference/keywords/switch.md).

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

Si se escribió `4`, la salida será:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [switch](../../../csharp/language-reference/keywords/switch.md)  
- [Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)  
- [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)
