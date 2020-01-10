---
title: Compartir bucles de mensajes entre Win32 y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 5c1d75ab9598196e9cffc78a2f116993e722fd38
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740314"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Compartir bucles de mensajes entre Win32 y WPF
En este tema se describe cómo implementar un bucle de mensajes para la interoperación con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], ya sea mediante la exposición de los bucles de mensajes existentes en <xref:System.Windows.Threading.Dispatcher> o mediante la creación de un bucle de mensajes independiente en el lado de Win32 del código de interoperación.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher y el bucle de mensajes  
 Un escenario normal de interoperación y la compatibilidad con los eventos de teclado es implementar <xref:System.Windows.Interop.IKeyboardInputSink>, o para subclases de clases que ya implementan <xref:System.Windows.Interop.IKeyboardInputSink>, como <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>. Sin embargo, la compatibilidad con el receptor de teclado no aborda todas las necesidades posibles de bucle de mensajes que pueda tener al enviar y recibir mensajes a través de los límites de interoperación. Para ayudar a formalizar una arquitectura de bucle de mensajes de aplicación, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona la clase <xref:System.Windows.Interop.ComponentDispatcher>, que define un protocolo simple para que siga un bucle de mensajes.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> es una clase estática que expone varios miembros. El ámbito de cada método está asociado implícitamente al subproceso que realiza la llamada. Un bucle de mensajes debe llamar a algunas de esas API en momentos críticos (como se define en la sección siguiente).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> proporciona eventos que pueden escuchar otros componentes (como el receptor del teclado). La clase <xref:System.Windows.Threading.Dispatcher> llama a todos los métodos de <xref:System.Windows.Interop.ComponentDispatcher> adecuados en una secuencia adecuada. Si está implementando su propio bucle de mensajes, el código es responsable de llamar a los métodos de <xref:System.Windows.Interop.ComponentDispatcher> de una manera similar.  
  
 La llamada a métodos <xref:System.Windows.Interop.ComponentDispatcher> en un subproceso solo invocará los controladores de eventos que se registraron en ese subproceso.  
  
## <a name="writing-message-loops"></a>Escribir bucles de mensajes  
 A continuación se proporciona una lista de comprobación de los miembros <xref:System.Windows.Interop.ComponentDispatcher> que usará si escribe su propio bucle de mensajes:  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: el bucle de mensajes debería llamarlo para indicar que el subproceso es modal.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: el bucle de mensajes debería llamarlo para indicar que el subproceso se ha revertido a no modal.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: el bucle de mensajes debería llamarlo para indicar que <xref:System.Windows.Interop.ComponentDispatcher> debe generar el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>. <xref:System.Windows.Interop.ComponentDispatcher> no generarán <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> si <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> está `true`, pero los bucles de mensajes pueden optar por llamar a <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> aunque <xref:System.Windows.Interop.ComponentDispatcher> no puedan responder a él mientras esté en estado modal.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: el bucle de mensajes debería llamarlo para indicar que hay un nuevo mensaje disponible. El valor devuelto indica si un agente de escucha de un evento <xref:System.Windows.Interop.ComponentDispatcher> controló el mensaje. Si <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> devuelve `true` (controlado), el distribuidor no debe hacer nada más con el mensaje. Si el valor devuelto es `false`, se espera que el distribuidor llame a la función `TranslateMessage`de Win32 y, a continuación, llame a `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Usar ComponentDispatcher y el control de mensajes existente  
 A continuación se ofrece una lista de comprobación de los miembros de <xref:System.Windows.Interop.ComponentDispatcher> que usará si confía en el bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inherente.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: devuelve si la aplicación ha desaparecido modal (por ejemplo, si se ha insertado un bucle de mensajes modal). <xref:System.Windows.Interop.ComponentDispatcher> puede realizar el seguimiento de este estado porque la clase mantiene un recuento de llamadas a <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> y <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> desde el bucle de mensajes.  
  
- los eventos <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> y <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> siguen las reglas estándar para las invocaciones de delegado. Los delegados se invocan en un orden no especificado y todos los delegados se invocan incluso si el primero de ellos marca el mensaje como controlado.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un tiempo adecuado y eficaz para realizar el procesamiento inactivo (no hay ningún otro mensaje pendiente para el subproceso). no se producirá <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> si el subproceso es modal.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: se genera para todos los mensajes que procesa el bombeo de mensajes.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: se genera para todos los mensajes que no se administraron durante <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Un mensaje se considera controlado si después del evento de <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> evento, se `true`el parámetro de `handled` pasado por referencia en los datos de evento. Los controladores de eventos deben omitir el mensaje si `handled` se `true`, porque esto significa que el controlador diferente controló el mensaje en primer lugar. Los controladores de eventos para ambos eventos pueden modificar el mensaje. El distribuidor debe enviar el mensaje modificado y no el mensaje original sin modificar. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> se entrega a todos los agentes de escucha, pero la intención de la arquitectura es que solo la ventana de nivel superior que contiene el HWND en el que los mensajes de destino deben invocar código en respuesta al mensaje.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Cómo trata HwndSource los eventos ComponentDispatcher  
 Si el <xref:System.Windows.Interop.HwndSource> es una ventana de nivel superior (sin HWND primario), se registrará en <xref:System.Windows.Interop.ComponentDispatcher>. Si se produce <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>, y si el mensaje está destinado a las ventanas <xref:System.Windows.Interop.HwndSource> o secundarias, <xref:System.Windows.Interop.HwndSource> llama a su <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> secuencia del receptor del teclado.  
  
 Si el <xref:System.Windows.Interop.HwndSource> no es una ventana de nivel superior (tiene un HWND primario), no habrá ningún control. Solo se espera que la ventana de nivel superior realice el control y se espera que sea una ventana de nivel superior con la compatibilidad del receptor de teclado como parte de cualquier escenario de interoperación.  
  
 Si se llama a <xref:System.Windows.Interop.HwndHost.WndProc%2A> en un <xref:System.Windows.Interop.HwndSource> sin que se llame primero al método del receptor de teclado adecuado, la aplicación recibirá los eventos de teclado de nivel superior como <xref:System.Windows.UIElement.KeyDown>. Sin embargo, no se llamará a ningún método de receptor de teclado, lo que evita las características deseadas del modelo de entrada de teclado, como la compatibilidad con claves de acceso. Esto puede ocurrir porque el bucle de mensajes no notificó correctamente el subproceso correspondiente en el <xref:System.Windows.Interop.ComponentDispatcher>, o porque el HWND primario no invocó las respuestas del receptor de teclado adecuado.  
  
 Es posible que un mensaje que pase al receptor de teclado no se envíe al HWND si agregó enlaces para ese mensaje mediante el método <xref:System.Windows.Interop.HwndSource.AddHook%2A>. Es posible que el mensaje se haya controlado directamente en el nivel de bombeo de mensajes y no se haya enviado a la función `DispatchMessage`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Modelo de subprocesos](threading-model.md)
- [Información general sobre acciones del usuario](input-overview.md)
