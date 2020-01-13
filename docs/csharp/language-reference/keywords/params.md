---
title: 'Palabra clave params: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 90d224080f607cbac96514aaf5ac6d67affef9e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713240"
---
# <a name="params-c-reference"></a>params (Referencia de C#)

Mediante el uso de la palabra clave `params`, puede especificar un [parámetro de método](method-parameters.md) que toma un número variable de argumentos.

Puede enviar una lista separada por comas de argumentos del tipo especificado en la declaración de parámetro o una matriz de argumentos del tipo especificado. También puede no enviar ningún argumento. Si no envía ningún argumento, la longitud de la lista `params` es cero.

No se permiten parámetros adicionales después de la palabra clave `params` en una declaración de método, y solo se permite una palabra clave `params` en una declaración de método.

El tipo declarado del parámetro `params` debe ser una matriz unidimensional, como se muestra en el ejemplo siguiente. En caso contrario, se produce un error del compilador [CS0225](../../misc/cs0225.md).

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
