---
title: Procedimiento para registrar excepciones en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: ea2cad121a6722b2cb59e29831f90648ad4cff78
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664699"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a>Procedimiento para registrar excepciones en Visual Basic
Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre excepciones que se producen en la aplicación. Estos ejemplos muestran cómo usar el método `My.Application.Log.WriteException` para registrar excepciones que detecta explícitamente y excepciones que no se controlan.  
  
 Para registrar información de seguimiento, use el método `My.Application.Log.WriteEntry`. Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
  
### <a name="to-log-a-handled-exception"></a>Para registrar una excepción controlada  
  
1.  Cree el método que generará la información de excepción.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  Use un bloque `Try...Catch` para detectar la excepción.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  Coloque el código que podría generar una excepción en el bloque `Try`.  
  
     Quite la marca de comentario de las líneas `Dim` y `MsgBox` para generar una excepción <xref:System.NullReferenceException>.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  En el bloque `Catch`, use el método `My.Application.Log.WriteException` para escribir la información de excepción.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     En el ejemplo siguiente se muestra el código completo para registrar una excepción controlada.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a>Para registrar una excepción no controlada  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto** , elija **Propiedades**.  
  
2.  Haga clic en la pestaña **Aplicación** .  
  
3.  Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.  
  
     Se abre el archivo ApplicationEvents.vb.  
  
4.  Tenga el archivo ApplicationEvents.vb abierto en el Editor de código. En el menú **General** , elija **Eventos MyApplication**.  
  
5.  En el menú **Declaraciones**, pulse **UnhandledException**.  
  
     La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> antes de que se ejecute la aplicación principal.  
  
6.  Agregue el método `My.Application.Log.WriteException` al controlador de eventos `UnhandledException` .  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     En el siguiente ejemplo se muestra el código completo para registrar una excepción no controlada.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
