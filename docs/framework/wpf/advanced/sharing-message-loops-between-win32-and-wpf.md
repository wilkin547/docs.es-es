---
title: "Compartir bucles de mensajes entre Win32 y WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "interoperabilidad [WPF], Win32"
  - "bucles de mensajes [WPF]"
  - "compartir bucles de mensajes"
  - "código Win32, compartir bucles de mensajes"
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Compartir bucles de mensajes entre Win32 y WPF
En este tema se describe cómo implementar un bucle de mensajes para la interoperación con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], ya sea usando la exposición del bucle de mensajes existente en <xref:System.Windows.Threading.Dispatcher> o bien creando un bucle de mensajes independiente en el lado de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] del código de interoperación.  
  
## ComponentDispatcher y el bucle de mensajes  
 Un escenario normal para la interacción y la compatibilidad de eventos de teclado consiste en implementar <xref:System.Windows.Interop.IKeyboardInputSink>, o en crear subclases de las clases que ya implementan <xref:System.Windows.Interop.IKeyboardInputSink>, como <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>.  Sin embargo, la compatibilidad con receptor de teclado no satisface todas las necesidades posibles de bucle de mensajes que puedan presentarse al enviar y recibir mensajes a través de los límites de interacción.  Para ayudar a formalizar la arquitectura de bucle de mensajes de la aplicación, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona la clase <xref:System.Windows.Interop.ComponentDispatcher>, que define un protocolo simple que puede seguir un bucle de mensajes.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> es una clase estática que expone varios miembros.  El ámbito de cada método está asociado implícitamente al subproceso que realiza la llamada.  Un bucle de mensajes debe llamar a algunas de esas [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] en los momentos críticos \(como se define en la sección siguiente\).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> proporciona eventos para los que otros componentes \(como el receptor de teclado\) pueden realizar escuchas.  La clase <xref:System.Windows.Threading.Dispatcher> llama a todos los métodos <xref:System.Windows.Interop.ComponentDispatcher> adecuados en la secuencia apropiada.  Si implementa su propio bucle de mensajes, el código es responsable de llamar a los métodos <xref:System.Windows.Interop.ComponentDispatcher> de un modo similar.  
  
 Al llamar a los métodos <xref:System.Windows.Interop.ComponentDispatcher> para un subproceso, sólo se invocarán los controladores de eventos que se registraron en ese subproceso.  
  
## Escribir bucles de mensajes  
 A continuación, se muestra una lista de comprobación de los miembros de <xref:System.Windows.Interop.ComponentDispatcher> que utilizará si escribe su propio bucle de mensajes:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: el bucle de mensajes debe llamar a este método para indicar que el subproceso es modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: el bucle de mensajes debe llamar a este método para indicar que el subproceso ha dejado de ser modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: el bucle de mensajes debe llamar a este método para indicar que <xref:System.Windows.Interop.ComponentDispatcher> debe generar el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>.  <xref:System.Windows.Interop.ComponentDispatcher> no generará <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> si <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> es `true`, pero los bucles de mensajes pueden optar por llamar a <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> aunque <xref:System.Windows.Interop.ComponentDispatcher> no pueda responder mientras se encuentra en estado modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: el bucle de mensajes debe llamar a este método para indicar que hay un nuevo mensaje disponible.  El valor devuelto indica si el mensaje lo administró un agente de escucha de un evento de <xref:System.Windows.Interop.ComponentDispatcher>.  Si <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> devuelve `true` \(se ha administrado\), el distribuidor no debe hacer nada más con el mensaje.  Si el valor devuelto es `false`, se espera que el distribuidor llame a la función `TranslateMessage` de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y, a continuación, a `DispatchMessage`.  
  
## Utilizar ComponentDispatcher y el control de mensajes existente  
 A continuación, se muestra una lista de comprobación de los miembros de <xref:System.Windows.Interop.ComponentDispatcher> que utilizará si se basa en el bucle de mensajes inherente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: devuelve si la aplicación se ha convertido en modal \(por ejemplo, se ha insertado un bucle de mensajes modal\).  <xref:System.Windows.Interop.ComponentDispatcher> puede realizar el seguimiento de este estado porque la clase mantiene un recuento de llamadas del bucle de mensajes a <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> y <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>.  
  
-   Los eventos <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> y <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> siguen las reglas estándar para las invocaciones de delegado.  Se invocan todos los delegados en un orden no especificado y aunque el primero marque el mensaje como administrado.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un momento adecuado y eficaz para efectuar el procesamiento en inactividad \(es decir, cuando no hay ningún otro mensaje pendiente para el subproceso\).  El evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> no se generará si el subproceso es modal.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: se provoca para todos los mensajes procesados por el suministro de mensajes.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: se provoca para todos los mensajes que no se administraron durante el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Un mensaje se considera administrado si, después del evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>, el parámetro `handled` pasado por referencia en los datos del evento es `true`.  Los controladores de eventos deben omitir el mensaje si `handled` es `true`, porque esto significa que otro controlador distinto ha administrado antes el mensaje.  Los controladores de ambos eventos pueden modificar el mensaje.  El distribuidor debe enviar el mensaje modificado y no el mensaje original sin modificar.  El evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> se entrega a todos los agentes de escucha, pero la intención de la arquitectura es que solo invoque código como respuesta al mensaje la ventana de nivel superior que contiene el indicador de ventana HWND al que están destinados los mensajes.  
  
## Cómo trata HwndSource los eventos ComponentDispatcher  
 Si <xref:System.Windows.Interop.HwndSource> es una ventana de nivel superior \(sin ningún HWND primario\), se registrará con <xref:System.Windows.Interop.ComponentDispatcher>.  Si se provoca el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>, y si el mensaje está dirigido a <xref:System.Windows.Interop.HwndSource> o a ventanas secundarias, <xref:System.Windows.Interop.HwndSource> llama a su secuencia de receptor de teclado: <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> y <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A>.  
  
 Si <xref:System.Windows.Interop.HwndSource> no es una ventana de nivel superior \(tiene un HWND primario\), no se realizará ninguna administración.  Se espera que sólo la ventana de nivel superior efectúe la administración, y que haya una ventana de nivel superior con compatibilidad con el receptor de teclado como parte de cualquier escenario de interacción.  
  
 Si se llama a <xref:System.Windows.Interop.HwndHost.WndProc%2A> para <xref:System.Windows.Interop.HwndSource> sin haber llamado antes a un método de receptor de teclado adecuado, la aplicación recibirá los eventos de nivel de teclado más alto, como <xref:System.Windows.UIElement.KeyDown>.  Sin embargo, no se llamará a ningún método de receptor de teclado, con lo que se omiten las características deseables del modelo de acciones del teclado, como la compatibilidad con las teclas de acceso.  Esto puede deberse a que el bucle de mensajes no notifique correctamente al subproceso pertinente en <xref:System.Windows.Interop.ComponentDispatcher>, o a que el HWND primario no invoque las respuestas de receptor de teclado apropiadas.  
  
 Un mensaje que va al receptor de teclado podría no enviarse al HWND si se han agregado enlaces para ese mensaje mediante el método <xref:System.Windows.Interop.HwndSource.AddHook%2A>.  El mensaje podría administrarse directamente en el nivel de suministro de mensajes y no enviarse a la función `DispatchMessage`.  
  
## Vea también  
 <xref:System.Windows.Interop.ComponentDispatcher>   
 <xref:System.Windows.Interop.IKeyboardInputSink>   
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Modelo de subprocesos](../../../../docs/framework/wpf/advanced/threading-model.md)   
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)