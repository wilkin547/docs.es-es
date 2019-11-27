---
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 98f8ed947c9f4376c5778011a3a91ca8b094f9ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351562"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del ensamblado que contiene su declaración.  
  
## <a name="remarks"></a>Comentarios  
 En muchos casos, desea que los elementos de programación, como clases y estructuras, se usen en todo el ensamblado, no solo en el componente que los declara. Sin embargo, es posible que no desee que el código fuera del ensamblado tenga acceso a ellos (por ejemplo, si la aplicación es propietaria). Si desea limitar el acceso a un elemento de esta manera, puede declararlo mediante el modificador `Friend`.  
  
 El código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado pueden tener acceso a todos los elementos de `Friend` de ese ensamblado.  
  
 `Friend` acceso es a menudo el nivel preferido para los elementos de programación de una aplicación y `Friend` es el nivel de acceso predeterminado de una interfaz, un módulo, una clase o una estructura.  
  
 Solo puede usar `Friend` en el nivel de módulo, interfaz o espacio de nombres. Por consiguiente, el contexto de la declaración de un elemento `Friend` debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura; no puede ser un procedimiento.  

> [!NOTE]
> También puede usar el modificador de acceso [Friend protegido](protected-friend.md) , que hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase. Para restringir el acceso a un miembro de dentro de su clase y de las clases derivadas en el mismo ensamblado, se utiliza el modificador de acceso [protegido privado](private-protected.md) .

 Para obtener una comparación de `Friend` y los demás modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> Puede especificar que otro ensamblado es un ensamblado de confianza, lo que le permite tener acceso a todos los tipos y miembros marcados como `Friend`. Para más información, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).

## <a name="example"></a>Ejemplo  
 La siguiente clase usa el modificador `Friend` para permitir que otros elementos de programación del mismo ensamblado tengan acceso a determinados miembros.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Uso  
 Puede usar el modificador `Friend` en estos contextos:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
