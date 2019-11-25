---
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351490"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.  
  
## <a name="remarks"></a>Comentarios  
 You can use `MustOverride` only in a property or procedure declaration statement. The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Reglas  
  
- **Incomplete Declaration.** When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.  
  
- **Combined Modifiers.** You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.  
  
- **Shadowing and Overriding.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Alternate Terms.** An element that cannot be used except in an override is sometimes called a *pure virtual* element.  
  
 El modificador `MustOverride` se puede utilizar en los contextos siguientes:  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
