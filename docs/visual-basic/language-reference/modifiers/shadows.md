---
title: "Shadows (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shadows"
  - "shadows"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "nombres duplicados"
  - "nombres, sombrear"
  - "ámbito, sombrear"
  - "sombrear"
  - "Shadows (palabra clave)"
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shadows (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que un elemento de programación declarado vuelve a declarar y oculta un elemento denominado de forma idéntica o un conjunto de elementos sobrecargados, en una clase base.  
  
## Comentarios  
 El propósito principal del sombreado \(que también se conoce como *ocultar por nombre*\) es conservar la definición de los miembros de clase.  La clase base puede sufrir un cambio que cree un elemento con el mismo nombre que otro ya definido.  Si sucede esto, el modificador `Shadows` fuerza a referencias a través de la clase para que se resuelvan en el miembro definido en lugar de hacerlo en el nuevo elemento de la clase base.  
  
 El sombreado y el reemplazo definen de nuevo un elemento heredado, pero existen diferencias significativas entre los dos enfoques.  Para obtener más información, vea [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## Reglas  
  
-   **Contexto de la declaración.** Sólo puede utilizar `Shadows` en el nivel de clase.  Esto significa que el contexto de la declaración para un elemento `Shadows` debe ser una clase, y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.  
  
     Se puede declarar sólo un elemento de sombreado en una única instrucción de declaración.  
  
-   **Modificadores combinados.** No se puede especificar `Shadows` junto con `Overloads`, `Overrides` o `Static` en la misma declaración.  
  
-   **Tipos de elementos.** Puede hacer que cualquier tipo de elemento declarado prevalezca sobre cualquier otro tipo.  Si sombrea una propiedad o procedimiento con otra propiedad o procedimiento, los parámetros y el tipo de valor devuelto no tienen que coincidir con los de la propiedad o procedimiento de la clase base.  
  
-   **Acceso.** El elemento sombreado en la clase base no está disponible normalmente desde la clase derivada que lo sombrea.  No obstante, se aplican las siguientes consideraciones.  
  
    -   Si el elemento de sombreado no es accesible desde el código que hace referencia a él, la referencia se resuelve como el elemento sombreado.  Por ejemplo, si un elemento `Private` sombrea un elemento de clase base, el código que no tiene el permiso para obtener acceso al elemento `Private` obtiene acceso al elemento de clase base.  
  
    -   Si se sombrea un elemento, aún se podrá tener acceso al mismo mediante un objeto declarado con el tipo de la clase base.  También puede tener acceso a él a través de `MyBase`.  
  
 El modificador `Shadows` se puede utilizar en estos contextos:  
  
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
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)