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
ms.openlocfilehash: cf73f07b6e13d524281129e3c5d8dceceb90764c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867949"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)

Especifica que una propiedad o procedimiento no está implementado en esta clase y se debe invalidar en una clase derivada antes de que se pueda utilizar.  
  
## <a name="remarks"></a>Comentarios  

 Solo se puede usar `MustOverride` en una instrucción de declaración de propiedad o procedimiento. La propiedad o el procedimiento que especifica `MustOverride` debe ser miembro de una clase y la clase debe marcarse como [MustInherit](mustinherit.md).  
  
## <a name="rules"></a>Reglas  
  
- **Declaración incompleta.** Cuando se especifica `MustOverride` , no se proporcionan líneas de código adicionales para la propiedad o el procedimiento, ni siquiera la `End Function` instrucción, `End Property` o `End Sub` .  
  
- **Modificadores combinados.** No se puede especificar `MustOverride` junto con `NotOverridable` , `Overridable` o `Shared` en la misma declaración.  
  
- **Sombreado y reemplazos.** Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos. Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Términos alternativos.** Un elemento que no se puede usar excepto en una invalidación a veces se denomina elemento *virtual puro* .  
  
 El modificador `MustOverride` se puede utilizar en los contextos siguientes:  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [NotOverridable](notoverridable.md)
- [Overridable](overridable.md)
- [Invalidaciones](overrides.md)
- [MustInherit](mustinherit.md)
- [Palabras clave](../keywords/index.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
