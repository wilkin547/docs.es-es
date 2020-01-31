---
title: Arquitectura de entrada de interoperabilidad de Windows Forms y WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
ms.openlocfilehash: 1c7027947d24c847ee298022344e02ce0bbff764
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794094"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF
La interoperación entre el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el Windows Forms requiere que ambas tecnologías tengan el procesamiento de entradas de teclado adecuado. En este tema se describe cómo estas tecnologías implementan el procesamiento de mensajes y teclado para habilitar la interoperación fluida en aplicaciones híbridas.  
  
 Este tema contiene las siguientes subsecciones:  
  
- Formularios y cuadros de diálogo no modales  
  
- Procesamiento de mensajes y teclado de WindowsFormsHost  
  
- Procesamiento de mensajes y teclado de ElementHost  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Formularios y cuadros de diálogo no modales  
 Llame al método <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> para abrir un formulario o cuadro de diálogo no modal desde una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Llame al método <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> en el control <xref:System.Windows.Forms.Integration.ElementHost> para abrir una página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no modal en una aplicación basada en Windows Forms.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>Procesamiento de mensajes y teclado de WindowsFormsHost  
 Cuando se hospeda en una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], Windows Forms el procesamiento de mensajes y de teclado consiste en lo siguiente:  
  
- La clase <xref:System.Windows.Forms.Integration.WindowsFormsHost> adquiere mensajes del bucle de mensajes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que se implementa mediante la clase <xref:System.Windows.Interop.ComponentDispatcher>.  
  
- La clase <xref:System.Windows.Forms.Integration.WindowsFormsHost> crea un bucle de mensajes Windows Forms suplente para asegurarse de que se produce el procesamiento normal del teclado de Windows Forms.  
  
- La clase <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementa la interfaz <xref:System.Windows.Interop.IKeyboardInputSink> para coordinar la administración del foco con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Los controles de <xref:System.Windows.Forms.Integration.WindowsFormsHost> se registran y inician sus bucles de mensajes.  
  
 En las secciones siguientes se describen con más detalle estas partes del proceso.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Adquirir mensajes del bucle de mensajes de WPF  
 La clase <xref:System.Windows.Interop.ComponentDispatcher> implementa el administrador de bucles de mensajes para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La clase <xref:System.Windows.Interop.ComponentDispatcher> proporciona enlaces para permitir que los clientes externos filtren los mensajes antes de que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los procese.  
  
 La implementación de interoperación controla el evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>, que permite a los controles de Windows Forms procesar los mensajes antes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Bucle de mensajes Windows Forms suplente  
 De forma predeterminada, la clase <xref:System.Windows.Forms.Application?displayProperty=nameWithType> contiene el bucle de mensajes principal para las aplicaciones de Windows Forms. Durante la interoperación, el bucle de mensajes Windows Forms no procesa los mensajes. Por lo tanto, esta lógica debe reproducirse. El controlador del evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> realiza los pasos siguientes:  
  
1. Filtra el mensaje mediante la interfaz de <xref:System.Windows.Forms.IMessageFilter>.  
  
2. Llama al método <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>.  
  
3. Traduce y envía el mensaje, si es necesario.  
  
4. Pasa el mensaje al control de hospedaje, si ningún otro control procesa el mensaje.  
  
### <a name="ikeyboardinputsink-implementation"></a>Implementación de IKeyboardInputSink  
 El bucle de mensajes suplente controla la administración del teclado. Por lo tanto, el método <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> es el único miembro <xref:System.Windows.Interop.IKeyboardInputSink> que requiere una implementación en la clase <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 De forma predeterminada, la clase <xref:System.Windows.Interop.HwndHost> devuelve `false` para su <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> implementación. Esto evita que la tabulación de un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un control Windows Forms.  
  
 La implementación <xref:System.Windows.Forms.Integration.WindowsFormsHost> del método <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> realiza los pasos siguientes:  
  
1. Busca el primer o último control Windows Forms que está incluido en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> y que puede recibir el foco. La elección del control depende de la información de recorrido.  
  
2. Establece el foco en el control y devuelve `true`.  
  
3. Si ningún control puede recibir el foco, devuelve `false`.  
  
### <a name="windowsformshost-registration"></a>Registro de WindowsFormsHost  
 Cuando se crea el identificador de ventana de un control <xref:System.Windows.Forms.Integration.WindowsFormsHost>, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> llama a un método estático interno que registra su presencia para el bucle de mensajes.  
  
 Durante el registro, el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> examina el bucle de mensajes. Si no se ha iniciado el bucle de mensajes, se crea el controlador de eventos <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>. Se considera que el bucle de mensajes se está ejecutando cuando se adjunta el controlador de eventos <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>.  
  
 Cuando se destruye el identificador de ventana, el control de <xref:System.Windows.Forms.Integration.WindowsFormsHost> se quita del registro.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>Procesamiento de mensajes y teclado de ElementHost  
 Cuando se hospeda en una aplicación Windows Forms, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el procesamiento de mensajes y de teclado consiste en lo siguiente:  
  
