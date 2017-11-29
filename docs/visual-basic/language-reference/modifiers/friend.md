---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32f993e4b9bcd126ebb6d70310fc0781e8b137b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro del ensamblado que contiene su declaración.  
  
## <a name="remarks"></a>Comentarios  
 En muchos casos, desea que elementos de programación como las clases y estructuras que se usará en todo el ensamblado, no solo por el componente que se declara. Sin embargo, no conviene que sean accesibles para el código fuera del ensamblado (por ejemplo, si la aplicación es propietaria). Si desea limitar el acceso a un elemento de esta manera, puede declarar mediante el `Friend` modificador.  
  
 Código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado puede tener acceso a toda la `Friend` elementos en ese ensamblado.  
  
 `Friend`acceso a menudo es el nivel preferido para elementos de programación de la aplicación, y `Friend` es el acceso predeterminado de una interfaz, un módulo, una clase o una estructura.  
  
 Puede usar `Friend` en el nivel de módulo, interfaz o espacio de nombres. Por lo tanto, el contexto de la declaración de un `Friend` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura; no puede ser un procedimiento.  
  
 Puede usar el `Friend` modificador junto con el [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modificador en la misma declaración. Esta combinación de ambos confiere `Friend` acceso y acceso protegido a los elementos declarados, para que sean accesibles desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas. Puede especificar `Protected Friend` solo en los miembros de clases.  
  
 Para obtener una comparación de `Friend` y otros modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Puede especificar que el otro ensamblado es un ensamblado de confianza, lo que le permite tener acceso a todos los tipos y miembros que están marcados como `Friend`. Para más información, vea [Ensamblados de confianza](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
## <a name="example"></a>Ejemplo  
 La siguiente clase utiliza el `Friend` modificador para permitir que otros elementos de programación dentro del mismo ensamblado para tener acceso a ciertos miembros.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a>Uso  
 Puede usar el `Friend` modificador en estos contextos:  
  
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
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
