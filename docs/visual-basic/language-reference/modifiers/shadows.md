---
description: 'Más información acerca de: Shadows (Visual Basic)'
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
ms.openlocfilehash: 4a455a78c36e15db977936b81c22e7a5b03d107e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700850"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Especifica que un elemento de programación declarado vuelve a declarar y oculta un elemento con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.

## <a name="remarks"></a>Observaciones

El propósito principal de la sombra (que también se denomina *ocultar por nombre*) es conservar la definición de los miembros de clase. La clase base puede someterse a un cambio que crea un elemento con el mismo nombre que el que ya se ha definido. Si esto ocurre, el `Shadows` modificador fuerza las referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.

Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `Shadows` en el nivel de clase. Esto significa que el contexto de la declaración de un `Shadows` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.

  Solo puede declarar un elemento de sombreado en una instrucción de declaración única.

- **Modificadores combinados.** No se puede especificar `Shadows` junto con `Overloads` , `Overrides` o `Static` en la misma declaración.

- **Tipos de elemento.** Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo. Si sombrea una propiedad o un procedimiento con otra propiedad o procedimiento, los parámetros y el tipo de valor devuelto no tienen que coincidir con los de la propiedad o el procedimiento de la clase base.

- **Acceso a.** Normalmente, el elemento sombreado de la clase base no está disponible en la clase derivada que lo sombrea. Sin embargo, se aplican las consideraciones siguientes.

  - Si el elemento de sombreado no es accesible desde el código que hace referencia a él, la referencia se resuelve en el elemento sombreado. Por ejemplo, si un `Private` elemento sombrea un elemento de clase base, el código que no tiene permiso para obtener acceso al elemento de `Private` la clase base en su lugar.

  - Si sombrea un elemento, todavía puede tener acceso al elemento sombreado a través de un objeto declarado con el tipo de la clase base. También puede tener acceso a ella a través de `MyBase` .

El modificador `Shadows` se puede utilizar en los contextos siguientes:

- [Instrucción Class](../statements/class-statement.md)

- [Instrucción Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Delegate (Instrucción)](../statements/delegate-statement.md)

- [Instrucción Dim](../statements/dim-statement.md)

- [Instrucción Enum](../statements/enum-statement.md)

- [Event (Instrucción)](../statements/event-statement.md)

- [Instrucción Function](../statements/function-statement.md)

- [Instrucción Interface](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Structure (Instrucción)](../statements/structure-statement.md)

- [Instrucción Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vea también

- [Compartido](shared.md)
- [Estática](static.md)
- [Privado](private.md)
- [Me, My, MyBase y MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Sobrecargas](overloads.md)
- [Overridable](overridable.md)
- [Invalidaciones](overrides.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