- <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>y <xref:System.Windows.Interop.IKeyboardInputSite> implementaciones de la interfaz.  
  
- Teclas de tabulación y de flecha.  
  
- Teclas de comando y teclas de cuadro de diálogo.  
  
- Windows Forms el procesamiento del acelerador.  
  
 En las secciones siguientes se describen estas partes con más detalle.  
  
### <a name="interface-implementations"></a>Implementaciones de interfaz  
 En Windows Forms, los mensajes del teclado se enrutan al identificador de ventana del control que tiene el foco. En el control <xref:System.Windows.Forms.Integration.ElementHost>, estos mensajes se enrutan al elemento hospedado. Para ello, el control <xref:System.Windows.Forms.Integration.ElementHost> proporciona una instancia de <xref:System.Windows.Interop.HwndSource>. Si el control de <xref:System.Windows.Forms.Integration.ElementHost> tiene el foco, la instancia de <xref:System.Windows.Interop.HwndSource> enruta la mayoría de las entradas del teclado para que pueda ser procesada por la clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager>.  
  
 La clase <xref:System.Windows.Interop.HwndSource> implementa las interfaces <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
 La interoperación de teclado se basa en la implementación del método <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> para controlar la tecla de TABULAción y la entrada de tecla de dirección que mueve el foco fuera de los elementos hospedados.  
  
### <a name="tabbing-and-arrow-keys"></a>Teclas de tabulación y de flecha  
 La lógica de selección de Windows Forms está asignada a los métodos <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> y <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> para implementar la navegación por la tecla TAB y las teclas de dirección. Al invalidar el método <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> se realiza esta asignación.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Teclas de comando y teclas de cuadro de diálogo  
 Para dar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la primera oportunidad de procesar teclas de comando y teclas de cuadro de diálogo, Windows Forms preprocesamiento de comandos está conectado al método <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>. Al invalidar el método <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> se conectan las dos tecnologías.  
  
 Con el método <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>, los elementos hospedados pueden controlar cualquier mensaje de tecla, como WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN o WM_SYSKEYUP, incluidas las teclas de comando, como TAB, ENTER, ESC y las teclas de dirección. Si no se controla un mensaje de tecla, se envía el Windows Forms jerarquía de antecesores para el control.  
  
### <a name="accelerator-processing"></a>Procesamiento de aceleradores  
 Para procesar los aceleradores correctamente, Windows Forms procesamiento del acelerador debe estar conectado a la clase <xref:System.Windows.Input.AccessKeyManager> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Además, todos los mensajes de WM_CHAR se deben enrutar correctamente a los elementos hospedados.  
  
 Dado que la implementación <xref:System.Windows.Interop.HwndSource> predeterminada del método <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> devuelve `false`, WM_CHAR mensajes se procesan con la lógica siguiente:  
  
- Se invalida el método <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> para asegurarse de que todos los mensajes de WM_CHAR se reenvían a los elementos hospedados.  
  
- Si se presiona la tecla ALT, el mensaje se WM_SYSCHAR. Windows Forms no procesa este mensaje a través del método <xref:System.Windows.Forms.Control.IsInputChar%2A>. Por lo tanto, el método <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> se invalida para consultar el <xref:System.Windows.Input.AccessKeyManager> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de un acelerador registrado. Si se encuentra un acelerador registrado, <xref:System.Windows.Input.AccessKeyManager> lo procesa.  
  
- Si no se presiona la tecla ALT, la clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> procesa la entrada no controlada. Si la entrada es un acelerador, el <xref:System.Windows.Input.AccessKeyManager> la procesa. El evento <xref:System.Windows.Input.InputManager.PostProcessInput> se controla para los mensajes de WM_CHAR que no se han procesado.  
  
 Cuando el usuario presiona la tecla ALT, las indicaciones visuales del acelerador se muestran en todo el formulario. Para admitir este comportamiento, todos los <xref:System.Windows.Forms.Integration.ElementHost> controles del formulario activo reciben WM_SYSKEYDOWN mensajes, independientemente del control que tenga el foco.  
  
 Los mensajes solo se envían a los controles <xref:System.Windows.Forms.Integration.ElementHost> del formulario activo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
