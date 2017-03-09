---
title: "Public (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Public"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Public (modificador de acceso)"
  - "Public (palabra clave)"
  - "Public (palabra clave), sintaxis"
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Public (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que uno o varios elementos de programación declarados no tienen ninguna restricción de acceso.  
  
## Comentarios  
 Si publica un componente o conjunto de componentes, como una biblioteca de clases, deseará que los elementos de programación sean accesibles para todos los códigos que interactúan con su ensamblado.  Para otorgar este acceso ilimitado en un elemento, puede declararlo con `Public`.  
  
 El acceso público es el nivel normal para un elemento de programación cuando no necesita limitar su acceso.  Tenga en cuenta que el nivel de acceso de un elemento declarado dentro de una interfaz, módulo, clase o estructura es de forma predeterminada `Public` si no lo declara de otra forma.  
  
## Reglas  
  
-   **Contexto de la declaración.** Puede utilizar `Public` solamente en el nivel de módulo, interfaz o espacio de nombres.  Esto significa que el contexto de la declaración para un elemento `Public` debe ser un archivo de código fuente, espacio de nombres, interfaz, módulo, clase o estructura y no puede ser un procedimiento.  
  
## Comportamiento  
  
-   **Nivel de acceso.** Todos los códigos que pueden tener acceso a un módulo, clase o estructura pueden tener acceso a sus elementos `Public`.  
  
-   **Acceso predeterminado.** Las variables locales dentro de un procedimiento tienen un valor predeterminado de acceso público y no puede utilizar ningún modificador de acceso en ellos.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se llaman *modificadores de acceso*.  Encontrará una comparación de los modificadores de acceso en [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Public` se puede utilizar en estos contextos:  
  
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
  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)