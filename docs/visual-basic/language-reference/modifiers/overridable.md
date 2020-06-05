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
ms.openlocfilehash: dcbabde8464dd8a0ce5fad24d7d72b1e780270d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392124"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Especifica que una propiedad o un procedimiento se puede invalidar mediante una propiedad o un procedimiento con el mismo nombre en una clase derivada.  
  
## <a name="remarks"></a>Observaciones  
 El `Overridable` modificador permite que una propiedad o un método de una clase se invalide en una clase derivada. El modificador [NotOverridable](notoverridable.md) evita que una propiedad o un método se invalide en una clase derivada.  Para más información, vea [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si `Overridable` `NotOverridable` no se especifica el modificador o, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base. Si la propiedad o el método reemplaza una propiedad o un método de clase base, el valor predeterminado es `Overridable` ; de lo contrario, es `NotOverridable` .  
  
 Puede sombrear o reemplazar para volver a definir un elemento heredado, pero hay diferencias significativas entre los dos enfoques. Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
 Un elemento que se puede reemplazar se denomina a veces elemento *virtual* . Si se puede invalidar, pero no es necesario, a veces también se denomina elemento *concreto* .  
  
 Solo se puede usar `Overridable` en una instrucción de declaración de propiedad o procedimiento.  
  
## <a name="combined-modifiers"></a>Modificadores combinados  
 No se puede especificar `Overridable` o `NotOverridable` para un `Private` método.  
  
 No se puede especificar `Overridable` junto con `MustOverride` , `NotOverridable` o `Shared` en la misma declaración.  
  
 Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.  
  
## <a name="usage"></a>Uso  
 El modificador `Overridable` se puede utilizar en los contextos siguientes:  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Modificadores](index.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Invalidaciones](overrides.md)
- [Palabras clave](../keywords/index.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
