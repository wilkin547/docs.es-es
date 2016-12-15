---
title: "#Const (Directiva) | Microsoft Docs"
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
  - "vb.#Const"
  - "#vb.Const"
  - "#Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#Const (directiva)"
  - "compilación condicional, directivas"
  - "Const (directiva) (#Const)"
  - "Const (instrucción) [Visual Basic], #Const (directiva)"
  - "constantes, Const (directiva)"
  - "constantes, declarar"
  - "declarar constantes, #const (directiva)"
  - "compilador de Visual Basic, directivas de compilador"
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# #Const (Directiva)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Permite definir constantes de compilación condicional para Visual Basic.  
  
## Sintaxis  
  
```  
#Const constname = expression  
```  
  
## Elementos  
 `constname`  
 Obligatorio.  Nombre de la constante que se define.  
  
 `expression`  
 Obligatorio.  Literal, otra constante de compilación condicional o cualquier combinación que incluya operadores aritméticos o lógicos, excepto `Is`.  
  
## Comentarios  
 Las constantes de compilación condicional son siempre privadas para el archivo en que aparecen.  No es posible crear constantes de compilación públicas con la directiva `#Const`, esto sólo es posible en la interfaz de usuario o con la opción de compilador `/define`.  
  
 En `expression` solamente pueden utilizarse constantes de compilación condicional y literales.  El uso de una constante estándar definida con `Const` produce un error.  A la inversa, las constantes definidas con la palabra clave `#Const` solamente pueden utilizarse para la compilación condicional.  También es posible que las constantes no estén definidas, en cuyo caso su valor es `Nothing`.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la directiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## Vea también  
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)   
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)