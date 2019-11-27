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
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351381"
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

  - Modificador de nivel de acceso (por ejemplo, [Public](../../../visual-basic/language-reference/modifiers/public.md))

  - Mecanismo de paso de cada parámetro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))

  - Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.

- **Sombrear e invalidar.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, vea [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.

El modificador `Overrides` se puede utilizar en los contextos siguientes:

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
