---
title: "Se deshabilit&#243; la evaluaci&#243;n de funciones porque se excedi&#243; el tiempo de espera de una evaluaci&#243;n de funciones anterior | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30957"
  - "vbc30957"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30957"
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Se deshabilit&#243; la evaluaci&#243;n de funciones porque se excedi&#243; el tiempo de espera de una evaluaci&#243;n de funciones anterior
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se deshabilitó la evaluación de funciones porque se excedió el tiempo de espera de una evaluación de funciones anteriorPara volver a habilitar la evaluación de funciones, vuelva a intentarlo o reinicie la depuración.  
  
 En el depurador de Visual Studio, una expresión especifica una llamada a procedimiento, pero otra evaluación ha agotado de tiempo de espera.  
  
 Las posibles causas para que una llamada a procedimiento supere el tiempo de espera incluyen un bucle infinito o *bucle sin fin*.  Para obtener más información, vea [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Un caso especial de bucle infinito es la *recursividad*.  Para obtener más información, vea [Procedimientos recursivos](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Identificador de error:** BC30957  
  
### Para corregir este error  
  
1.  Si es posible, determine cuál era la evaluación de función anterior y lo que lo produjo que se superara el tiempo de espera.  De lo contrario, podría encontrar de nuevo este error.  
  
2.  O bien, ejecute paso a paso de nuevo el depurador, o finalice y reinicie la depuración.  
  
## Vea también  
 [Depurar en Visual Studio](/visual-studio/debugger/debugging-in-visual-studio)   
 [Desplazarse por el código con el depurador](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [Expresiones en Visual Basic](../Topic/Expressions%20in%20Visual%20Basic.md)