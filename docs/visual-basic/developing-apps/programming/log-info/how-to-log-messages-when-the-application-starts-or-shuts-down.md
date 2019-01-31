---
title: Procedimiento para registrar mensajes cuando se inicia o se cierra la aplicación (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: 20eabd08db0763ec08bb28add41ff63fa3196dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585635"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a>Procedimiento para registrar mensajes cuando se inicia o se cierra la aplicación (Visual Basic)
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
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> después de la ejecución de la aplicación principal, pero antes del cierre.  
  
3.  Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Shutdown` .  
  
     [!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Puede usar el **Diseñador de proyectos** para acceder a los eventos de aplicación en el Editor de código. Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 [!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Página de aplicación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
