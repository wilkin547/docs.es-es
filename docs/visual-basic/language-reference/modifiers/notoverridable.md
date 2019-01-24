---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: d2495e9d44a32e080d20deb4232ab27bfbd4051a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595817"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Especifica que una propiedad o procedimiento no puede reemplazarse en una clase derivada.  
  
## <a name="remarks"></a>Comentarios  
 El `NotOverridable` modificador evita que una propiedad o método que se invalida en una clase derivada.  El [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modificador permite que una propiedad o método en una clase que se invalide en una clase derivada. Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si el `Overridable` o `NotOverridable` modificador no se especifica, el valor predeterminado depende de si la propiedad o método invalida un método o propiedad de clase base. Si la propiedad o método reemplaza un método o propiedad de clase base, el valor predeterminado es `Overridable`; en caso contrario, es `NotOverridable`.  
  
 A veces se denomina un elemento que no se puede invalidar un *sealed* elemento.  
  
 Puede usar `NotOverridable` únicamente en una instrucción de declaración de procedimiento o propiedad. Puede especificar `NotOverridable` solo en una propiedad o procedimiento que reemplaza a otra propiedad o procedimiento, es decir, sólo en combinación con `Overrides`.  
  
## <a name="combined-modifiers"></a>Modificadores combinados  
 No puede especificar `Overridable` o `NotOverridable` para un `Private` método.  
  
 No puede especificar `NotOverridable` junto con `MustOverride`, `Overridable`, o `Shared` en la misma declaración.  
  
## <a name="usage"></a>Uso  
 El modificador `NotOverridable` se puede utilizar en los contextos siguientes:  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también
- [Modificadores](../../../visual-basic/language-reference/modifiers/index.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
