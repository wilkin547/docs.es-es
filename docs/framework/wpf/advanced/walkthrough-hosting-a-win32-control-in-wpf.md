---
title: 'Tutorial: Hospedar un Control de Win32 en WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 047ccd4ea4ba83c8d7427559f3ee76cc3547a430
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747536"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Tutorial: Hospedar un Control de Win32 en WPF
Windows Presentation Foundation (WPF) proporciona un entorno rico para crear aplicaciones. Sin embargo, cuando tiene una inversión sustancial en código Win32, puede ser más efectivo reutilizar al menos parte de ese código en la aplicación de WPF en lugar de volver a escribir por completo. WPF proporciona un mecanismo sencillo para hospedar una ventana de Win32 en una página WPF.  
  
 En este tema le guiará a través de una aplicación, [hospedaje a Win32 ListBox Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), que aloja el control de un cuadro de lista de Win32. Este procedimiento general se puede extender para hospedar cualquier ventana de Win32.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 En este tema se da por supuesto un conocimiento básico de programación de WPF y Win32. Para obtener una introducción básica a la programación de WPF, vea [Introducción](../../../../docs/framework/wpf/getting-started/index.md). Para obtener una introducción a la programación de Win32, debe hacer referencia a cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* por Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tema se implementa en C#, hace uso de servicios de invocación de plataforma (PInvoke) para tener acceso a la API de Win32. Cierta familiaridad con PInvoke es útil, pero no esencial.  
  
