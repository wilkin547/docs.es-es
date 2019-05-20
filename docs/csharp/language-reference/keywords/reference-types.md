---
title: 'Tipos de referencia: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 4b3b1d5b27c3f6a88ce752243ab2d1389b168f0e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634061"
---
# <a name="reference-types-c-reference"></a>Tipos de referencia (referencia de C#)

Hay dos clases de tipos en C#: tipos de referencia y tipos de valor. Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos. Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable. Con los tipos de valor, cada variable tiene su propia copia de los datos, y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso de las variables de parámetro in, ref y out, consulte el modificador de parámetro [in](in-parameter-modifier.md), [ref](ref.md) y [out](out-parameter-modifier.md)).

 Las palabras clave siguientes se usan para declarar tipos de referencia:

- [class](class.md)

- [interface](interface.md)

- [delegate](delegate.md)

 C# también proporciona los siguientes tipos de referencia integrados:

- [dynamic](dynamic.md)

- [object](object.md)

- [string](string.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tipos](types.md)
- [Tipos de valor](value-types.md)
