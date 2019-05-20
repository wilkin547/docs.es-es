---
title: '- operador: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 920981addd5c779c9ad1c666ef45e1de5cd23408
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633002"
---
# <a name="--operator-c-reference"></a>Operador - (Referencia de C#)

El operador `-` puede funcionar como un operador unario o binario.

## <a name="remarks"></a>Comentarios

Los operadores unarios `-` están predefinidos para todos los tipos numéricos. El resultado de una operación unaria `-` aplicada a un tipo numérico es la negación numérica del operando.

Los operadores binarios `-` están predefinidos para todos los tipos numéricos y de enumeración de modo que restan el segundo operando del primero.

Los tipos de delegado también proporcionan un operador `-` binario, que realiza la eliminación de delegados.

Los tipos definidos por el usuario pueden sobrecargar los operadores `-` unarios y `-` binarios. Para más información, consulte [operator keyword](../keywords/operator.md) (Palabra clave operator).

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
