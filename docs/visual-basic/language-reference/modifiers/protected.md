---
title: "Protected (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Protected"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Protected (modificador de acceso)"
  - "Protected Friend (combinación de palabras clave)"
  - "Protected (palabra clave)"
  - "Protected (palabra clave), y Friend"
  - "Protected (palabra clave), sintaxis"
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Protected (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica que sólo se puede obtener acceso a uno o varios elementos de programación declarados desde su propia clase o desde una clase derivada.  
  
## Comentarios  
 A veces un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, por lo que conviene limitar el acceso a dicho elemento.  Sin embargo, si la clase se puede heredar y se espera una jerarquía de clases derivadas, quizás sea necesario que estas clases derivadas tengan acceso a los datos y al código.  En este caso, deseará que se pueda tener acceso al elemento desde la clase base y desde todas las clases derivadas.  Para limitar el acceso a un elemento de este modo, puede declararlo con `Protected`.  
  
## Reglas  
  
-   **Contexto de la declaración.** Puede usar `Protected` sólo a nivel de clase.  Esto significa que el contexto de la declaración de un elemento `Protected` debe ser una clase, y no un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura ni un procedimiento.  
  
-   **Modificadores combinados.** Puede usar el modificador `Protected` junto con el modificador [Friend](../../../visual-basic/language-reference/modifiers/friend.md) en la misma declaración.  Esta combinación hace que se pueda obtener acceso a los elementos declarados desde cualquier punto del mismo ensamblado, desde su propia clase y desde las clases derivadas.  Sólo puede especificar `Protected Friend` en miembros de clases.  
  
## Comportamiento  
  
-   **Nivel de acceso.** Todo el código en una clase puede obtener acceso a sus elementos.  El código de cualquier clase que se derive de una clase base puede tener acceso a todos los elementos `Protected` de la clase base.  Esto es cierto para todos los niveles de derivación.  Esto significa que una clase puede tener acceso a los elementos `Protected` de la clase base de la clase base, etc.  
  
     El acceso protegido no es un supraconjunto ni un subconjunto del acceso de tipo amigo.  
  
-   **Modificadores de acceso.** Las palabras clave que especifican el nivel de acceso se llaman *modificadores de acceso*.  Encontrará una comparación de los modificadores de acceso en [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 El modificador `Protected` se puede utilizar en estos contextos:  
  
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
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)