---
title: 'Tutorial: Hospedar control Win32 en WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: cc27189afd2185d5f0a1eeacccf4c537dd3d9c2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917541"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Tutorial: Hospedar control Win32 en WPF
Windows Presentation Foundation (WPF) proporciona un entorno completo para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en código Win32, puede ser más eficaz reutilizar al menos parte de ese código en la aplicación WPF en lugar de volver a escribirlo completamente. WPF proporciona un mecanismo sencillo para hospedar una ventana de Win32, en una página de WPF.  
  
 Este tema le guía a través de una aplicación, que [hospeda un control ListBox de Win32 en el ejemplo de WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), que hospeda un control de cuadro de lista de Win32. Este procedimiento general se puede extender para hospedar cualquier ventana de Win32.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 En este tema se da por supuesto que está familiarizado con la programación de la API de Windows y WPF. Para obtener una introducción básica a la programación de WPF, vea [Introducción](../getting-started/index.md). Para obtener una introducción a la programación de la API de Windows, consulte cualquiera de los numerosos libros del asunto, en determinadas *ventanas de programación* , de Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tema se implementa C#en, hace uso de los servicios de invocación de plataforma (PInvoke) para tener acceso a la API de Windows. Algunos conocimientos de PInvoke son útiles, pero no esenciales.  
  
