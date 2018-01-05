---
title: Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a246a3297d212eabc31bf2ac9d000aeb56329d09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Arquitectura de entrada de interoperabilidad entre formularios Windows Forms y WPF
Interoperación entre el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] requiere que ambas tecnologías tengan el procesamiento de entrada de teclado correspondiente. Este tema describe cómo estas tecnologías implementan el teclado y procesamiento para habilitar la interoperabilidad sin contratiempos en aplicaciones híbridas de mensajes.  
  
 Este tema contiene las siguientes subsecciones:  
  
-   Formularios no modales y cuadros de diálogo  
  
-   Procesamiento de mensajes y teclado de WindowsFormsHost  
  
-   Procesamiento de mensajes y teclado de ElementHost  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Formularios no modales y cuadros de diálogo  
 Llame a la <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento para abrir un cuadro de diálogo o formulario no modal de una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en.  
  
 Llame a la <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> control para abrir un no modal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página en un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-aplicación basada en.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>Procesamiento de mensajes y teclado de WindowsFormsHost  
 Cuando se hospedan en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] teclado y el mensaje de procesamiento consta de las siguientes acciones:  
  
-   El <xref:System.Windows.Forms.Integration.WindowsFormsHost> clase adquiere mensajes desde el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bucle de mensajes, que se implementa mediante la <xref:System.Windows.Interop.ComponentDispatcher> clase.  
  
-   El <xref:System.Windows.Forms.Integration.WindowsFormsHost> clase crea un suplente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] bucle de mensajes para asegurarse de esa normal [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se produce el procesamiento de teclado.  
  
-   El <xref:System.Windows.Forms.Integration.WindowsFormsHost> la clase implementa la <xref:System.Windows.Interop.IKeyboardInputSink> interfaz para coordinar la administración del foco con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   El <xref:System.Windows.Forms.Integration.WindowsFormsHost> controles registrarse e iniciar sus bucles de mensajes.  
  
 En las siguientes secciones se describen estas partes del proceso con más detalle.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Adquirir mensajes desde el bucle de mensajes WPF  
 El <xref:System.Windows.Interop.ComponentDispatcher> clase implementa el Administrador de bucle de mensajes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El <xref:System.Windows.Interop.ComponentDispatcher> clase proporciona enlaces para permitir que los clientes externos para filtrar los mensajes antes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procesarlos.  
  
 Los identificadores de implementación de la interoperabilidad del <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> eventos, lo que permite [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles para procesar los mensajes antes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Bucle de mensajes de suplente Windows Forms  
 De forma predeterminada, el <xref:System.Windows.Forms.Application?displayProperty=nameWithType> clase contiene el bucle de mensajes principal para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] las aplicaciones. Durante la interoperabilidad, la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mensaje bucle no procesa los mensajes. Por lo tanto, se debe reproducir esta lógica. El controlador para el <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> eventos realizan los pasos siguientes:  
  
1.  Filtra el mensaje mediante la <xref:System.Windows.Forms.IMessageFilter> interfaz.  
  
2.  Llamadas a la <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> método.  
  
3.  Traduce y lo envía el mensaje, si es necesario.  
  
4.  Pasa el mensaje al control host, si ningún otro control procesa el mensaje.  
  
### <a name="ikeyboardinputsink-implementation"></a>Implementación de IKeyboardInputSink  
 El bucle de mensajes suplente controla la administración de teclado. Por lo tanto, la <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> es el único método <xref:System.Windows.Interop.IKeyboardInputSink> miembro que requiere una implementación en la <xref:System.Windows.Forms.Integration.WindowsFormsHost> clase.  
  
 De forma predeterminada, el <xref:System.Windows.Interop.HwndHost> clase devuelve `false` para su <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> implementación. Esto evita la tabulación desde una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el control a un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementación de la <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> método lleva a cabo los pasos siguientes:  
  
1.  Busca el primer o último [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control que está contenida en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control y que puede recibir el foco. La opción de control depende de la información de recorrido.  
  
2.  Establece el foco en el control y devuelve `true`.  
  
3.  Si ningún control puede recibir el foco, devuelve `false`.  
  
### <a name="windowsformshost-registration"></a>Registro de WindowsFormsHost  
 Al identificador de la ventana de un <xref:System.Windows.Forms.Integration.WindowsFormsHost> se crea el control, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control llama a un método estático interno que registra su presencia para el bucle de mensajes.  
  
 Durante el registro, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control examina el bucle de mensajes. Si no se ha iniciado el bucle de mensajes, el <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> se crea el controlador de eventos. El bucle de mensajes se considera que se ejecuta cuando el <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> se adjunta el controlador de eventos.  
  
 Cuando se destruye el identificador de ventana, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control propio quita del registro.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>Procesamiento de mensajes y teclado de ElementHost  
 Cuando se hospedan en un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplicación, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] teclado y el mensaje de procesamiento consta de las siguientes acciones:  
  
-   <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, y <xref:System.Windows.Interop.IKeyboardInputSite> implementaciones de interfaz.  
  
-   Teclas de tabulación y de dirección.  
  
-   Teclas de comando y claves del cuadro de diálogo.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]procesamiento de aceleradores.  
  
 En las siguientes secciones se describen estas partes más detalladamente.  
  
