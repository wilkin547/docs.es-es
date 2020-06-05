---
title: NotOverridable
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
ms.openlocfilehash: 463dd2454aafebf11554fb7bacdb73724c3130d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392163"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Especifica que una propiedad o un procedimiento no se pueden invalidar en una clase derivada.  
  
## <a name="remarks"></a>Observaciones  
 El `NotOverridable` modificador evita que una propiedad o un método se invalide en una clase derivada.  El modificador [Overridable](overridable.md) permite que una propiedad o un método de una clase se invalide en una clase derivada. Para más información, vea [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si `Overridable` `NotOverridable` no se especifica el modificador o, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base. Si la propiedad o el método reemplaza una propiedad o un método de clase base, el valor predeterminado es `Overridable` ; de lo contrario, es `NotOverridable` .  
  
 Un elemento que no se puede invalidar se denomina a veces elemento *sellado* .  
  
 Solo se puede usar `NotOverridable` en una instrucción de declaración de propiedad o procedimiento. Solo se puede especificar `NotOverridable` en una propiedad o un procedimiento que invalide otra propiedad o procedimiento, es decir, solo en combinación con `Overrides` .  
  
## <a name="combined-modifiers"></a>Modificadores combinados  
 No se puede especificar `Overridable` o `NotOverridable` para un `Private` método.  
  
 No se puede especificar `NotOverridable` junto con `MustOverride` , `Overridable` o `Shared` en la misma declaración.  
  
## <a name="usage"></a>Uso  
 El modificador `NotOverridable` se puede utilizar en los contextos siguientes:  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Modificadores](index.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [Overridable](overridable.md)
- [Invalidaciones](overrides.md)
- [Palabras clave](../keywords/index.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
