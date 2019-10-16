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
ms.openlocfilehash: 2628da73364cf94a52e2862d349243c100d4afaf
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179932"
---
# <a name="break-c-reference"></a>break (Referencia de C#)

La instrucción `break` finaliza la ejecución del bucle contenedor más próximo o de la instrucción [switch](./switch.md) en la que aparezca. El control se pasa a la instrucción que hay a continuación de la instrucción finalizada, si existe.

## <a name="example"></a>Ejemplo

En este ejemplo, la instrucción condicional contiene un contador que se supone que cuenta de 1 a 100. Pero la instrucción `break` finaliza el bucle después de cuatro recuentos.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Ejemplo

En este ejemplo se muestra el uso de `break` en una instrucción [switch](./switch.md).

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

Si se escribió `4`, la salida será:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a>Ejemplo

En este ejemplo, se usa la instrucción `break` para salir de un bucle anidado interno y devolver el control al bucle externo. El control _solo_ se devuelve un nivel hacia arriba en los bucles anidados.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Ejemplo

En este ejemplo, la instrucción `break` solo se usa para salir de la rama actual durante cada iteración del bucle. El propio bucle no se ve afectado por las instancias de `break` que pertenecen a la instrucción anidada [switch](./switch.md).

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [switch](./switch.md)
