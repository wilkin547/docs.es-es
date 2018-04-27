---
title: 'Tutorial: Hospedar un control de Win32 en WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab80f39a15952bee8296166ea19a78498c3c1b23
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Tutorial: Hospedar un control de Win32 en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] código, puede ser más eficaz volver a usar al menos parte de ese código en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación en lugar de escribirlo completamente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Proporciona un mecanismo sencillo para hospedar un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página.  
  
 Este tema le guía a través de una aplicación, [hospedar un Control de cuadro de lista de Win32 en WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998), que hospeda un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control de cuadro de lista. Este procedimiento general se puede extender para hospedar cualquier [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 Este tema supone una familiarización básica con ambos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de programación. Para obtener una introducción básica a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de programación, vea [Introducción](../../../../docs/framework/wpf/getting-started/index.md). Para obtener una introducción a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de programación, debe hacer referencia a cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* por Charles Petzold.  
  
 Dado que el ejemplo que se incluye en este tema se implementa en C#, facilita el uso de [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)] para tener acceso a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]. Cierta familiaridad con [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] es útil, pero no es esencial.  
  
> [!NOTE]
>  En este tema se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Puede obtener o ver el código completo de [hospedar un Control de cuadro de lista de Win32 en WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico para hospedar una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página. En las secciones restantes se explican los detalles de cada paso.  
  
 El procedimiento de hospedaje básico es el siguiente:  
  
1.  Implemente un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página para hospedar la ventana. Una de estas técnicas consiste en crear un <xref:System.Windows.Controls.Border> elemento que se va a reservar una sección de la página de la ventana hospedada.  
  
2.  Implementar una clase para hospedar el control que se hereda de <xref:System.Windows.Interop.HwndHost>.  
  
3.  En esa clase, invalide el <xref:System.Windows.Interop.HwndHost> miembro de la clase <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Crear la ventana hospedada como un elemento secundario de la ventana que contiene la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página. Aunque convencional [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no es necesario que la programación de manera explícita que use del mismo, la página de hospedaje es una ventana con un identificador (HWND). Aparecerá la página HWND a través de la `hwndParent` parámetro de la <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> método. La ventana hospedada debe crearse como un elemento secundario del HWND.  
  
5.  Una vez que haya creado la ventana host, devuelva el HWND de la ventana hospedada. Si desea hospedar uno o varios [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controles, normalmente crea una ventana host como un elemento secundario de HWND y lo convierte los elementos secundarios de controles de esa ventana host. Ajuste los controles en una ventana host proporciona una manera sencilla para su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página para recibir notificaciones de los controles que se tratan algunas determinado [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] problemas con las notificaciones a través del límite HWND.  
  
6.  Controle los mensajes seleccionados que se envían a la ventana host, como las notificaciones de los controles secundarios. Existen dos formas de lograr esto.  
  
    -   Si desea controlar los mensajes de la clase de hospedaje, invalide el <xref:System.Windows.Interop.HwndHost.WndProc%2A> método de la <xref:System.Windows.Interop.HwndHost> clase.  
  
    -   Si prefiere tener la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlar los mensajes, controlar el <xref:System.Windows.Interop.HwndHost> clase <xref:System.Windows.Interop.HwndHost.MessageHook> evento en el código subyacente. Este evento se produce para cada mensaje recibido por la ventana hospedada. Si elige esta opción, debe invalidar <xref:System.Windows.Interop.HwndHost.WndProc%2A>, pero sólo necesita una implementación mínima.  
  
7.  Invalidar el <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y <xref:System.Windows.Interop.HwndHost.WndProc%2A> métodos de <xref:System.Windows.Interop.HwndHost>. Debe invalidar estos métodos para satisfacer el <xref:System.Windows.Interop.HwndHost> contrato, pero solo puede necesitar proporcionar una implementación mínima.  
  
8.  En el archivo de código subyacente, cree una instancia de la clase que hospeda los controles y conviértala en un elemento secundario de la <xref:System.Windows.Controls.Border> elemento que se va a hospedar la ventana.  
  
9. Comunicarse con la ventana hospedada enviándole [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] mensajes y mensajes de control de sus ventanas secundarias, como las notificaciones enviadas por los controles.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementar el diseño de página  
 El diseño de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página que hospeda el ListBox Control consta de dos regiones. El lado izquierdo de la página hospeda varios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles que proporcionan un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que permite manipular el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control. La esquina superior derecha de la página tiene una región cuadrada para el control ListBox.  
  
 El código para implementar este diseño es muy sencillo. El elemento raíz es un <xref:System.Windows.Controls.DockPanel> que tiene dos elementos secundarios. El primero es un <xref:System.Windows.Controls.Border> elemento que hospeda el Control de cuadro de lista. Ocupa un cuadrado de 200x200 en la esquina superior derecha de la página. El segundo es un <xref:System.Windows.Controls.StackPanel> elemento que contiene un conjunto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles que muestran información y permiten manipular el ListBox Control estableciendo propiedades de interoperación exponen. Para cada uno de los elementos que son elementos secundarios de la <xref:System.Windows.Controls.StackPanel>, consulte el material de referencia para los distintos elementos utilizados para obtener más información sobre estos elementos son y qué hacen, estos se muestran en el ejemplo de código siguiente, pero no estará explicados aquí (básica modelo de interoperación no requiere ninguna de ellas, que se proporcionan para agregar parte de esta interactividad al ejemplo).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementar una clase para hospedar el control de Microsoft Win32  
 El núcleo de este ejemplo es la clase que realmente hospeda el control, ControlHost.cs. Hereda de <xref:System.Windows.Interop.HwndHost>. El constructor toma dos parámetros, alto y ancho, que se corresponde con el alto y ancho de la <xref:System.Windows.Controls.Border> elemento que hospeda el control de cuadro de lista. Estos valores se usan más adelante para asegurarse de que el tamaño del control coincide con el <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Hay también un conjunto de constantes. Estas constantes se obtienen principalmente de Winuser.h y le permiten utilizar nombres convencionales al llamar a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] funciones.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Invalidar BuildWindowCore para crear la ventana de Microsoft Win32  
 Invalide este método para crear el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana que se hospedará en la página y realizar la conexión entre la ventana y la página. Dado que este ejemplo implica hospedar un control ListBox, se crean dos ventanas. La primera es la ventana que se hospeda realmente en la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página. El control ListBox se crea como un elemento secundario de esa ventana.  
  
 El motivo de esto es simplificar el proceso de recepción de notificaciones desde el control. La <xref:System.Windows.Interop.HwndHost> clase le permite procesar los mensajes enviados a la ventana que lo hospeda. Si hospeda un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] controlar directamente, recibirá los mensajes enviados al bucle de mensajes interno del control. Puede mostrar el control y enviarle mensajes, pero no recibirá las notificaciones que el control envíe a su ventana primaria. Entre otras cosas, esto significa que no hay manera de detectar en qué momento el usuario interactúa con el control. Por eso, debe crear una ventana host y convertir el control en un elemento secundario de esa ventana. Esto le permite procesar los mensajes para la ventana host, incluidas las notificaciones que el control envía a la ventana. Para mayor comodidad, y dado que la ventana host es poco más que un simple contenedor del control, se hará referencia al paquete como un control ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Crear la ventana host y el control ListBox  
 Puede usar [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] para crear una ventana de host para el control creando y registrando una clase de ventana y así sucesivamente. Aun así, un enfoque mucho más sencillo consiste en crear una ventana con la clase de ventana "estática" predefinida. Esto le proporciona el procedimiento de ventana que necesita para recibir notificaciones del control y requiere una codificación mínima.  
  
 El HWND del control se expone a través de una propiedad de solo lectura, de modo que la página host pueda usarla para enviar mensajes al control.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 El control ListBox se crea como un elemento secundario de la ventana host. El alto y el ancho de ambas ventanas se establecen en los valores pasados al constructor, como se ha descrito anteriormente. Esto garantiza que el tamaño de la ventana host y del control sea idéntico al área reservada en la página.  Una vez creadas las ventanas, el ejemplo devuelve una <xref:System.Runtime.InteropServices.HandleRef> objeto que contiene el HWND de la ventana host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementar DestroyWindow y WndProc  
 Además <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, también debe invalidar el <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> métodos de la <xref:System.Windows.Interop.HwndHost>. En este ejemplo, se administran los mensajes para el control con el <xref:System.Windows.Interop.HwndHost.MessageHook> controlador, por lo tanto, la implementación de <xref:System.Windows.Interop.HwndHost.WndProc%2A> y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> es mínimo. En el caso de <xref:System.Windows.Interop.HwndHost.WndProc%2A>, establezca `handled` a `false` para indicar que el mensaje no se ha controlado y devuelva 0. Para <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, simplemente destruya la ventana.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Hospedar el control en la página  
 Para hospedar el control en la página, primero se crea una nueva instancia de la `ControlHost` clase. Pase el alto y ancho del elemento de borde que contiene el control (`ControlHostElement`) a la `ControlHost` constructor. Esto garantiza que el control ListBox tenga el tamaño correcto. A continuación, hospedar el control en la página mediante la asignación de la `ControlHost` el objeto a la <xref:System.Windows.Controls.Decorator.Child%2A> propiedad del host <xref:System.Windows.Controls.Border>.  
  
 El ejemplo asocia un controlador para el <xref:System.Windows.Interop.HwndHost.MessageHook> eventos de la `ControlHost` para recibir mensajes desde el control. Este evento se genera para cada mensaje enviado a la ventana hospedada. En este caso, estos son los mensajes enviados a la ventana que contiene el control ListBox real, incluidas las notificaciones del control. En el ejemplo se llama a SendMessage para obtener información del control y modificar su contenido. En la siguiente sección se describe en detalle la manera en que la página se comunica con el control.  
  
> [!NOTE]
>  Tenga en cuenta que hay dos [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] declaraciones para SendMessage. Esto es necesario porque una utiliza el `wParam` parámetro que se pasa una cadena y la otra lo utiliza para pasar un entero. Necesita una declaración distinta para cada firma para asegurarse de que los datos se serializan correctamente.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementar la comunicación entre el control y la página  
 Manipular el control mediante su envío [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)] mensajes. El control le notifica en qué momento el usuario interactúa con él mediante el envío de notificaciones a la ventana host. El [hospedar un Control de cuadro de lista de Win32 en WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159998) ejemplo incluye una interfaz de usuario que proporciona varios ejemplos de cómo funciona esto:  
  
-   Anexar un elemento a la lista  
  
-   Eliminar el elemento seleccionado de la lista  
  
-   Mostrar el texto del elemento actualmente seleccionado  
  
-   Mostrar el número de elementos de la lista  
  
 El usuario también puede seleccionar un elemento en el cuadro de lista haciendo clic en él, tal como haría con un convencional [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación. Los datos mostrados se actualizan cada vez que el usuario cambia el estado del cuadro de lista al seleccionar, agregar o anexar un elemento.  
  
 Para anexar elementos, envíe al cuadro de lista un mensaje LB_ADDSTRING. Si quiere eliminar elementos, envíe LB_GETCURSEL para obtener el índice de la selección actual y, después, LB_DELETESTRING para eliminar el elemento. En el ejemplo también se envía LB_GETCOUNT y se usa el valor devuelto para actualizar la pantalla que muestra el número de elementos. Ambas instancias de SendMessage usan uno de los [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] declaraciones descritas en la sección anterior.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Cuando el usuario selecciona un elemento o cambia su selección, el control notifica a la ventana de host mediante el envío de un mensaje WM_COMMAND, que provoca la <xref:System.Windows.Interop.HwndHost.MessageHook> eventos de la página. El controlador recibe la misma información que el procedimiento de ventana principal de la ventana host. También pasa una referencia a un valor booleano, `handled`. Establece `handled` a `true` para indicar que ha controlado el mensaje y no es necesario ningún procesamiento adicional.  
  
 WM_COMMAND se envía por diversas razones, por lo que debe examinar el identificador de la notificación para determinar si se trata de un evento que quiere controlar. El identificador se encuentra en los bytes más significativos de la `wParam` parámetro. Puesto que [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] does no tiene una macro HIWORD, el ejemplo usa los operadores bit a bit para extraer el identificador. Si el usuario ha realizado su selección o la ha cambiado, el identificador será LBN_SELCHANGE.  
  
 Cuando se recibe LBN_SELCHANGE, el ejemplo obtiene el índice del elemento seleccionado mediante el envío de un mensaje LB_GETCURSEL al control. Para obtener el texto, cree primero un <xref:System.Text.StringBuilder>. Después, envíe al control un mensaje LB_GETTEXT. Pasar el vacío <xref:System.Text.StringBuilder> objeto como el `wParam` parámetro. Cuando se devuelve SendMessage, el <xref:System.Text.StringBuilder> contendrá el texto del elemento seleccionado. Este uso de SendMessage todavía requiere otro [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] declaración.  
  
 Por último, establezca `handled` a `true` para indicar que se ha administrado el mensaje.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Interop.HwndHost>  
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Tutorial: Mi primera aplicación de escritorio WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
