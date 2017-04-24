---
title: "Tutorial: Hospedar un control de Win32 en WPF | Microsoft Docs"
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
  - "hospedar control Win32 en WPF"
  - "código Win32, interoperabilidad con WPF"
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Tutorial: Hospedar un control de Win32 en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno enriquecido para la creación de aplicaciones.  Sin embargo, cuando se tiene una inversión sustancial en código [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], puede resultar más eficaz reutilizar al menos parte de ese código en la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirlo todo por completo.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo sencillo para hospedar una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en una página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 En este tema se explica cómo crear una aplicación, [Hosting a Win32 ListBox Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998), que hospeda un control de cuadro de lista de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Este procedimiento general se puede extender para hospedar cualquier ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
   
  
<a name="requirements"></a>   
## Requisitos  
 En este tema se da por hecho que está familiarizado con la programación básica en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Para obtener una introducción básica a la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Introducción](../../../../docs/framework/wpf/getting-started/index.md).  Para obtener una introducción a la programación en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], puede consultar cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* escrito por Charles Petzold.  
  
 Como el ejemplo que acompaña a este tema se implementa en [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], se utiliza [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)] para tener acceso a la [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Puede ser útil tener algún conocimiento sobre [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)], pero no esencial.  
  
> [!NOTE]
>  En este tema se incluyen varios ejemplos de código del ejemplo asociado.  Sin embargo, para facilitar la legibilidad, no se incluye el código de ejemplo completo.  Puede obtener o ver el código completo en [Hosting a Win32 ListBox Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998).  
  
<a name="basic_procedure"></a>   
## El procedimiento básico  
 En esta sección se describe el procedimiento básico para hospedar una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En las demás secciones se explican los detalles de cada paso.  
  
 El procedimiento de hospedaje básico es el siguiente:  
  
1.  Implemente una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para hospedar la ventana.  Una técnica es crear un elemento <xref:System.Windows.Controls.Border> para reservar una sección de la página de la ventana hospedada.  
  
2.  Implemente una clase para hospedar el control que se hereda de <xref:System.Windows.Interop.HwndHost>.  
  
3.  En esta clase, invalide el miembro <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> de la clase <xref:System.Windows.Interop.HwndHost>.  
  
4.  Cree la ventana hospedada como un elemento secundario de la ventana que contiene la página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Aunque la programación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] convencional no necesita utilizar esta ventana explícitamente, la página de hospedaje es una ventana con un controlador \(HWND\).  Recibirá la página HWND a través del parámetro `hwndParent` del método <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  La ventana hospedada se debe crear como un elemento secundario de HWND.  
  
5.  Una vez creada la ventana host, devuelva el HWND de la ventana hospedada.  Si desea hospedar uno o varios controles [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], normalmente creará una ventana host como un elemento secundario de HWND y convertirá los controles en elementos secundarios de esa ventana host.  Alojar los controles en una ventana host es un modo simple de permitir que la página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reciba las notificaciones de los controles y de abordar algunos de los problemas de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con las notificaciones a través de los límites de HWND.  
  
6.  Controle algunos de los mensajes enviados a la ventana host, como las notificaciones de los controles secundarios.  Existen dos formas de lograr esto.  
  
    -   Si prefiere controlar los mensajes en la clase de hospedaje, invalide el método <xref:System.Windows.Interop.HwndHost.WndProc%2A> de la clase <xref:System.Windows.Interop.HwndHost>.  
  
    -   Si prefiere que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controle los mensajes, controle el evento <xref:System.Windows.Interop.HwndHost.MessageHook> de la clase <xref:System.Windows.Interop.HwndHost> en el código subyacente.  Este evento se produce para cada mensaje recibido por la ventana hospedada.  Si elige esta opción, debe invalidar igualmente <xref:System.Windows.Interop.HwndHost.WndProc%2A>, pero sólo necesita una implementación mínima.  
  
7.  Invalide los métodos <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y <xref:System.Windows.Interop.HwndHost.WndProc%2A> de <xref:System.Windows.Interop.HwndHost>.  Debe invalidar estos métodos para cumplir el contrato de <xref:System.Windows.Interop.HwndHost>, pero es posible que sólo necesite proporcionar una implementación mínima.  
  
8.  En su archivo de código subyacente, cree una instancia de la clase que hospeda los controles y conviértala en un elemento secundario del elemento <xref:System.Windows.Controls.Border> que va a hospedar la ventana.  
  
9. Comuníquese con la ventana hospedada enviándole mensajes [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] y controlando los mensajes de sus ventanas secundarias, como las notificaciones enviadas por los controles.  
  
