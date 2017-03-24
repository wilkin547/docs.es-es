---
title: "Overridable (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Overridable"
  - "vb.Overridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elementos concretos"
  - "elementos, concretos"
  - "elementos, virtual"
  - "Overridable (palabra clave)"
  - "reemplazar, Overridable (palabra clave)"
  - "procedimientos, reemplazar"
  - "procedimientos, redefinir"
  - "propiedades [Visual Basic], reemplazar"
  - "propiedades [Visual Basic], redefinir"
  - "elementos virtuales"
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Overridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una propiedad o procedimiento se puede reemplazar por una propiedad o procedimiento con nombre idéntico de una clase derivada.  
  
## Comentarios  
 El modificador de `Overridable` permite una propiedad o un método de una clase que se invalide en una clase derivada.  El modificador de [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) evita que una propiedad o un método se invalide en una clase derivada.  Para obtener más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si no se especifica el modificador de `Overridable` o de `NotOverridable` , la configuración predeterminada depende de si la propiedad o el método reemplaza una propiedad o un método de clase base.  Si la propiedad o el método reemplaza una propiedad o un método de clase base, la configuración predeterminada es `Overridable`; de lo contrario, es `NotOverridable`.  
  
 Puede sombrear o invalidar para definir de nuevo un elemento heredado, pero hay diferencias significativas entre los dos enfoques.  Para obtener más información, vea [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Un elemento que se puede reemplazar se denomina en ocasiones elemento *virtual*.  Si se puede reemplazar, pero no tiene que reemplazarse, en ocasiones también se denomina elemento *concreto*.  
  
 Sólo puede utilizarse `Overridable` en una propiedad o instrucción de declaración de procedimiento.  
  
## modificadores combinados  
 No puede especificar `Overridable` o `NotOverridable` para un método de `Private` .  
  
 No se puede especificar `Overridable` junto con `MustOverride`, `NotOverridable` o `Shared` en la misma declaración.  
  
 Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.  
  
## Uso  
 El modificador `Overridable` se puede utilizar en estos contextos:  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Modificadores](../../../visual-basic/language-reference/modifiers/index.md)   
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)