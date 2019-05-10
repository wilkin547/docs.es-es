---
title: MustOverride (Visual Basic)
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
ms.openlocfilehash: f5932b28c4664dd59dad829228f2186e78108af5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661240"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Especifica que una propiedad o procedimiento no se implementa en esta clase y se debe invalidar en una clase derivada antes de que se puede usar.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar `MustOverride` únicamente en una instrucción de declaración de procedimiento o propiedad. La propiedad o procedimiento que especifica `MustOverride` debe ser un miembro de una clase, y la clase debe marcarse [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Reglas  
  
- **Declaración incompleta.** Al especificar `MustOverride`, no proporciona líneas adicionales de código para la propiedad o procedimiento, no incluso la `End Function`, `End Property`, o `End Sub` instrucción.  
  
- **Modificadores combinados.** No puede especificar `MustOverride` junto con `NotOverridable`, `Overridable`, o `Shared` en la misma declaración.  
  
- **Sombrear y reemplazar.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Términos alternativos.** Un elemento que no se puede usar, excepto en una invalidación a veces se denomina un *pura virtual* elemento.  
  
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
