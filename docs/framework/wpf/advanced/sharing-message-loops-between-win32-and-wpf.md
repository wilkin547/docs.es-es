---
title: Compartir bucles de mensajes entre Win32 y WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dcf8baa87038bc5625d46968b39d759daae25cbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Compartir bucles de mensajes entre Win32 y WPF
Este tema describe cómo implementar un bucle de mensajes para la interoperación con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], ya sea mediante existente mensaje exposición de bucle en <xref:System.Windows.Threading.Dispatcher> o mediante la creación de un bucle de mensajes independiente en el [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] lado de su código de interoperación.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher y el bucle de mensajes  
 Un escenario normal para la compatibilidad con eventos de interoperación y teclado consiste en implementar <xref:System.Windows.Interop.IKeyboardInputSink>, o para crear subclases de clases que ya implementan <xref:System.Windows.Interop.IKeyboardInputSink>, como <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>. Sin embargo, la compatibilidad con el receptor de teclado no abordar las necesidades de bucle de mensajes posibles que tenga al enviar y recibir mensajes a través de los límites de interoperación. Para ayudar a formalizar una arquitectura de bucle de mensajes de aplicación, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona el <xref:System.Windows.Interop.ComponentDispatcher> (clase), que define un protocolo simple de un bucle de mensajes debe seguir.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>es una clase estática que expone a varios miembros. El ámbito de cada método implícitamente está asociado al subproceso que realiza la llamada. Un bucle de mensajes debe llamar a algunas de ellas [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] en los momentos críticos (según se define en la sección siguiente).  
  
 <xref:System.Windows.Interop.ComponentDispatcher>Proporciona eventos que pueden escuchar otros componentes (por ejemplo, el receptor de teclado). El <xref:System.Windows.Threading.Dispatcher> llamadas todos los controles de la clase <xref:System.Windows.Interop.ComponentDispatcher> métodos en un orden adecuado. Si implementa su propio bucle de mensajes, el código es responsable de llamar a <xref:System.Windows.Interop.ComponentDispatcher> métodos de una manera similar.  
  
 Al llamar a <xref:System.Windows.Interop.ComponentDispatcher> métodos en un subproceso, sólo se invocarán los controladores de eventos que se registraron en ese subproceso.  
  
## <a name="writing-message-loops"></a>Escribir bucles de mensajes  
 La siguiente es una lista de comprobación de <xref:System.Windows.Interop.ComponentDispatcher> los miembros que se va a usar si escribe su propio bucle de mensajes:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: el bucle de mensajes debe llamar a este método para indicar que el subproceso es modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: el bucle de mensajes debe llamar a este método para indicar que el subproceso ha dejado de ser modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: el bucle de mensajes debe llamar a este método para indicar que <xref:System.Windows.Interop.ComponentDispatcher> debería desencadenar el <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> eventos. <xref:System.Windows.Interop.ComponentDispatcher>no se producirá <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> si <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> es `true`, pero pueden elegir bucles de mensajes llamar a <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> incluso si <xref:System.Windows.Interop.ComponentDispatcher> no puede responder a él mientras está en estado modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: el bucle de mensajes debe llamar a este método para indicar que hay un nuevo mensaje. El valor devuelto indica si un agente de escucha para un <xref:System.Windows.Interop.ComponentDispatcher> controla el mensaje de evento. Si <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> devuelve `true` (controlará), el distribuidor no debe hacer nada más con el mensaje. Si el valor devuelto es `false`, el distribuidor se espera que llame el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] función `TranslateMessage`, a continuación, llamar a `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Utilizar ComponentDispatcher y el control de mensajes existente  
 La siguiente es una lista de comprobación de <xref:System.Windows.Interop.ComponentDispatcher> los miembros que se va a usar si confía en el inherente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bucle de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: devuelve si la aplicación ha convertido en modal (por ejemplo, se ha insertado un bucle de mensajes modal). <xref:System.Windows.Interop.ComponentDispatcher>puede realizar un seguimiento de este estado porque la clase mantiene un recuento de <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> y <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> llamadas desde el bucle de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>y <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> eventos siguen las reglas estándares para las invocaciones del delegado. Los delegados se invocan en un orden no especificado y todos los delegados se invocan aun cuando la primera de ellas marca el mensaje como controlado.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un momento adecuado y eficaz para el procesamiento en inactividad (no hay ningún otro mensaje pendiente para el subproceso). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>no se generará si el subproceso es modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: genera para todos los mensajes que procesa el suministro de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: genera para todos los mensajes que no se administraron durante <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Se considera un mensaje si administrado después de la <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> eventos o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> eventos, el `handled` parámetro pasado por referencia en los datos del evento es `true`. Controladores de eventos deben pasar por alto el mensaje si `handled` es `true`, ya que significa que el controlador distinto ha administrado el mensaje primero. Controladores de eventos para ambos eventos pueden modificar el mensaje. El distribuidor debe enviar el mensaje modificado y no en el mensaje original sin cambios. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>se entrega a todos los agentes de escucha, pero la intención de la arquitectura es que sólo la ventana de nivel superior que contiene el HWND en el que los mensajes de destino deben invocar código en respuesta al mensaje.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Cómo trata HwndSource los eventos ComponentDispatcher  
 Si el <xref:System.Windows.Interop.HwndSource> es una ventana de nivel superior (ningún elemento primario HWND), registrará con <xref:System.Windows.Interop.ComponentDispatcher>. Si <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> se genera, y si el mensaje está diseñado para la <xref:System.Windows.Interop.HwndSource> o ventanas secundarias, <xref:System.Windows.Interop.HwndSource> llamadas su <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> secuencia de receptor de teclado.  
  
 Si el <xref:System.Windows.Interop.HwndSource> no es una ventana de nivel superior (tiene un HWND primario), no habrá ningún control. La ventana de nivel superior se espera que haga el control y no existe, se espera que una ventana de nivel superior con compatibilidad con el teclado receptor como parte de cualquier escenario de interoperación.  
  
 Si <xref:System.Windows.Interop.HwndHost.WndProc%2A> en un <xref:System.Windows.Interop.HwndSource> se llama sin un método de receptor de teclado correspondiente que se llama en primer lugar, la aplicación recibirá los eventos de teclado de nivel superior como <xref:System.Windows.UIElement.KeyDown>. Sin embargo, no hay ningún método de receptor de teclado se llamará, lo que evita la características de modelo de entrada de teclado deseable como la posibilidad de clave de acceso. Esto podría deberse a que el bucle de mensajes no correctamente notificó al subproceso pertinente en el <xref:System.Windows.Interop.ComponentDispatcher>, o porque el elemento primario HWND no invocó las respuestas de receptor de teclado adecuado.  
  
 Un mensaje que entra en el receptor de teclado podría no enviarse al HWND si se han agregado enlaces para ese mensaje utilizando el <xref:System.Windows.Interop.HwndSource.AddHook%2A> método. El mensaje se podría haber detectado en el nivel de bombeo de mensajes directamente y no se envían a la `DispatchMessage` (función).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Interop.ComponentDispatcher>  
 <xref:System.Windows.Interop.IKeyboardInputSink>  
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Modelo de subprocesos](../../../../docs/framework/wpf/advanced/threading-model.md)  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)
