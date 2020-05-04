---
title: 'Palabra clave params para matrices de parámetros: referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738836"
---
# <a name="params-c-reference"></a>params (Referencia de C#)

Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](method-parameters.md) que toma un número variable de argumentos. El tipo de parámetro debe ser una matriz unidimensional.

No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.

Si el tipo declarado del parámetro `params` no es una matriz unidimensional, se produce el error [CS0225](../../misc/cs0225.md) del compilador.

Cuando se llama a un método con un parámetro `params`, se puede pasar:

- Una lista separada por comas de argumentos del tipo de los elementos de la matriz.
- Una matriz de argumentos del tipo especificado.
- Sin argumentos. Si no envía ningún argumento, la longitud de la lista `params` es cero.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestran varias maneras de enviar argumentos a un parámetro `params`.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Parámetros de métodos](method-parameters.md)
