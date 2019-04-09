---
title: Compartir bucles de mensajes entre Win32 y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 74055ec3facb7db9145c4c0e969d57da24eccbc8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115081"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Compartir bucles de mensajes entre Win32 y WPF
Este tema describe cómo implementar un bucle de mensajes para la interoperación con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], mediante el uso existente del mensaje exposición de bucle en <xref:System.Windows.Threading.Dispatcher> o mediante la creación de un bucle de mensajes independiente en el [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] en paralelo del código de interoperación.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher y el bucle de mensajes  
 Un escenario normal para la compatibilidad con eventos de teclado y la interoperación consiste en implementar <xref:System.Windows.Interop.IKeyboardInputSink>, o para crear una subclase de las clases que ya implementan <xref:System.Windows.Interop.IKeyboardInputSink>, tales como <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>. Sin embargo, compatibilidad con receptor de teclado no abordar las necesidades de bucle de mensaje posible es posible que tenga al enviar y recibir mensajes a través de los límites de interoperación. Para ayudar a formalizar una arquitectura de bucle de mensaje de aplicación, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona el <xref:System.Windows.Interop.ComponentDispatcher> (clase), que define un protocolo simple de un bucle de mensajes a seguir.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> es una clase estática que expone a varios miembros. El ámbito de cada método implícitamente está asociado al subproceso que realiza la llamada. Un bucle de mensajes debe llamar a algunas de ellas [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] en los momentos críticos (como se define en la sección siguiente).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> Proporciona eventos que pueden escuchar otros componentes (por ejemplo, el receptor del teclado). El <xref:System.Windows.Threading.Dispatcher> llama a todos los controles de la clase <xref:System.Windows.Interop.ComponentDispatcher> métodos en la secuencia apropiada. Si está implementando su propio bucle de mensajes, el código es responsable de llamar a <xref:System.Windows.Interop.ComponentDispatcher> los métodos de una manera similar.  
  
 Una llamada a <xref:System.Windows.Interop.ComponentDispatcher> métodos en un subproceso, sólo se invocarán los controladores de eventos que se registraron en ese subproceso.  
  
## <a name="writing-message-loops"></a>Escribir bucles de mensajes  
 El siguiente es una lista de comprobación de <xref:System.Windows.Interop.ComponentDispatcher> los miembros que se usará si escribe su propio bucle de mensajes:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: el bucle de mensajes debe llamar a este método para indicar que el subproceso es modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: el bucle de mensajes debe llamar a este método para indicar que el subproceso ha dejado de ser modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: el bucle de mensajes debe llamar a este método para indicar que <xref:System.Windows.Interop.ComponentDispatcher> debe generar el <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> eventos. <xref:System.Windows.Interop.ComponentDispatcher> no se producirá <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> si <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> es `true`, pero pueden elegir llamar a bucles de mensajes <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> aunque <xref:System.Windows.Interop.ComponentDispatcher> no puede responder a él mientras esté en estado modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: el bucle de mensajes debe llamar a este método para indicar que está disponible un nuevo mensaje. El valor devuelto indica si un agente de escucha para un <xref:System.Windows.Interop.ComponentDispatcher> controla el mensaje de evento. Si <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> devuelve `true` (controladas), el distribuidor debe hacer nada más con el mensaje. Si el valor devuelto es `false`, se espera el distribuidor para llamar a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] función `TranslateMessage`, a continuación, llamar a `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Utilizar ComponentDispatcher y el control de mensajes existente  
 El siguiente es una lista de comprobación de <xref:System.Windows.Interop.ComponentDispatcher> los miembros que se usará si confía en el inherente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bucle de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: devuelve si la aplicación ha quedado modal (por ejemplo, se ha insertado un bucle de mensaje modal). <xref:System.Windows.Interop.ComponentDispatcher> puede realizar un seguimiento de este estado porque la clase mantiene un recuento de <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> y <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> llamadas desde el bucle de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> y <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> eventos siguen las reglas estándar para las invocaciones del delegado. Los delegados se invocan en un orden no especificado y todos los delegados se invocan incluso si la primera de ellas marca el mensaje como controlado.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un tiempo adecuado y eficiente para el procesamiento en inactividad (no hay ningún otro mensaje pendiente para el subproceso). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> no se generará si el subproceso es modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: se genera para todos los mensajes que procesa el bombeo de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: se genera para todos los mensajes que no se controlaron durante <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Se considera un mensaje controlado si después de la <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> eventos o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> eventos, el `handled` parámetro pasado por referencia en los datos del evento es `true`. Controladores de eventos deben omitir el mensaje si `handled` es `true`, ya que esto significa que el controlador de diferentes controlado el mensaje primero. Controladores de eventos para eventos pueden modificar el mensaje. El distribuidor debe enviar el mensaje modificado y no en el mensaje original sin cambios. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> se entrega a todos los agentes de escucha, pero la intención de la arquitectura es que sólo la ventana de nivel superior que contiene el HWND en el que los mensajes de destino deben invocar código en respuesta al mensaje.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Cómo trata HwndSource ComponentDispatcher eventos  
 Si el <xref:System.Windows.Interop.HwndSource> es una ventana de nivel superior (ningún HWND primario), registrará con <xref:System.Windows.Interop.ComponentDispatcher>. Si <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> se genera, y si el mensaje está diseñado para la <xref:System.Windows.Interop.HwndSource> o ventanas secundarias, <xref:System.Windows.Interop.HwndSource> llamadas su <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> secuencia receptor del teclado.  
  
 Si el <xref:System.Windows.Interop.HwndSource> no es una ventana de nivel superior (tiene un HWND primario), no habrá ningún control. Sólo la ventana de nivel superior se espera que haga el control y no existe, se espera que una ventana de nivel superior con compatibilidad con receptor de teclado como parte de cualquier escenario de interoperación.  
  
 Si <xref:System.Windows.Interop.HwndHost.WndProc%2A> en un <xref:System.Windows.Interop.HwndSource> se llama sin un método de receptor de teclado correspondiente que se llama en primer lugar, la aplicación recibirá los eventos de teclado de nivel superior como <xref:System.Windows.UIElement.KeyDown>. Sin embargo, no hay métodos de receptor del teclado se llamará, lo que omiten las características de modelo de entrada de teclado deseable, como compatibilidad con claves de acceso. Esto podría deberse a que el bucle de mensajes no notificar correctamente el subproceso pertinente en el <xref:System.Windows.Interop.ComponentDispatcher>, o porque el HWND primario no invocó las respuestas de receptor de teclado adecuados.  
  
 No se podría enviar un mensaje que entra en el receptor del teclado en el HWND si se han agregado enlaces para ese mensaje mediante el uso de la <xref:System.Windows.Interop.HwndSource.AddHook%2A> método. El mensaje han sido controlado en el nivel de la bomba de mensaje directamente y no se envían a la `DispatchMessage` función.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Modelo de subprocesos](threading-model.md)
- [Información general sobre acciones del usuario](input-overview.md)
