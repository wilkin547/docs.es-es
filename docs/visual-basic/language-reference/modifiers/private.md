---
title: "Private (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Private"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Private (palabra clave)"
  - "Private (palabra clave), sintaxis"
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Private (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que sólo se puede tener acceso a uno o varios elementos de programación declarados desde el contexto de la declaración, incluidos todos los tipos que contiene.  
  
## Comentarios  
 Si un elemento de programación representa la funcionalidad de propiedad o contiene datos confidenciales, por lo general deseará limitar el acceso a este elemento con toda la rigurosidad que sea posible.  Para alcanzar la limitación máxima, permita únicamente que el módulo, la clase o la estructura que define el elemento tenga acceso a este elemento.  Para limitar el acceso a un elemento de este modo, puede declararlo con `Private`.  
  
## Reglas  
  
-   **Contexto de la declaración.** Sólo puede utilizar `Private` en el nivel de módulo.  Esto significa que el contexto de la declaración de un elemento `Private` debe ser un módulo, una clase o una estructura, y no un archivo de código fuente, un espacio de nombres, una interfaz o un procedimiento.  
  
## Comportamiento  
  
-   **Nivel de acceso.** Todo el código de un contexto de declaración puede tener acceso a sus elementos `Private`.  Esto incluye el código del tipo contenido, por ejemplo una clase anidada o una expresión de asignación de una enumeración.  Ningún código fuera del contexto de declaración puede tener acceso a sus elementos `Private`.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se llaman *modificadores de acceso*.  Encontrará una comparación de los modificadores de acceso en [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Private` se puede utilizar en estos contextos:  
  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)