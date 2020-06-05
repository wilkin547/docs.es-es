---
title: Invalidaciones
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392033"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)

Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Overrides` en una instrucción de declaración de propiedad o procedimiento.

- **Modificadores combinados.** No se puede especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración. Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.

- **Firmas coincidentes.** La firma de esta declaración debe coincidir exactamente con la *firma* de la propiedad o el procedimiento que reemplaza. Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.

  Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:

  - El nivel de acceso.

  - El tipo de valor devuelto, si lo hay.

- **Firmas genéricas.** En los procedimientos genéricos, la firma incluye el número de parámetros de tipo. Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.

- **Coincidencia adicional.** Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:

  - Modificador de nivel de acceso (por ejemplo, [Public](public.md))

  - Mecanismo de paso de cada parámetro ([ByVal](byval.md) o [ByRef](byref.md))

  - Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.

- **Sombreado y reemplazos.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.

El modificador `Overrides` se puede utilizar en los contextos siguientes:

- [Instrucción Function](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Instrucción Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Consulte también

- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overridable](overridable.md)
- [Palabras clave](../keywords/index.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
