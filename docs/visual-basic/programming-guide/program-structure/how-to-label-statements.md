---
title: "C&#243;mo: Aplicar etiquetas a las instrucciones (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "carácter separador :"
  - "dos puntos (:)"
  - "instrucciones [Visual Basic], etiquetas"
  - "código de Visual Basic, etiquetar instrucciones"
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# C&#243;mo: Aplicar etiquetas a las instrucciones (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los bloques de instrucciones están formados por líneas de código delimitadas por dos puntos.  Las líneas de código precedidas por una cadena o número entero identificador se denominan *etiquetadas*.  Las etiquetas de instrucciones se utilizan para marcar una línea de código e identificarla para su utilización en instrucciones del tipo `On Error Goto`.  
  
 Las etiquetas pueden ser cualquier Visual Basic válido identificadores de mientras los que identifican la que identifican literales enteros.  Las etiquetas deben aparecen al principio de una línea de código fuente y deben ir seguidas de un signo dos puntos, independientemente de si van seguidas de una instrucción en la misma línea.  
  
 El compilador identifica las etiquetas al comprobar si el principio de la línea coincide con un identificador ya definido.  Si no es así, el compilador dará por hecho que se trata de una etiqueta.  
  
 Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores.  El ámbito de una etiqueta es el cuerpo del método.  La declaración de etiqueta tiene prioridad en cualquier situación ambigua.  
  
> [!NOTE]
>  Las etiquetas sólo se pueden utilizar en instrucciones ejecutables dentro de métodos.  
  
### Para etiquetar una línea de código.  
  
-   Coloque un identificador, seguido de dos puntos, al principio de la línea de código fuente.  
  
     Por ejemplo, a las siguientes líneas de código se les han asignado las etiquetas `Jump` y `120`, respectivamente:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## Vea también  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)