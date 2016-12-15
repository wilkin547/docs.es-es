---
title: "C&#243;mo: Registrar excepciones en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "excepciones, registro"
  - "excepciones, seguimiento"
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Registrar excepciones en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede utilizar los objetos `My.Application.Log` y `My.Log` para registrar información sobre excepciones que se producen en la aplicación.  Estos ejemplos muestran cómo utilizar el método `My.Application.Log.WriteException` para registrar excepciones que detecta explícitamente y excepciones que no se controlan.  
  
 Para registrar información de traza, utilice el método `My.Application.Log.WriteEntry`.  Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
  
### Para registrar una excepción controlada  
  
1.  Cree el método que generará la información de excepción.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  Utilice un bloque `Try...Catch` para detectar la excepción.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  Coloque el código que podría generar una excepción en el bloque `Try`.  
  
     Quite los comentarios de las líneas `Dim` y `MsgBox` para provocar una excepción <xref:System.NullReferenceException>.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  En el bloque `Catch`, utilice el método `My.Application.Log.WriteException` para escribir la información de excepción.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     El ejemplo siguiente se muestra el código completo para registrar una excepción controlada.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### Para registrar una excepción no controlada  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, elija **Propiedades**.  
  
2.  Haga clic en la ficha **Aplicación**.  
  
3.  Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.  
  
     Así abre el archivo ApplicationEvents.vb.  
  
4.  Tenga abierto el archivo ApplicationEvents.vb en el Editor de código.  En el menú **General**, elija **Eventos de MyApplication**.  
  
5.  En el menú **Declaraciones**, elija **UnhandledException**.  
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> antes de que se ejecute la aplicación principal.  
  
6.  Agregue el método `My.Application.Log.WriteException` al controlador de eventos `UnhandledException`.  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     El ejemplo siguiente se muestra el código completo para registrar una excepción no controlada.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)