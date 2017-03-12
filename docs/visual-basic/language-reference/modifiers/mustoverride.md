---
title: "MustOverride (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.MustOverride"
  - "MustOverride"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "elementos, virtuales puros"
  - "MustOverride (palabra clave)"
  - "reemplazar, MustOverride (palabra clave)"
  - "procedimientos, reemplazar"
  - "procedimientos, redefinir"
  - "propiedades [Visual Basic], reemplazar"
  - "propiedades [Visual Basic], redefinir"
  - "elementos virtuales puros"
  - "elementos virtuales, puros"
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# MustOverride (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una propiedad o procedimiento no se implementa en esta clase y debe reemplazarse en una clase derivada para poder utilizarse.  
  
## Comentarios  
 Sólo puede utilizarse `MustOverride` en una propiedad o instrucción de declaración de procedimiento.  La propiedad o el procedimiento que especifica `MustOverride` debe ser un miembro de una clase y ésta se debe marcar como [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## Reglas  
  
-   **Declaración incompleta.** Si especifica `MustOverride`, no proporciona líneas adicionales de código para la propiedad o el procedimiento, ni siquiera las instrucciones `End Function`, `End Property` o `End Sub`.  
  
-   **Modificadores combinados.** No se puede especificar `MustOverride` junto con `NotOverridable`, `Overridable` o `Shared` en la misma declaración.  
  
-   **Sombreado y reemplazo.** El sombreado y el reemplazo definen de nuevo un elemento heredado, pero existen diferencias significativas entre los dos enfoques.  Para obtener más información, vea [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
-   **Términos alternativos.** Un elemento que no se puede utilizar excepto en reemplazos se denomina en ocasiones elemento *virtual puro*.  
  
 El modificador `MustOverride` se puede utilizar en estos contextos:  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)