---
title: "Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Mensajes y teclado de ElementHost"
  - "arquitectura de entrada [interoperabilidad con WPF]"
  - "interoperabilidad [WPF], Windows Forms"
  - "interoperabilidad con teclado [WPF]"
  - "mensajes [WPF]"
  - "cuadros de diálogo no modales [WPF]"
  - "formularios no modales"
  - "formularios Windows Forms [WPF], interoperabilidad con"
  - "Windows Forms, interoperabilidad con WPF"
  - "Mensajes y teclado de WindowsFormsHost"
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF
La interoperabilidad entre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] requiere que ambas tecnologías tengan el procesamiento adecuado de la entrada de teclado.  En este tema se describe cómo estas tecnologías implementan el procesamiento de teclado y de mensajes para habilitar la interoperabilidad sin contratiempos en aplicaciones híbridas.  
  
 Este tema contiene las siguientes subsecciones:  
  
-   Formularios no modales y cuadros de diálogo  
  
-   Procesamiento de mensajes y de teclado de WindowsFormsHost  
  
-   Procesamiento de mensajes y de teclado de ElementHost  
  
## Formularios no modales y cuadros de diálogo  
 Llame al método <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> para abrir un formulario no modal o un cuadro de diálogo desde una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Llame al método <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> del control <xref:System.Windows.Forms.Integration.ElementHost> para abrir una página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no modal en una aplicación basada en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## Procesamiento de mensajes y de teclado de WindowsFormsHost  
 Cuando se hospeda en una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el procesamiento de mensajes y teclado de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] consta de lo siguiente:  
  
-   La clase <xref:System.Windows.Forms.Integration.WindowsFormsHost> adquiere mensajes del bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], implementado por la clase <xref:System.Windows.Interop.ComponentDispatcher>.  
  
-   La clase <xref:System.Windows.Forms.Integration.WindowsFormsHost> crea un bucle de mensajes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] suplente para asegurarse de que se produzca el procesamiento de teclado ordinario de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   La clase <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementa la interfaz <xref:System.Windows.Interop.IKeyboardInputSink> para coordinar la administración del foco con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Los controles <xref:System.Windows.Forms.Integration.WindowsFormsHost> se registran por sí mismos e inician sus bucles de mensajes.  
  
 En las secciones siguientes se describen estas partes del proceso más detalladamente.  
  
### Adquirir mensajes del bucle de mensajes de WPF  
 La clase <xref:System.Windows.Interop.ComponentDispatcher> implementa el administrador del bucle de mensajes para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La clase <xref:System.Windows.Interop.ComponentDispatcher> proporciona enlaces para permitir que los clientes externos filtren mensajes antes de que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los procese.  
  
 La implementación de la interoperabilidad administra el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>, que permite a los controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] procesar mensajes antes que los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Bucle de mensajes suplente de formularios de Windows Forms  
 De forma predeterminada, la clase <xref:System.Windows.Forms.Application?displayProperty=fullName> contiene el bucle de mensajes primario para aplicaciones de formularios de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Durante la interoperabilidad, el bucle de mensajes de formularios de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no procesa los mensajes.  Por consiguiente, se debe reproducir esta lógica.  El controlador para el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName> realiza los pasos siguientes:  
  
1.  Filtra el mensaje mediante la interfaz <xref:System.Windows.Forms.IMessageFilter>.  
  
2.  Llama al método <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName>.  
  
3.  Traduce y envía el mensaje, si se requiere.  
  
4.  Pasa el mensaje al control host, si ningún otro control procesa el mensaje.  
  
### Implementación de IKeyboardInputSink  
 El bucle de mensajes suplente controla la administración del teclado.  Por consiguiente, el método <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName> es el único miembro de <xref:System.Windows.Interop.IKeyboardInputSink> que requiere una implementación en la clase <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 De forma predeterminada, la clase <xref:System.Windows.Interop.HwndHost> devuelve `false` para su implementación de <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>.  Esto evita pasar con la tecla de tabulación de un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 La implementación de <xref:System.Windows.Forms.Integration.WindowsFormsHost> del método <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName> realiza los pasos siguientes:  
  
1.  Busca el primer o el último control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] contenido en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> y que puede recibir el foco.  La opción de control depende de la información de recorrido.  
  
2.  Establece el foco en el control y devuelve `true`.  
  
3.  Si ningún control puede recibir el foco, devuelve `false`.  
  