<a name="page_layout"></a>   
## Implementar el diseño de página  
 El diseño de la página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que hospeda el control ListBox consta de dos regiones.  El margen izquierdo de la página hospeda varios controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que proporcionan una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que le permite manipular el control [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  La esquina superior derecha de la página tiene una región cuadrada para el control ListBox hospedado.  
  
 El código para implementar este diseño es bastante simple.  El elemento raíz es un <xref:System.Windows.Controls.DockPanel> que tiene dos elementos secundarios.  El primero es un elemento <xref:System.Windows.Controls.Border> que hospeda el control ListBox.  Ocupa un espacio cuadrado de 200 x 200 en la esquina superior derecha de la página.  El segundo es un elemento <xref:System.Windows.Controls.StackPanel> que contiene un conjunto de los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que muestran información y le permiten manipular el control ListBox estableciendo las propiedades de interoperación expuestas.  Para cada uno de los elementos que son elementos secundarios de <xref:System.Windows.Controls.StackPanel>, consulte el material de referencia de los distintos elementos utilizados para obtener detalles sobre qué son estos elemento y qué hacen. Estos elementos se muestran en el código de ejemplo siguiente, pero no se ofrece una explicación de ellos \(no son necesarios para el modelo básico de interoperación; se proporcionan para agregar interactividad al ejemplo\).  
  
 [!code-xml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## Implementar una clase para hospedar el control Microsoft Win32  
 El núcleo de este ejemplo es la clase que realmente hospeda el control, ControlHost.cs.  Se hereda de <xref:System.Windows.Interop.HwndHost>.  El constructor toma dos parámetros, el alto y el ancho, que se corresponden con el alto y ancho del elemento <xref:System.Windows.Controls.Border> que hospeda el control ListBox.  Estos valores se utilizan después para garantizar que el tamaño del control coincide con el elemento <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 También hay un conjunto de constantes.  Estas constantes se obtienen principalmente de Winuser.h y permiten utilizar nombres convencionales al llamar a las funciones [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### Invalidar BuildWindowCore para crear la ventana Microsoft Win32  
 Este método se invalida para crear la ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] que se hospedará en la página y realizar la conexión entre la ventana y la página.  Como este ejemplo implica hospedar un control ListBox Control, se crean dos ventanas.  La primera es la ventana que se hospeda realmente en la página [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El control ListBox se crea como un elemento secundario de esa ventana.  
  
 La razón de este enfoque es simplificar el proceso de recepción de notificaciones desde el control.  La clase <xref:System.Windows.Interop.HwndHost> permite procesar los mensajes enviados a la ventana hospedada.  Si hospeda directamente un control [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], recibirá los mensajes enviados al bucle de mensajes interno del control.  Puede mostrar el control y enviarle mensajes, pero no recibirá las notificaciones que el control envía a su ventana primaria.  Esto significa, entre otras cosas, que no hay forma de detectar cuándo el usuario interactúa con el control.  En lugar de ello, cree una ventana host y convierta el control en un elemento secundario de esa ventana.  Esto le permite procesar los mensajes de la ventana host incluidas las notificaciones enviadas a ella por el control.  Por comodidad, como la ventana host es básicamente un contenedor simple del control, el paquete recibirá el nombre de control ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### Crear la ventana host y el control ListBox  
 Puede utilizar [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] para crear una ventana host para el control creando y registrando una clase de ventana, etc.  Sin embargo, un procedimiento mucho más simple es crear una ventana con la clase de ventana "estática" predefinida.  De esta forma, obtendrá el procedimiento de la ventana que necesita para recibir las notificaciones del control, sin tener apenas que escribir código.  
  
 El HWND del control se expone a través de una propiedad de sólo lectura, que la página host puede utilizar para enviar mensajes al control.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 El control ListBox se crea como un elemento secundario de la ventana host.  El alto y ancho de ambas ventanas se establecen en los valores pasados al constructor, descritos anteriormente.  Esto garantiza que el tamaño de la ventana host y el control sea idéntico al del área reservada en la página.  Una vez creadas las ventanas, el ejemplo devuelve un objeto <xref:System.Runtime.InteropServices.HandleRef> que contiene el HWND de la ventana host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### Implementar DestroyWindow y WndProc  
 Además de <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, debe invalidar también los métodos <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> de <xref:System.Windows.Interop.HwndHost>.  En este ejemplo, los mensajes del control se controlan mediante el controlador <xref:System.Windows.Interop.HwndHost.MessageHook>, por lo que la implementación de <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> es mínima.  En el caso de <xref:System.Windows.Interop.HwndHost.WndProc%2A>, establezca `handled` en `false` para indicar que el mensaje no se ha controlado y devuelva 0.  Para <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, simplemente destruya la ventana.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## Hospedar el control en la página  
 Para hospedar el control en la página, primero debe crear una nueva instancia de la clase `ControlHost`.  Pase el alto y ancho del elemento de esquina que contiene el control \(`ControlHostElement`\) al constructor `ControlHost`.  De esta forma, se asegurará de que el control ListBox tiene el tamaño correcto.  A continuación, hospede el control en la página asignando el objeto `ControlHost` a la propiedad <xref:System.Windows.Controls.Decorator.Child%2A> del <xref:System.Windows.Controls.Border> host.  
  
 En el ejemplo se asocia un controlador al evento <xref:System.Windows.Interop.HwndHost.MessageHook> de `ControlHost` para recibir los mensajes del control.  Este evento se provoca para cada mensaje enviado a la ventana hospedada.  En este caso, éstos son los mensajes enviados a la ventana que contiene el control ListBox real, incluidas las notificaciones del control.  En el ejemplo se llama a SendMessage para obtener información del control y modificar su contenido.  Los detalles sobre cómo la página se comunica con el control se describen en la sección siguiente.  
  
> [!NOTE]
>  Observe que hay dos declaraciones [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] para SendMessage.  Esto es necesario porque una utiliza el parámetro `wParam` para pasar una cadena y la otra lo utiliza para pasar un valor entero.  Necesita una declaración distinta para cada firma con el fin de garantizar que las referencias a los datos se calculan correctamente.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## Implementar la comunicación entre el control y la página  
 El control se manipula enviándole mensajes [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)].  El control le indica cuándo el usuario interactúa con él enviando notificaciones a su ventana host.  En el ejemplo [Hosting a Win32 ListBox Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998) se incluye una interfaz de usuario que proporciona varios ejemplos sobre cómo funciona esto:  
  
-   Asocie un elemento a la lista.  
  
-   Elimine el elemento seleccionado de la lista  
  
-   Muestre el texto del elemento actualmente seleccionado.  
  
-   Muestre el número de elementos de la lista.  
  
 El usuario puede seleccionar también un elemento del cuadro de lista haciendo clic en él, como ocurre en cualquier aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] convencional.  Los datos mostrados se actualizan cada vez que el usuario cambia el estado del cuadro de lista seleccionándolo, agregando o anexando un elemento.  
  
 Para anexar elementos, envíe un mensaje LB\_ADDSTRING al cuadro de lista.  Para eliminar elementos, envíe LB\_GETCURSEL para obtener el índice de la selección actual y, después, LB\_DELETESTRING para eliminar el elemento.  En el ejemplo se envía también LB\_GETCOUNT y se utiliza el valor devuelto para actualizar la pantalla que muestra el número de elementos.  Ambas instancias de SendMessage utilizan una de las declaraciones [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] descritas en la sección anterior.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Cuando el usuario selecciona un elemento que cambia su selección, el control se lo notifica a la ventana host enviándole un mensaje WM\_COMMAND, que provoca el evento <xref:System.Windows.Interop.HwndHost.MessageHook> para la página.  El controlador recibe la misma información que el procedimiento de la ventana principal de la ventana host.  Pasa también una referencia a un valor booleano, `handled`.  `handled` se establece en `true` para indicar que se ha controlado el mensaje, y ya no hace falta más procesamiento.  
  
 WM\_COMMAND se envía por varias razones, por lo que debe examinar el identificador de la notificación para determinar si es un evento que desea controlar.  El identificador se incluye en los bytes más significativos del parámetro `wParam`.  Como [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] no tiene una macro HIWORD, en el ejemplo se utilizan operadores bit a bit para extraer el identificador.  Si el usuario ha realizado o cambiado su selección, el identificador será LBN\_SELCHANGE.  
  
 Cuando se recibe LBN\_SELCHANGE, el ejemplo obtiene el índice del elemento seleccionado enviando un mensaje LB\_GETCURSEL al control.  Para obtener el texto, primero creará <xref:System.Text.StringBuilder>.  A continuación, enviará un mensaje LB\_GETTEXT al control.  Pase el objeto <xref:System.Text.StringBuilder> vacío como parámetro `wParam`.  Cuando SendMessage termine de procesarse, <xref:System.Text.StringBuilder> contendrá el texto del elemento seleccionado.  Este uso de SendMessage requiere una nueva declaración [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)].  
  
 Por último, establezca `handled` en `true` para indicar que el mensaje se ha controlado.  
  
## Vea también  
 <xref:System.Windows.Interop.HwndHost>   
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)