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
ms.openlocfilehash: d37a93343822d069295477958780c2b9c72043fa
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875466"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)

Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del ensamblado que contiene su declaración.  
  
## <a name="remarks"></a>Comentarios  

 En muchos casos, desea que los elementos de programación, como clases y estructuras, se usen en todo el ensamblado, no solo en el componente que los declara. Sin embargo, es posible que no desee que el código fuera del ensamblado tenga acceso a ellos (por ejemplo, si la aplicación es propietaria). Si desea limitar el acceso a un elemento de esta manera, puede declararlo mediante el `Friend` modificador.  
  
 El código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado pueden tener acceso a todos los `Friend` elementos de ese ensamblado.  
  
 `Friend` el acceso es a menudo el nivel preferido para los elementos de programación de una aplicación y `Friend` es el nivel de acceso predeterminado de una interfaz, un módulo, una clase o una estructura.  
  
 Solo se puede usar `Friend` en el nivel de módulo, interfaz o espacio de nombres. Por consiguiente, el contexto de la declaración de un `Friend` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura; no puede ser un procedimiento.  

> [!NOTE]
> También puede usar el modificador de acceso [Friend protegido](protected-friend.md) , que hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase. Para restringir el acceso a un miembro de dentro de su clase y de las clases derivadas en el mismo ensamblado, se utiliza el modificador de acceso [protegido privado](private-protected.md) .

 Para obtener una comparación de `Friend` y los demás modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
> Puede especificar que otro ensamblado es un ensamblado de confianza, lo que le permite tener acceso a todos los tipos y miembros marcados como `Friend` . Para más información, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).

## <a name="example"></a>Ejemplo  

 La siguiente clase usa el `Friend` modificador para permitir que otros elementos de programación del mismo ensamblado tengan acceso a determinados miembros.  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>Uso  

 Puede usar el `Friend` modificador en estos contextos:  
  
 [Instrucción Class](../statements/class-statement.md)  
  
 [Instrucción Const](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Delegate (Instrucción)](../statements/delegate-statement.md)  
  
 [Instrucción Dim](../statements/dim-statement.md)  
  
 [Instrucción Enum](../statements/enum-statement.md)  
  
 [Event (Instrucción)](../statements/event-statement.md)  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Instrucción Interface](../statements/interface-statement.md)  
  
 [Module (Instrucción)](../statements/module-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure (Instrucción)](../statements/structure-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Pública](public.md)
- [Contra](protected.md)
- [Privado](private.md)
- [Privado protegido](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedimientos](../../programming-guide/language-features/procedures/index.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