### Registro de WindowsFormsHost  
 Cuando se crea el identificador de ventana para un control <xref:System.Windows.Forms.Integration.WindowsFormsHost>, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> llama a un método estático interno que registra su presencia para el bucle de mensajes.  
  
 Durante el registro, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> examina el bucle de mensajes.  Si no se ha iniciado el bucle de mensajes, se crea el controlador de eventos <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>.  Se considera que el bucle de mensajes se está ejecutando cuando está asociado el controlador de eventos <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>.  
  
 Cuando se destruye el identificador de ventana, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> se quita del registro.  
  
## Procesamiento de mensajes y de teclado de ElementHost  
 Cuando se hospeda en una aplicación [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], el procesamiento de mensajes y teclado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consta de lo siguiente:  
  
-   Implementaciones de la interfaz <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
-   Teclas de tabulación y dirección.  
  
-   Teclas de comando y de cuadro de diálogo.  
  
-   Procesamiento de aceleradores de formularios de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 En las secciones siguientes se describen estas partes más detalladamente.  
  
### Implementaciones de interfaces  
 En [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], los mensajes del teclado se enrutan al identificador de ventana del control que tiene el foco.  En el control <xref:System.Windows.Forms.Integration.ElementHost>, estos mensajes se enrutan al elemento hospedado.  Para ello, el control <xref:System.Windows.Forms.Integration.ElementHost> proporciona una instancia de <xref:System.Windows.Interop.HwndSource>.  Si el control <xref:System.Windows.Forms.Integration.ElementHost> tiene el foco, la instancia de <xref:System.Windows.Interop.HwndSource> enruta la mayor parte de la entrada del teclado para que pueda procesarla la clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.InputManager>.  
  
 La clase <xref:System.Windows.Interop.HwndSource> implementa las interfaces <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
 La interoperabilidad del teclado se apoya en la implementación del método <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> para administrar la entrada de la tecla de tabulación y las teclas de dirección que mueve el foco fuera de los elementos hospedados.  
  
### Teclas de tabulación y dirección  
 La lógica de selección [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] está asignada a los métodos <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> y <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> para implementar la navegación con la tecla de tabulación y las teclas de dirección.  Esta asignación se realiza invalidando el método <xref:System.Windows.Forms.Integration.ElementHost.Select%2A>.  
  
### Teclas de comando y de cuadro de diálogo  
 Para dar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la primera oportunidad de procesar teclas de comando y teclas de diálogo, el procesamiento previo de comandos de formularios de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] está conectado al método <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>.  Al invalidar el método <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=fullName>, se conectan las dos tecnologías.  
  
 Con el método <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>, los elementos hospedados pueden administrar cualquier mensaje clave, como WM\_KEYDOWN, WM\_KEYUP, WM\_SYSKEYDOWN o WM\_SYSKEYUP, incluidas las teclas de comando como TAB, Entrar, ESC y las teclas de dirección.  Si no se administra un mensaje clave, se envía a la jerarquía de antecesor de formularios de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] para su administración.  
  
### Procesamiento de aceleradores  
 Para procesar correctamente los aceleradores, el procesamiento de aceleradores de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] debe estar conectado a la clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.AccessKeyManager>.  Además, todos los mensajes de WM\_CHAR se deben enrutar correctamente a los elementos hospedados.  
  
 Dado que la implementación predeterminada de <xref:System.Windows.Interop.HwndSource> del método <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> devuelve `false`, los mensajes de WM\_CHAR se procesan utilizando la lógica siguiente:  
  
-   El método <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=fullName> se invalida para asegurarse que todos los mensajes de WM\_CHAR se reenvíen a los elementos hospedados.  
  
-   Si se presiona la tecla ALT, el mensaje es WM\_SYSCHAR.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no preprocesa este mensaje a través del método <xref:System.Windows.Forms.Control.IsInputChar%2A>.  Por tanto, el método <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> se invalida para consultar un acelerador registrado en el objeto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.AccessKeyManager>.  Si se encuentra un acelerador registrado, <xref:System.Windows.Input.AccessKeyManager> lo procesa.  
  
-   Si no se presiona la tecla ALT, la clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.InputManager> procesa la entrada no controlada.  Si la entrada es un acelerador, el objeto <xref:System.Windows.Input.AccessKeyManager> lo procesa.  El evento <xref:System.Windows.Input.InputManager.PostProcessInput> se administra para los mensajes de WM\_CHAR que no se procesaron.  
  
 Cuando el usuario presiona la tecla ALT, se muestran indicaciones visuales del acelerador en todo el formulario.  Para admitir este comportamiento, todos los controles <xref:System.Windows.Forms.Integration.ElementHost> del formulario activo reciben mensajes de WM\_SYSKEYDOWN, sin tener en cuenta qué control tiene el foco.  
  
 Los mensajes solamente se envían a los controles <xref:System.Windows.Forms.Integration.ElementHost> del formulario activo.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)