---
title: unchecked (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: 44301333f7a36e6b0baa6ea9e089d930bb485a45
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238460"
---
# <a name="unchecked-c-reference"></a>unchecked (Referencia de C#)

La palabra clave `unchecked` se usa para suprimir la comprobación de desbordamiento en las operaciones y conversiones aritméticas de tipos enteros.

En un contexto unchecked, si una expresión genera un valor que está fuera del intervalo del tipo de destino, no se marca el desbordamiento. Por ejemplo, dado que el cálculo del siguiente ejemplo se realiza en un bloque o una expresión `unchecked`, el hecho de que el resultado sea demasiado grande para un entero se omite y se asigna a `int1` el valor -2 147 483 639.

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

Si se quita el entorno `unchecked`, se produce un error de compilación. El desbordamiento se puede detectar en tiempo de compilación porque todos los términos de la expresión son constantes.

Las expresiones que contienen términos no constantes son unchecked de forma predeterminada en tiempo de compilación y tiempo de ejecución. Vea [checked](checked.md) para obtener información sobre cómo habilitar un entorno checked.

Puesto que la comprobación de desbordamiento lleva tiempo, el uso del código unchecked en situaciones donde no hay riesgo de desbordamiento puede mejorar el rendimiento. Pero si el desbordamiento es una posibilidad, se debe usar un entorno checked.

## <a name="example"></a>Ejemplo

En este ejemplo se muestra cómo usar la palabra clave `unchecked`.

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Checked y Unchecked](checked-and-unchecked.md)
- [checked](checked.md)