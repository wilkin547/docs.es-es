---
title: "Resume (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Resume"
  - "vb.ResumeNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Error (instrucción), y Resume (instrucción)"
  - "errores [Visual Basic], reanudar cuando"
  - "ejecución"
  - "ejecución, reanudar"
  - "Next (instrucción), Resume"
  - "Resume Next (instrucción)"
  - "Resume (instrucción)"
  - "Resume (instrucción), sintaxis"
  - "errores en tiempo de ejecución, reanudar cuando"
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Resume (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Reanuda la ejecución cuando finaliza una rutina de control de errores.  
  
 Recomendamos que utilice el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y las instrucciones de `On Error` y de `Resume` .  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Sintaxis  
  
```  
Resume [ Next | line ]  
```  
  
## Elementos  
 `Resume`  
 Obligatorio.  Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución continúa con la instrucción que causó el error.  Si se produjo en un procedimiento llamado, la ejecución continúa en la última instrucción que realizó una llamada al exterior del procedimiento que contiene la rutina de control de errores.  
  
 `Next`  
 Opcional.  Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución continúa con la instrucción siguiente a la que causó el error.  Si el error se produjo en un procedimiento llamado, la ejecución continúa en la instrucción siguiente a la que realizó por última vez la llamada fuera del procedimiento que contiene la rutina de control de errores \(o la instrucción `On Error Resume Next`\).  
  
 `line`  
 Opcional.  La ejecución continúa en la línea especificada en el argumento `line` requerido.  El argumento `line` es una etiqueta de línea o un número de línea, y debe estar en el mismo procedimiento que el controlador de errores.  
  
## Comentarios  
  
> [!NOTE]
>  Se recomienda usar el control estructurado de excepciones en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y las instrucciones de `On Error` y de `Resume` .  Para obtener más información, vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Si se utiliza una instrucción `Resume` fuera de una rutina de controlador de errores, se producirá un error.  
  
 La instrucción `Resume` no se puede utilizar en un procedimiento que contenga una instrucción `Try...Catch...Finally`.  
  
## Ejemplo  
 En este ejemplo se utiliza la instrucción `Resume` para finalizar el controlador de errores en un procedimiento y, a continuación, reanudar la ejecución con la instrucción que provocó el error.  Para ilustrar el uso de la instrucción `Resume` se genera el error número 55.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/resume-statement_1.vb)]  
  
## Requisitos  
 **Espacio de nombres:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** biblioteca en tiempo de ejecución de Visual Basic \(en Microsoft.VisualBasic.dll\)  
  
## Vea también  
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Error \(Instrucción\)](../../../visual-basic/language-reference/statements/error-statement.md)   
 [On Error \(Instrucción\)](../../../visual-basic/language-reference/statements/on-error-statement.md)