---
title: "C&#243;mo: Registrar mensajes cuando se inicia o se cierra la aplicaci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "registros de eventos, cerrar"
  - "My.Application.Log (objeto), registrar"
  - "Startup (evento)"
  - "registros de eventos, iniciar"
  - "Shutdown (evento)"
  - "My.Log (objeto), registrar"
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Registrar mensajes cuando se inicia o se cierra la aplicaci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación. En este ejemplo se muestra cómo usar el método `My.Application.Log.WriteEntry` con los eventos `Startup` y `Shutdown` para escribir información de seguimiento.  
  
### Para acceder a código de controlador de eventos de la aplicación  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, elija **Propiedades**.  
  
2.  Haga clic en la pestaña **Aplicación**.  
  
3.  Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.  
  
     Se abre el archivo ApplicationEvents.vb.  
  
### Para registrar mensajes cuando se inicia la aplicación  
  
1.  Tenga el archivo ApplicationEvents.vb abierto en el Editor de código. En el menú **General**, elija **Eventos MyApplication**.  
  
2.  En el menú **Declaraciones**, elija **Inicio**.  
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> antes de que se ejecute la aplicación principal.  
  
3.  Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Startup`.  
  
     [!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]  
  
### Para registrar mensajes cuando se cierra la aplicación  
  
1.  Tenga el archivo ApplicationEvents.vb abierto en el Editor de código. En el menú **General**, elija **Eventos MyApplication**.  
  
2.  En el **declaraciones** menú, elija **Apagar**.  
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> después de la ejecución de la aplicación principal, pero antes del cierre.  
  
3.  Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Shutdown`.  
  
     [!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]  
  
## Ejemplo  
 Puede usar el **Diseñador de proyectos** para acceder a los eventos de aplicación en el Editor de código. Para obtener más información, consulta [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)