> [!NOTE]
>  En este tema se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Puede obtener o ver el código completo de [hospedaje a Win32 ListBox Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico para hospedar una ventana de Win32 en una página WPF. En las secciones restantes se explican los detalles de cada paso.  
  
 El procedimiento de hospedaje básico es el siguiente:  
  
1.  Implemente una página de WPF para hospedar la ventana. Una técnica consiste en crear un <xref:System.Windows.Controls.Border> elemento que se va a reservar una sección de la página de la ventana hospedada.  
  
2.  Implementar una clase para hospedar el control que hereda de <xref:System.Windows.Interop.HwndHost>.  
  
3.  En esa clase, invalide el <xref:System.Windows.Interop.HwndHost> miembro de clase <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Crear la ventana hospedada como un elemento secundario de la ventana que contiene la página WPF. Aunque la programación convencional de WPF no es necesario crear explícitamente de él, la página de hospedaje es una ventana con un controlador (HWND). Recibirá el HWND de la página a través de la `hwndParent` parámetro de la <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> método. La ventana hospedada debe crearse como un elemento secundario del HWND.  
  
5.  Una vez que haya creado la ventana host, devuelva el HWND de la ventana hospedada. Si desea hospedar uno o más controles de Win32, normalmente crea una ventana host como elemento secundario del HWND y lo convierte los elementos secundarios de los controles de esa ventana host. Ajuste los controles en una ventana host proporciona una manera sencilla de la página WPF recibir notificaciones de los controles, que trata sobre algunos problemas específicos de Win32 con las notificaciones a través de los límites de HWND.  
  
6.  Controle los mensajes seleccionados que se envían a la ventana host, como las notificaciones de los controles secundarios. Hay dos formas de hacerlo.  
  
    -   Si prefiere controlar los mensajes en la clase de hospedaje, invalide el <xref:System.Windows.Interop.HwndHost.WndProc%2A> método de la <xref:System.Windows.Interop.HwndHost> clase.  
  
    -   Si prefiere tener WPF controle los mensajes, controlar el <xref:System.Windows.Interop.HwndHost> clase <xref:System.Windows.Interop.HwndHost.MessageHook> eventos en el código subyacente. Este evento se produce para cada mensaje recibido por la ventana hospedada. Si elige esta opción, debe invalidar igualmente <xref:System.Windows.Interop.HwndHost.WndProc%2A>, pero solo necesita una implementación mínima.  
  
7.  Invalidar el <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y <xref:System.Windows.Interop.HwndHost.WndProc%2A> métodos de <xref:System.Windows.Interop.HwndHost>. Debe invalidar estos métodos para satisfacer el <xref:System.Windows.Interop.HwndHost> contrato, pero solo puede necesitar proporcionar una implementación mínima.  
  
8.  En el archivo de código subyacente, cree una instancia de la clase que hospeda los controles y convertirlo en un elemento secundario de la <xref:System.Windows.Controls.Border> elemento que se va a hospedar la ventana.  
  
9. Comunicarse con la ventana hospedada mediante el envío de [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] mensajes y controle los mensajes de sus ventanas secundarias, como las notificaciones enviadas por los controles.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementar el diseño de página  
 El diseño de la página WPF que hospeda el ListBox Control consta de dos regiones. El lado izquierdo de la página hospeda varios controles WPF que proporcionan un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que permite manipular el control de Win32. La esquina superior derecha de la página tiene una región cuadrada para el control ListBox.  
  
 El código para implementar este diseño es bastante sencillo. El elemento raíz es un <xref:System.Windows.Controls.DockPanel> que tiene dos elementos secundarios. El primero es un <xref:System.Windows.Controls.Border> elemento que hospeda el ListBox Control. Ocupa un cuadrado de 200x200 en la esquina superior derecha de la página. El segundo es un <xref:System.Windows.Controls.StackPanel> elemento que contiene un conjunto de controles WPF que muestran información y permiten manipular el ListBox Control mediante el establecimiento de propiedades de interoperación expuestas. Para cada uno de los elementos que son elementos secundarios de la <xref:System.Windows.Controls.StackPanel>, consulte el material de referencia para los distintos elementos utilizados para obtener más información sobre estos elementos son y lo que hacen, estos se muestran en el ejemplo de código siguiente, pero no se explican aquí (básica modelo de interoperación no requiere ninguna de ellas, se proporcionan para agregar cierta interactividad al ejemplo).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementar una clase para hospedar el control de Microsoft Win32  
 El núcleo de este ejemplo es la clase que realmente hospeda el control, ControlHost.cs. Hereda de <xref:System.Windows.Interop.HwndHost>. El constructor toma dos parámetros, alto y ancho, que se corresponde con el alto y ancho de la <xref:System.Windows.Controls.Border> elemento que hospeda el control ListBox. Estos valores se usan más adelante para asegurarse de que el tamaño del control coincide con el <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Hay también un conjunto de constantes. Estas constantes suelen tomarse de Winuser.h y permiten usar nombres convencionales al llamar a funciones de Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Invalidar BuildWindowCore para crear la ventana de Microsoft Win32  
 Invalide este método para crear la ventana de Win32 que se hospedará en la página y realizar la conexión entre la ventana y la página. Dado que este ejemplo implica hospedar un control ListBox, se crean dos ventanas. La primera es la ventana que se hospeda realmente en la página WPF. El control ListBox se crea como un elemento secundario de esa ventana.  
  
 El motivo de esto es simplificar el proceso de recepción de notificaciones desde el control. La <xref:System.Windows.Interop.HwndHost> clase le permite procesar los mensajes enviados a la ventana hospedada. Si el host Win32 controlar directamente, recibirá los mensajes enviados al bucle de mensajes interno del control. Puede mostrar el control y enviarle mensajes, pero no recibirá las notificaciones que el control envíe a su ventana primaria. Entre otras cosas, esto significa que no hay manera de detectar en qué momento el usuario interactúa con el control. Por eso, debe crear una ventana host y convertir el control en un elemento secundario de esa ventana. Esto le permite procesar los mensajes para la ventana host, incluidas las notificaciones que el control envía a la ventana. Para mayor comodidad, y dado que la ventana host es poco más que un simple contenedor del control, se hará referencia al paquete como un control ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Crear la ventana host y el control ListBox  
 Puede utilizar PInvoke para crear una ventana de host para el control creando y registrando una clase de ventana y así sucesivamente. Aun así, un enfoque mucho más sencillo consiste en crear una ventana con la clase de ventana "estática" predefinida. Esto le proporciona el procedimiento de ventana que necesita para recibir notificaciones del control y requiere una codificación mínima.  
  
 El HWND del control se expone a través de una propiedad de solo lectura, de modo que la página host pueda usarla para enviar mensajes al control.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 El control ListBox se crea como un elemento secundario de la ventana host. El alto y el ancho de ambas ventanas se establecen en los valores pasados al constructor, como se ha descrito anteriormente. Esto garantiza que el tamaño de la ventana host y del control sea idéntico al área reservada en la página.  Una vez creadas las ventanas, el ejemplo devuelve un <xref:System.Runtime.InteropServices.HandleRef> objeto que contiene el HWND de la ventana host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementar DestroyWindow y WndProc  
 Además <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, también debe invalidar el <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> métodos de la <xref:System.Windows.Interop.HwndHost>. En este ejemplo, los mensajes para el control se controlan mediante el <xref:System.Windows.Interop.HwndHost.MessageHook> controlador, de modo que la implementación de <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> es mínimo. En el caso de <xref:System.Windows.Interop.HwndHost.WndProc%2A>, establezca `handled` a `false` para indicar que no se ha controlado el mensaje y devolver 0. Para <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, simplemente destruya la ventana.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Hospedar el control en la página  
 Para hospedar el control en la página, primero se crea una nueva instancia de la `ControlHost` clase. Pase el alto y ancho del elemento border que contiene el control (`ControlHostElement`) a la `ControlHost` constructor. Esto garantiza que el control ListBox tenga el tamaño correcto. Después, hospede el control en la página mediante la asignación de la `ControlHost` de objeto para el <xref:System.Windows.Controls.Decorator.Child%2A> propiedad del host <xref:System.Windows.Controls.Border>.  
  
 El ejemplo adjunta un controlador para el <xref:System.Windows.Interop.HwndHost.MessageHook> eventos de la `ControlHost` para recibir mensajes desde el control. Este evento se genera para cada mensaje enviado a la ventana hospedada. En este caso, estos son los mensajes enviados a la ventana que contiene el control ListBox real, incluidas las notificaciones del control. En el ejemplo se llama a SendMessage para obtener información del control y modificar su contenido. En la siguiente sección se describe en detalle la manera en que la página se comunica con el control.  
  
> [!NOTE]
>  Observe que hay dos declaraciones de PInvoke para SendMessage. Esto es necesario porque una usa la `wParam` parámetro para pasar una cadena y la otra lo usa para pasar un entero. Necesita una declaración distinta para cada firma para asegurarse de que los datos se serializan correctamente.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementar la comunicación entre el control y la página  
 Manipular el control mediante el envío de mensajes de Windows. El control le notifica en qué momento el usuario interactúa con él mediante el envío de notificaciones a la ventana host. El [hospedar un ListBox Control de Win32 en WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) ejemplo incluye una interfaz de usuario que proporciona varios ejemplos de cómo funciona esto:  
  
-   Anexar un elemento a la lista  
  
-   Eliminar el elemento seleccionado de la lista  
  
-   Mostrar el texto del elemento actualmente seleccionado  
  
-   Mostrar el número de elementos de la lista  
  
 El usuario también puede seleccionar un elemento en el cuadro de lista haciendo clic en él, tal como haría para una aplicación de Win32 convencional. Los datos mostrados se actualizan cada vez que el usuario cambia el estado del cuadro de lista al seleccionar, agregar o anexar un elemento.  
  
 Para anexar elementos, enviar el cuadro de lista un [ `LB_ADDSTRING` mensaje](/windows/desktop/Controls/lb-addstring). Para eliminar elementos, enviar [ `LB_GETCURSEL` ](/windows/desktop/Controls/lb-getcursel) para obtener el índice de la selección actual y, a continuación, [ `LB_DELETESTRING` ](/windows/desktop/Controls/lb-deletestring) para eliminar el elemento. El ejemplo también envía [ `LB_GETCOUNT` ](/windows/desktop/Controls/lb-getcount)y usa el valor devuelto para actualizar la pantalla que muestra el número de elementos. Ambas instancias de [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) utilizar una de las declaraciones de PInvoke descritas en la sección anterior.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Cuando el usuario selecciona un elemento o cambia su selección, el control notifica a la ventana host mediante el envío de un [ `WM_COMMAND` mensaje](/windows/desktop/menurc/wm-command), que provoca el <xref:System.Windows.Interop.HwndHost.MessageHook> eventos de la página. El controlador recibe la misma información que el procedimiento de ventana principal de la ventana host. También pasa una referencia a un valor booleano, `handled`. Establece `handled` a `true` para indicar que ha controlado el mensaje y no es necesario ningún procesamiento adicional.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) se envía por una serie de motivos, por lo que debe examinar el identificador de notificación para determinar si se trata de un evento que desea controlar. El identificador se encuentra en la palabra alta de la `wParam` parámetro. El ejemplo usa los operadores bit a bit para extraer el identificador. Si el usuario ha realizado o cambiado su selección, el identificador será [ `LBN_SELCHANGE` ](/windows/desktop/Controls/lbn-selchange).  
  
 Cuando [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx) es recibe, el ejemplo obtiene el índice del elemento seleccionado mediante el envío del control una [ `LB_GETCURSEL` mensaje](/windows/desktop/Controls/lb-getcursel). Para obtener el texto, cree primero un <xref:System.Text.StringBuilder>. A continuación, que se envíe al control un [ `LB_GETTEXT` mensaje](/windows/desktop/Controls/lb-gettext). Pase el vacío <xref:System.Text.StringBuilder> objeto como el `wParam` parámetro. Cuando [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) que devuelve el <xref:System.Text.StringBuilder> contendrá el texto del elemento seleccionado. Este uso de [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) requiere otra declaración PInvoke.  
  
 Por último, establezca `handled` a `true` para indicar que se ha controlado el mensaje.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Interop.HwndHost>
- [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
- [Tutorial: Mi primera aplicación de escritorio WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
