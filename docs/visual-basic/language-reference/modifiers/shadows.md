---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: e9a423fa69ad1dcd8c1d4a5b7085e5b5da548f93
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351260"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Especifica que un elemento de programación declarado vuelve a declarar y oculta un elemento con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.

## <a name="remarks"></a>Comentarios

El propósito principal de la sombra (que también se denomina *ocultar por nombre*) es conservar la definición de los miembros de clase. La clase base puede someterse a un cambio que crea un elemento con el mismo nombre que el que ya se ha definido. Si esto ocurre, el modificador `Shadows` fuerza las referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.

Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, vea [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Shadows` en el nivel de clase. Esto significa que el contexto de la declaración de un elemento `Shadows` debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

  Solo puede declarar un elemento de sombreado en una instrucción de declaración única.

- **Modificadores combinados.** No se puede especificar `Shadows` junto con `Overloads`, `Overrides`o `Static` en la misma declaración.

- **Tipos de elemento.** Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo. Si sombrea una propiedad o un procedimiento con otra propiedad o procedimiento, los parámetros y el tipo de valor devuelto no tienen que coincidir con los de la propiedad o el procedimiento de la clase base.

- **Acceso a.** Normalmente, el elemento sombreado de la clase base no está disponible en la clase derivada que lo sombrea. Sin embargo, se aplican las consideraciones siguientes.

  - Si el elemento de sombreado no es accesible desde el código que hace referencia a él, la referencia se resuelve en el elemento sombreado. Por ejemplo, si un elemento `Private` sombrea un elemento de clase base, el código que no tiene permiso para obtener acceso al elemento `Private` tiene acceso al elemento de clase base en su lugar.

  - Si sombrea un elemento, todavía puede tener acceso al elemento sombreado a través de un objeto declarado con el tipo de la clase base. También puede tener acceso a ella a través de `MyBase`.

El modificador `Shadows` se puede utilizar en los contextos siguientes:

- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)

- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)

- [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)

- [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)

- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)

- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)

- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Sobrecargas](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
