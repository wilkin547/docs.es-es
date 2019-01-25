---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: e879819d945f3e7256edd34e87b9cae4a04c0829
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512741"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)
Especifica que un elemento de programación declarado vuelve a declarar y oculta un elemento con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.  
  
## <a name="remarks"></a>Comentarios  
 El propósito principal de sombreado (también conocido como *ocultar por nombre*) consiste en conservar la definición de los miembros de clase. La clase base puede sufrir un cambio que se crea un elemento con el mismo nombre que ya ha definido. Si esto ocurre, el `Shadows` modificador fuerza hace referencia a través de su clase se resuelvan en el miembro está definido, en lugar de para el nuevo elemento de la clase base.  
  
 Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de declaración.** Puede usar `Shadows` sólo en el nivel de clase. Esto significa que el contexto de declaración de un `Shadows` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.  
  
     Puede declarar un único elemento sombreado en una única instrucción de declaración.  
  
-   **Modificadores combinados.** No puede especificar `Shadows` junto con `Overloads`, `Overrides`, o `Static` en la misma declaración.  
  
-   **Tipos de elemento.** Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo. Si sombrea una propiedad o procedimiento con otra propiedad o procedimiento, los parámetros y el tipo de valor devuelto no es necesario para que coincida con los de la propiedad de clase base o el procedimiento.  
  
-   **Acceso a.** El elemento sombreado en la clase base está disponible normalmente desde dentro de la clase derivada que lo reemplaza. Sin embargo, se aplican las consideraciones siguientes.  
  
    -   Si el elemento reemplazado no es accesible desde el código que hace referencia a él, la referencia se resuelve en el elemento sombreado. Por ejemplo, si un `Private` elemento oculta o prevalece sobre un elemento de clase base, el código que no tiene permiso para tener acceso a la `Private` elemento tiene acceso al elemento de clase base en su lugar.  
  
    -   Ocultar un elemento, es posible acceder el elemento sombreado a través de un objeto declarado con el tipo de la clase base. También puede acceder a través de `MyBase`.  
  
 El modificador `Shadows` se puede utilizar en los contextos siguientes:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
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
