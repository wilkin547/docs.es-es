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
Especifica que una propiedad o procedimiento no está implementado en esta clase y se debe invalidar en una clase derivada antes de que se pueda utilizar.  
  
## <a name="remarks"></a>Comentarios  
 Solo se puede usar `MustOverride` en una instrucción de declaración de propiedad o procedimiento. La propiedad o el procedimiento que especifica `MustOverride` debe ser miembro de una clase y la clase debe marcarse como [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Reglas  
  
- **Declaración incompleta.** Cuando se especifica `MustOverride`, no se proporcionan líneas de código adicionales para la propiedad o el procedimiento, ni siquiera la instrucción `End Function`, `End Property`o `End Sub`.  
  
- **Modificadores combinados.** No se puede especificar `MustOverride` junto con `NotOverridable`, `Overridable`o `Shared` en la misma declaración.  
  
- **Sombrear e invalidar.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, vea [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Términos alternativos.** Un elemento que no se puede usar excepto en una invalidación a veces se denomina elemento *virtual puro* .  
  
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
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
