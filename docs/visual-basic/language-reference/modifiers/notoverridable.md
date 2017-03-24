---
title: "NotOverridable (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.NotOverridable"
  - "NotOverridable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elementos, sellado"
  - "métodos [Visual Basic], sellado"
  - "NotOverridable (palabra clave)"
  - "reemplazar"
  - "procedimientos, reemplazar"
  - "procedimientos, redefinir"
  - "propiedades [Visual Basic], reemplazar"
  - "propiedades [Visual Basic], redefinir"
  - "elementos sellados"
  - "métodos sellados"
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# NotOverridable (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una propiedad o un procedimiento no se puede reemplazar en una clase derivada.  
  
## Comentarios  
 El modificador de `NotOverridable` evita que una propiedad o un método se invalide en una clase derivada.  El modificador de [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) permite una propiedad o un método de una clase que se invalide en una clase derivada.  Para obtener más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Si no se especifica el modificador de `Overridable` o de `NotOverridable` , la configuración predeterminada depende de si la propiedad o el método reemplaza una propiedad o un método de clase base.  Si la propiedad o el método reemplaza una propiedad o un método de clase base, la configuración predeterminada es `Overridable`; de lo contrario, es `NotOverridable`.  
  
 Un elemento que no se puede reemplazar se denomina en ocasiones elemento *sellado*.  
  
 Sólo puede utilizarse `NotOverridable` en una propiedad o instrucción de declaración de procedimiento.  Sólo puede especificar `NotOverridable` en una propiedad o procedimiento que reemplaza otra propiedad o procedimiento, es decir, sólo en combinación con `Overrides`.  
  
## modificadores combinados  
 No puede especificar `Overridable` o `NotOverridable` para un método de `Private` .  
  
 No se puede especificar `NotOverridable` junto con `MustOverride`, `Overridable` o `Shared` en la misma declaración.  
  
## Uso  
 El modificador `NotOverridable` se puede utilizar en estos contextos:  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Modificadores](../../../visual-basic/language-reference/modifiers/index.md)   
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)