> [!NOTE]
> En este tema se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Puede obtener o ver el código completo para [hospedar un control ListBox de Win32 en el ejemplo de WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico para hospedar una ventana de Win32 en una página de WPF. En las secciones restantes se explican los detalles de cada paso.  
  
 El procedimiento de hospedaje básico es el siguiente:  
  
1. Implemente una página de WPF para hospedar la ventana. Una técnica consiste en crear un <xref:System.Windows.Controls.Border> elemento para reservar una sección de la página para la ventana hospedada.  
  
2. Implemente una clase para hospedar el control que hereda <xref:System.Windows.Interop.HwndHost>de.  
  
3. En esa clase, invalide <xref:System.Windows.Interop.HwndHost> el <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>miembro de clase.  
  
4. Cree la ventana hospedada como un elemento secundario de la ventana que contiene la página de WPF. Aunque la programación de WPF convencional no necesita utilizarla explícitamente, la página de hospedaje es una ventana con un identificador (HWND). Recibirá el HWND <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> de la página `hwndParent` a través del parámetro del método. La ventana hospedada debe crearse como un elemento secundario del HWND.  
  
5. Una vez que haya creado la ventana host, devuelva el HWND de la ventana hospedada. Si desea hospedar uno o varios controles Win32, normalmente crea una ventana host como elemento secundario del HWND y hace que los controles sean secundarios de dicha ventana host. El ajuste de los controles en una ventana host proporciona una manera sencilla de que la página de WPF reciba notificaciones de los controles, lo que aborda algunos problemas específicos de Win32 con las notificaciones en el límite del HWND.  
  
6. Controle los mensajes seleccionados que se envían a la ventana host, como las notificaciones de los controles secundarios. Hay dos formas de hacerlo.  
  
    - Si prefiere controlar los mensajes en la clase de hospedaje, invalide el <xref:System.Windows.Interop.HwndHost.WndProc%2A> método de la <xref:System.Windows.Interop.HwndHost> clase.  
  
    - Si prefiere que WPF controle los mensajes, controle el <xref:System.Windows.Interop.HwndHost> evento de clase <xref:System.Windows.Interop.HwndHost.MessageHook> en el código subyacente. Este evento se produce para cada mensaje recibido por la ventana hospedada. Si elige esta opción, debe invalidar <xref:System.Windows.Interop.HwndHost.WndProc%2A>, pero solo necesita una implementación mínima.  
  
7. Invalide los <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> métodos <xref:System.Windows.Interop.HwndHost>y <xref:System.Windows.Interop.HwndHost.WndProc%2A> de. Debe invalidar estos métodos para satisfacer el <xref:System.Windows.Interop.HwndHost> contrato, pero solo es necesario proporcionar una implementación mínima.  
  
8. En el archivo de código subyacente, cree una instancia de la clase de hospedaje del control y conviértalo en un <xref:System.Windows.Controls.Border> elemento secundario del elemento que se va a hospedar en la ventana.  
  
9. Comunicarse con la ventana hospedada mediante el [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] envío de mensajes de ti y el control de los mensajes desde sus ventanas secundarias, como las notificaciones enviadas por los controles.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementar el diseño de página  
 El diseño de la página de WPF que hospeda el control ListBox se compone de dos regiones. En el lado izquierdo de la página se hospedan varios controles de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] WPF que proporcionan un que le permite manipular el control Win32. La esquina superior derecha de la página tiene una región cuadrada para el control ListBox.  
  
 El código para implementar este diseño es bastante sencillo. El elemento raíz es un <xref:System.Windows.Controls.DockPanel> que tiene dos elementos secundarios. El primero es un <xref:System.Windows.Controls.Border> elemento que hospeda el control ListBox. Ocupa un cuadrado de 200x200 en la esquina superior derecha de la página. El segundo es un <xref:System.Windows.Controls.StackPanel> elemento que contiene un conjunto de controles de WPF que muestran información y permiten manipular el control ListBox mediante el establecimiento de propiedades de interoperación expuestas. Para cada uno de los elementos que son elementos secundarios <xref:System.Windows.Controls.StackPanel>de, consulte el material de referencia de los distintos elementos que se usan para obtener detalles sobre lo que son estos elementos o lo que hacen, estos se enumeran en el código de ejemplo siguiente, pero no se explican aquí (el el modelo de interoperación no requiere ninguno de ellos, sino que se proporciona para agregar una interactividad al ejemplo.  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementar una clase para hospedar el control de Microsoft Win32  
 El núcleo de este ejemplo es la clase que realmente hospeda el control, ControlHost.cs. Hereda de <xref:System.Windows.Interop.HwndHost>. El constructor toma dos parámetros, height y width, que corresponden al alto y ancho del <xref:System.Windows.Controls.Border> elemento que hospeda el control ListBox. Estos valores se usan más adelante para asegurarse de que el tamaño del control coincide <xref:System.Windows.Controls.Border> con el elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Hay también un conjunto de constantes. Estas constantes se toman en gran medida de Winuser. h y permiten usar nombres convencionales al llamar a funciones de Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Invalidar BuildWindowCore para crear la ventana de Microsoft Win32  
 Invalide este método para crear la ventana Win32 que se hospedará en la página y establecer la conexión entre la ventana y la página. Dado que este ejemplo implica hospedar un control ListBox, se crean dos ventanas. La primera es la ventana que realmente se hospeda en la página de WPF. El control ListBox se crea como un elemento secundario de esa ventana.  
  
 El motivo de esto es simplificar el proceso de recepción de notificaciones desde el control. La <xref:System.Windows.Interop.HwndHost> clase permite procesar los mensajes enviados a la ventana que hospeda. Si hospeda un control Win32 directamente, recibirá los mensajes enviados al bucle de mensajes interno del control. Puede mostrar el control y enviarle mensajes, pero no recibirá las notificaciones que el control envíe a su ventana primaria. Entre otras cosas, esto significa que no hay manera de detectar en qué momento el usuario interactúa con el control. Por eso, debe crear una ventana host y convertir el control en un elemento secundario de esa ventana. Esto le permite procesar los mensajes para la ventana host, incluidas las notificaciones que el control envía a la ventana. Para mayor comodidad, y dado que la ventana host es poco más que un simple contenedor del control, se hará referencia al paquete como un control ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Crear la ventana host y el control ListBox  
 Puede usar PInvoke para crear una ventana host para el control mediante la creación y el registro de una clase de ventana, etc. Aun así, un enfoque mucho más sencillo consiste en crear una ventana con la clase de ventana "estática" predefinida. Esto le proporciona el procedimiento de ventana que necesita para recibir notificaciones del control y requiere una codificación mínima.  
  
 El HWND del control se expone a través de una propiedad de solo lectura, de modo que la página host pueda usarla para enviar mensajes al control.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 El control ListBox se crea como un elemento secundario de la ventana host. El alto y el ancho de ambas ventanas se establecen en los valores pasados al constructor, como se ha descrito anteriormente. Esto garantiza que el tamaño de la ventana host y del control sea idéntico al área reservada en la página.  Una vez creadas las ventanas, el ejemplo devuelve un <xref:System.Runtime.InteropServices.HandleRef> objeto que contiene el HWND de la ventana host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementar DestroyWindow y WndProc  
 Además de <xref:System.Windows.Interop.HwndHost.WndProc%2A> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> <xref:System.Windows.Interop.HwndHost>, también debe invalidar los métodos y de. <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> En este ejemplo, el <xref:System.Windows.Interop.HwndHost.MessageHook> controlador controla los mensajes para el control, de modo que la implementación de <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> es mínima. En el caso de <xref:System.Windows.Interop.HwndHost.WndProc%2A>, establezca `handled` en `false` para indicar que el mensaje no se controló y devolvió 0. Para <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, simplemente destruya la ventana.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Hospedar el control en la página  
 Para hospedar el control en la página, primero debe crear una nueva instancia de `ControlHost` la clase. Pase el alto y el ancho del elemento de borde que contiene el control`ControlHostElement`() `ControlHost` al constructor. Esto garantiza que el control ListBox tenga el tamaño correcto. A continuación, debe hospedar el control en la página asignando `ControlHost` el objeto a <xref:System.Windows.Controls.Decorator.Child%2A> la propiedad del host <xref:System.Windows.Controls.Border>.  
  
 En el ejemplo se adjunta un controlador al <xref:System.Windows.Interop.HwndHost.MessageHook> evento `ControlHost` de para recibir mensajes del control. Este evento se genera para cada mensaje enviado a la ventana hospedada. En este caso, estos son los mensajes enviados a la ventana que contiene el control ListBox real, incluidas las notificaciones del control. En el ejemplo se llama a SendMessage para obtener información del control y modificar su contenido. En la siguiente sección se describe en detalle la manera en que la página se comunica con el control.  
  
> [!NOTE]
> Observe que hay dos declaraciones PInvoke para SendMessage. Esto es necesario porque uno usa el `wParam` parámetro para pasar una cadena y el otro lo usa para pasar un entero. Necesita una declaración distinta para cada firma para asegurarse de que los datos se serializan correctamente.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementar la comunicación entre el control y la página  
 El control se manipula mediante el envío de mensajes de Windows. El control le notifica en qué momento el usuario interactúa con él mediante el envío de notificaciones a la ventana host. El ejemplo [Hosting a Win32 ListBox control in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) incluye una interfaz de usuario que proporciona varios ejemplos de cómo funciona esto:  
  
- Anexar un elemento a la lista  
  
- Eliminar el elemento seleccionado de la lista  
  
- Mostrar el texto del elemento actualmente seleccionado  
  
- Mostrar el número de elementos de la lista  
  
 El usuario también puede seleccionar un elemento en el cuadro de lista haciendo clic en él, tal como lo haría para una aplicación Win32 convencional. Los datos mostrados se actualizan cada vez que el usuario cambia el estado del cuadro de lista al seleccionar, agregar o anexar un elemento.  
  
 Para anexar elementos, envíe un [ `LB_ADDSTRING` mensaje](/windows/desktop/Controls/lb-addstring)al cuadro de lista. Para eliminar elementos, envíelo [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) para obtener el índice de la selección actual y, [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) a continuación, eliminar el elemento. El ejemplo también envía [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)y usa el valor devuelto para actualizar la pantalla que muestra el número de elementos. Ambas instancias de [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) usan una de las declaraciones PInvoke descritas en la sección anterior.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Cuando el usuario selecciona un elemento o cambia su selección, el control notifica a la ventana host mediante el envío de un [ `WM_COMMAND` mensaje](/windows/desktop/menurc/wm-command), que genera <xref:System.Windows.Interop.HwndHost.MessageHook> el evento para la página. El controlador recibe la misma información que el procedimiento de ventana principal de la ventana host. También pasa una referencia a un valor booleano, `handled`. Se establece `handled` en `true` para indicar que se ha controlado el mensaje y no se necesita ningún procesamiento adicional.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)se envía por diversos motivos, por lo que debe examinar el identificador de notificación para determinar si es un evento que desea controlar. El identificador está contenido en la palabra alta del `wParam` parámetro. El ejemplo utiliza operadores bit a bit para extraer el identificador. Si el usuario ha realizado o cambiado su selección, el identificador [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)será.  
  
 Cuando [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) se recibe, el ejemplo obtiene el índice del elemento seleccionado mediante el envío de un [ `LB_GETCURSEL` mensaje](/windows/desktop/Controls/lb-getcursel)al control. Para obtener el texto, primero debe crear un <xref:System.Text.StringBuilder>. A continuación, envía un [ `LB_GETTEXT` mensaje](/windows/desktop/Controls/lb-gettext)al control. Pase el objeto <xref:System.Text.StringBuilder> vacío `wParam` como parámetro. Cuando [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) devuelve<xref:System.Text.StringBuilder> , contendrá el texto del elemento seleccionado. Este uso de [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) requiere todavía otra declaración PInvoke.  
  
 Por último, `handled` establezca `true` en para indicar que se ha controlado el mensaje.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndHost>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
