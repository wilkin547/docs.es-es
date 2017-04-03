---
title: "Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event
- event logs, startup
- Shutdown event
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 12e99815d1fd1b9c57706653e41a360802a6d80c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a>Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación (Visual Basic)
Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación. En este ejemplo se muestra cómo usar el método `My.Application.Log.WriteEntry` con los eventos `Startup` y `Shutdown` para escribir información de seguimiento.  
  
### <a name="to-access-the-applications-event-handler-code"></a>Para acceder a código de controlador de eventos de la aplicación  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto** , elija **Propiedades**.  
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.  
  
     Se abre el archivo ApplicationEvents.vb.  
  
### <a name="to-log-messages-when-the-application-starts"></a>Para registrar mensajes cuando se inicia la aplicación  
  
1.  Tenga el archivo ApplicationEvents.vb abierto en el Editor de código. En el menú **General** , elija **Eventos MyApplication**.  
  
2.  En el menú **Declaraciones** , elija **Inicio**.  
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> antes de que se ejecute la aplicación principal.  
  
3.  Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Startup` .  
  
     [!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a>Para registrar mensajes cuando se cierra la aplicación  
  
1.  Tenga el archivo ApplicationEvents.vb abierto en el Editor de código. En el menú **General** , elija **Eventos MyApplication**.  
  
2.  En el **declaraciones** menú, elija **Apagar**.  
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> después de que se ejecute la aplicación principal, pero antes de que se cierre.  
  
3.  Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Shutdown` .  
  
     [!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Puede usar el **Diseñador de proyectos** para acceder a los eventos de aplicación en el Editor de código. Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [Página de aplicación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
