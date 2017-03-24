---
title: "Friend (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Friend"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Friend (palabra clave)"
  - "Friend (modificador de acceso)"
  - "palabra clave Friend, sintaxis"
  - "Protected Friend (combinación de palabras clave)"
  - "palabra clave Friend, y Protected"
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Friend (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que solo se puede obtener acceso a uno o varios elementos de programación declarados desde dentro del ensamblado que contiene su declaración.  
  
## Comentarios  
 En numerosas ocasiones deseará que elementos de programación como clases y estructuras se utilicen en todo el ensamblado y no sólo en el componente en que se declaran.  Sin embargo, es posible que no se desee sea accesible por código fuera del ensamblado \(por ejemplo, si la aplicación es propietaria\).  Si desea restringir el acceso a un elemento de esta manera, puede declararla utilizando el modificador de `Friend`.  
  
 El código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado puede tener acceso a todos los elementos `Friend` de dicho ensamblado.  
  
 el acceso de `Friend` suele ser el nivel preferido para los elementos de programa de aplicación, y `Friend` es el nivel de acceso predeterminado de una interfaz, un módulo, una clase, o una estructura.  
  
 Puede utilizar `Friend` sólo en el módulo, la interfaz, o el nivel de espacio de nombres.  Por consiguiente, el contexto de declaración para un elemento de `Friend` debe ser un archivo de código fuente, un espacio de nombres, una interfaz, módulo, clase o estructura; no puede ser un procedimiento.  
  
 Puede utilizar el modificador `Friend` junto con el modificador [Protected](../../../visual-basic/language-reference/modifiers/protected.md) en la misma declaración.  Esta combinación consulta tanto acceso de `Friend` y acceso protegido a los elementos declarados, por lo que son accesibles desde cualquier parte del mismo ensamblado, su propia clase, y clases derivadas.  Sólo puede especificar `Protected Friend` en miembros de clases.  
  
 Para una comparación de `Friend` y los otros modificadores de acceso, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
> [!NOTE]
>  Puede especificar que otro ensamblado es un ensamblado de confianza, que permite tener acceso a todos los tipos y miembros que están marcadas como `Friend`.  Para obtener más información, vea [Ensamblados de confianza](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Ejemplo  
 La siguiente clase usa el modificador `Friend` para permitir a otros elementos de programación dentro del mismo ensamblado tener acceso a ciertos miembros.  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## Uso  
 Puede utilizar el modificador de `Friend` en estos contextos:  
  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)