### <a name="interface-implementations"></a>Implementaciones de interfaces  
 En [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], se enrutan los mensajes de teclado para el identificador de ventana del control que tiene el foco. En el <xref:System.Windows.Forms.Integration.ElementHost> (control), estos mensajes se enrutan al elemento hospedado. Para lograr esto, la <xref:System.Windows.Forms.Integration.ElementHost> control proporciona un <xref:System.Windows.Interop.HwndSource> instancia. Si el <xref:System.Windows.Forms.Integration.ElementHost> control tiene el foco, el <xref:System.Windows.Interop.HwndSource> instancia enruta la mayoría de teclado de entrada para que pueden ser procesado por el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> clase.  
  
 El <xref:System.Windows.Interop.HwndSource> la clase implementa la <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite> interfaces.  
  
 La interoperabilidad del teclado se basa en la implementación de la <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> método con flecha y una clave de la PESTAÑA de identificador de clave proporcionados por el que se mueve el foco fuera de elementos hospedados.  
  
### <a name="tabbing-and-arrow-keys"></a>Tabulación y las teclas de dirección  
 El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] lógica de selección se asigna a la <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> y <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> navegación de clave de métodos para implementar la tabulación y dirección. Reemplazar el <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> método lleva a cabo esta asignación.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Las claves y claves del cuadro de diálogo de comandos  
 Para conceder a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la primera oportunidad para procesar las teclas de comando y las claves del cuadro de diálogo, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] comando preprocesamiento está conectado a la <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> método. Reemplazar el <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> método conecta las dos tecnologías.  
  
 Con el <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> método, los elementos hospedados pueden administrar cualquier mensaje de clave, como WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN o WM_SYSKEYUP, incluidas las claves de comando, como teclas TAB, ENTRAR, ESC y flecha. Si no se controla un mensaje de tecla, se envía a la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] jerarquía antecesor para el control.  
  
### <a name="accelerator-processing"></a>Procesamiento de aceleradores  
 Para procesar correctamente, los aceleradores [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] procesamiento del acelerador debe estar conectado a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> clase. Además, todos los mensajes WM_CHAR se deben enrutar correctamente a los elementos hospedados.  
  
 Dado que el valor predeterminado <xref:System.Windows.Interop.HwndSource> implementación de la <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> método `false`, los mensajes de WM_CHAR se procesan utilizando la lógica siguiente:  
  
-   El <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> método se invalida para asegurarse de que todos los mensajes WM_CHAR se reenvíen a los elementos hospedados.  
  
-   Si se presiona la tecla ALT, el mensaje es WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]no procesa previamente este mensaje a través de la <xref:System.Windows.Forms.Control.IsInputChar%2A> método. Por lo tanto, la <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> método se invalida para consultar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> para un acelerador registrado. Si se encuentra un acelerador registrado, <xref:System.Windows.Input.AccessKeyManager> lo procesa.  
  
-   Si no se presiona la tecla ALT, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> clase procesa la entrada no controlada. Si la entrada es un acelerador, el <xref:System.Windows.Input.AccessKeyManager> lo procesa. El <xref:System.Windows.Input.InputManager.PostProcessInput> evento está controlado para los mensajes WM_CHAR que no se han procesado.  
  
 Cuando el usuario presiona la tecla ALT, se muestran indicaciones visuales del acelerador en todo el formulario. Para admitir este comportamiento, todos los <xref:System.Windows.Forms.Integration.ElementHost> controles en el formulario activo reciban los mensajes WM_SYSKEYDOWN, con independencia de qué control tiene el foco.  
  
 Los mensajes se envían únicamente a <xref:System.Windows.Forms.Integration.ElementHost> controles en el formulario activo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
