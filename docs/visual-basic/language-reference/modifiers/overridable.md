---
title: Overridable
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351401"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Especifica que una propiedad o un procedimiento se puede invalidar mediante una propiedad o un procedimiento con el mismo nombre en una clase derivada.  
  
## <a name="remarks"></a>Comentarios  
 El modificador `Overridable` permite que una propiedad o un método de una clase se invalide en una clase derivada. El modificador [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) evita que una propiedad o un método se invalide en una clase derivada.  Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si no se especifica el modificador `Overridable` o `NotOverridable`, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base. Si la propiedad o el método reemplaza una propiedad o un método de clase base, la configuración predeterminada es `Overridable`; de lo contrario, se `NotOverridable`.  
  
 Puede sombrear o reemplazar para volver a definir un elemento heredado, pero hay diferencias significativas entre los dos enfoques. Para obtener más información, vea [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Un elemento que se puede reemplazar se denomina a veces elemento *virtual* . Si se puede invalidar, pero no es necesario, a veces también se denomina elemento *concreto* .  
  
 Solo se puede usar `Overridable` en una instrucción de declaración de propiedad o procedimiento.  
  
## <a name="combined-modifiers"></a>Modificadores combinados  
 No se puede especificar `Overridable` ni `NotOverridable` para un método `Private`.  
  
 No se puede especificar `Overridable` junto con `MustOverride`, `NotOverridable`o `Shared` en la misma declaración.  
  
 Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.  
  
## <a name="usage"></a>Uso  
 El modificador `Overridable` se puede utilizar en los contextos siguientes:  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Modificadores](../../../visual-basic/language-reference/modifiers/index.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
