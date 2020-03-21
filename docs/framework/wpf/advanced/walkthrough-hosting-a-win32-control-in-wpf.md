---
title: Hospedar un control Win32 en WPFWPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 5185e60640c652b79bd105db54830ac3acc57129
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186746"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>Tutorial: Hospedar un control Win32 en WPF
Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona un entorno enriquecido para crear aplicaciones. Sin embargo, cuando tiene una inversión sustancial en código Win32, puede ser más eficaz reutilizar al menos parte de ese código en la aplicación WPF en lugar de volver a escribirlo por completo. WPFWPF proporciona un mecanismo sencillo para hospedar una ventana Win32, en una página WPFWPF.  
  
 En este tema se le guía a través de una aplicación, [Hospedar un control ListBox de Win32 en ejemplo de WPF,](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)que hospeda un control de cuadro de lista de Win32. Este procedimiento general se puede extender al hospedaje de cualquier ventana Win32.  

<a name="requirements"></a>
## <a name="requirements"></a>Requisitos  
 En este tema se supone una familiaridad básica con la programación de WPF y la API de Windows. Para obtener una introducción básica a la programación de WPF, vea [Introducción](../getting-started/index.md). Para obtener una introducción a la programación de la API de Windows, consulte cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* de Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tema se implementa en C- , hace uso de Platform Invocation Services (PInvoke) para tener acceso a la API de Windows. Cierta familiaridad con PInvoke es útil, pero no esencial.  
  
> [!NOTE]
> En este tema se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Puede obtener o ver código completo desde [Hosting a Win32 ListBox Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico para hospedar una ventana Win32 en una página WPF. En las secciones restantes se explican los detalles de cada paso.  
  
 El procedimiento de hospedaje básico es el siguiente:  
  
1. Implemente una página WPFWPF para hospedar la ventana. Una técnica consiste <xref:System.Windows.Controls.Border> en crear un elemento para reservar una sección de la página para la ventana hospedada.  
  
2. Implemente una clase para hospedar el <xref:System.Windows.Interop.HwndHost>control que hereda de .  
  
3. En esa clase, reemplace el <xref:System.Windows.Interop.HwndHost> miembro <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>de clase .  
  
4. Cree la ventana hospedada como un elemento secundario de la ventana que contiene el WPFWPF página. Aunque la programación convencional de WPFWPF no necesita hacer uso explícitamente de ella, la página de hospedaje es una ventana con un identificador (HWND). Recibirá la página HWND `hwndParent` a <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> través del parámetro del método. La ventana hospedada debe crearse como un elemento secundario del HWND.  
  
5. Una vez que haya creado la ventana host, devuelva el HWND de la ventana hospedada. Si desea hospedar uno o varios controles Win32, normalmente cree una ventana host como elemento secundario de HWND y realice los elementos secundarios de los controles de esa ventana host. Ajustar los controles en una ventana host proporciona una manera sencilla para que la página WPFWPF reciba notificaciones de los controles, que se ocupa de algunos problemas particulares de Win32 con notificaciones a través del límite hwnd.  
  
6. Controle los mensajes seleccionados que se envían a la ventana host, como las notificaciones de los controles secundarios. Existen dos formas de hacerlo.  
  
    - Si prefiere controlar los mensajes de la <xref:System.Windows.Interop.HwndHost.WndProc%2A> clase <xref:System.Windows.Interop.HwndHost> de hospedaje, invalide el método de la clase.  
  
    - Si prefiere que WPFWPF controle los <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.MessageHook> mensajes, controle el evento de clase en el código subyacente. Este evento se produce para cada mensaje recibido por la ventana hospedada. Si elige esta opción, debe <xref:System.Windows.Interop.HwndHost.WndProc%2A>invalidar , pero solo necesita una implementación mínima.  
  
7. Invalide <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> <xref:System.Windows.Interop.HwndHost.WndProc%2A> los <xref:System.Windows.Interop.HwndHost>métodos y de . Debe invalidar estos métodos <xref:System.Windows.Interop.HwndHost> para satisfacer el contrato, pero es posible que solo necesite proporcionar una implementación mínima.  
  
8. En el archivo de código subyacente, cree una instancia de la <xref:System.Windows.Controls.Border> clase de hospedaje de control y conviézquela en un elemento secundario del elemento que está pensado para hospedar la ventana.  
  
9. Comunicarse con la ventana hospedada enviándole mensajes de Microsoft Windows y controlando los mensajes desde sus ventanas secundarias, como las notificaciones enviadas por los controles.  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>Implementar el diseño de página  
 El diseño de la página WPFWPF que hospeda el control ListBox consta de dos regiones. El lado izquierdo de la página hospeda [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] varios WPFWPF controles que proporcionan un que le permite manipular el control Win32. La esquina superior derecha de la página tiene una región cuadrada para el control ListBox.  
  
 El código para implementar este diseño es bastante simple. El elemento raíz <xref:System.Windows.Controls.DockPanel> es un que tiene dos elementos secundarios. El primero <xref:System.Windows.Controls.Border> es un elemento que hospeda el control ListBox. Ocupa un cuadrado de 200x200 en la esquina superior derecha de la página. El segundo <xref:System.Windows.Controls.StackPanel> es un elemento que contiene un conjunto de WPFWPF controles que muestran información y permiten manipular el ListBox Control estableciendo las propiedades de interoperación expuestas. Para cada uno de los <xref:System.Windows.Controls.StackPanel>elementos que son hijos de la , ver el material de referencia para los diversos elementos utilizados para los detalles sobre lo que son estos elementos o lo que hacen, estos se enumeran en el código de ejemplo a continuación, pero no se explicarán aquí (el modelo de interoperación básica no requiere ninguno de ellos, se proporcionan para agregar cierta interactividad a la muestra).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementar una clase para hospedar el control de Microsoft Win32  
 El núcleo de este ejemplo es la clase que realmente hospeda el control, ControlHost.cs. Hereda de <xref:System.Windows.Interop.HwndHost>. El constructor toma dos parámetros, height y width, <xref:System.Windows.Controls.Border> que corresponden al alto y ancho del elemento que hospeda el ListBox control. Estos valores se usan más adelante para asegurarse de que el tamaño del control coincide con el <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Hay también un conjunto de constantes. Estas constantes se toman en gran medida de Winuser.h, y le permiten utilizar nombres convencionales al llamar a funciones Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Invalidar BuildWindowCore para crear la ventana de Microsoft Win32  
 Invalide este método para crear la ventana Win32 que hospedará la página y realice la conexión entre la ventana y la página. Dado que este ejemplo implica hospedar un control ListBox, se crean dos ventanas. La primera es la ventana que realmente hospeda la página WPFWPF. El control ListBox se crea como un elemento secundario de esa ventana.  
  
 El motivo de esto es simplificar el proceso de recepción de notificaciones desde el control. La <xref:System.Windows.Interop.HwndHost> clase le permite procesar los mensajes enviados a la ventana que hospeda. Si hospeda un control Win32 directamente, recibirá los mensajes enviados al bucle de mensajes interno del control. Puede mostrar el control y enviarle mensajes, pero no recibirá las notificaciones que el control envíe a su ventana primaria. Entre otras cosas, esto significa que no hay manera de detectar en qué momento el usuario interactúa con el control. Por eso, debe crear una ventana host y convertir el control en un elemento secundario de esa ventana. Esto le permite procesar los mensajes para la ventana host, incluidas las notificaciones que el control envía a la ventana. Para mayor comodidad, y dado que la ventana host es poco más que un simple contenedor del control, se hará referencia al paquete como un control ListBox.  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>Crear la ventana host y el control ListBox  
 Puede usar PInvoke para crear una ventana host para el control mediante la creación y el registro de una clase de ventana, etc. Aun así, un enfoque mucho más sencillo consiste en crear una ventana con la clase de ventana "estática" predefinida. Esto le proporciona el procedimiento de ventana que necesita para recibir notificaciones del control y requiere una codificación mínima.  
  
 El HWND del control se expone a través de una propiedad de solo lectura, de modo que la página host pueda usarla para enviar mensajes al control.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 El control ListBox se crea como un elemento secundario de la ventana host. El alto y el ancho de ambas ventanas se establecen en los valores pasados al constructor, como se ha descrito anteriormente. Esto garantiza que el tamaño de la ventana host y del control sea idéntico al área reservada en la página.  Después de crear las ventanas, el ejemplo devuelve un <xref:System.Runtime.InteropServices.HandleRef> objeto que contiene el HWND de la ventana host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>Implementar DestroyWindow y WndProc  
 Además <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>de , también <xref:System.Windows.Interop.HwndHost.WndProc%2A> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> debe invalidar <xref:System.Windows.Interop.HwndHost>los métodos y métodos del archivo . En este ejemplo, el <xref:System.Windows.Interop.HwndHost.MessageHook> controlador controla los mensajes del <xref:System.Windows.Interop.HwndHost.WndProc%2A> control, por lo que la implementación de y <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> es mínima. En el <xref:System.Windows.Interop.HwndHost.WndProc%2A>caso `handled` de `false` , se establece para indicar que el mensaje no se ha controlado y devolver 0. Porque <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, simplemente destruya la ventana.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>Hospedar el control en la página  
 Para hospedar el control en la página, primero `ControlHost` debe crear una nueva instancia de la clase. Pase el alto y ancho del elemento`ControlHostElement`border que `ControlHost` contiene el control ( ) al constructor. Esto garantiza que el control ListBox tenga el tamaño correcto. A continuación, hospeda el control `ControlHost` en la <xref:System.Windows.Controls.Decorator.Child%2A> página asignando el objeto a la propiedad del host. <xref:System.Windows.Controls.Border>  
  
 El ejemplo adjunta un <xref:System.Windows.Interop.HwndHost.MessageHook> controlador al `ControlHost` evento del que se va a recibir mensajes del control. Este evento se genera para cada mensaje enviado a la ventana hospedada. En este caso, estos son los mensajes enviados a la ventana que contiene el control ListBox real, incluidas las notificaciones del control. En el ejemplo se llama a SendMessage para obtener información del control y modificar su contenido. En la siguiente sección se describe en detalle la manera en que la página se comunica con el control.  
  
> [!NOTE]
> Tenga en cuenta que hay dos PInvoke declaraciones para SendMessage. Esto es necesario porque `wParam` uno utiliza el parámetro para pasar una cadena y el otro lo utiliza para pasar un entero. Necesita una declaración distinta para cada firma para asegurarse de que los datos se serializan correctamente.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementar la comunicación entre el control y la página  
 Manipular el control mediante el envío de mensajes de Windows. El control le notifica en qué momento el usuario interactúa con él mediante el envío de notificaciones a la ventana host. El [hosting a Win32 ListBox Control en WPFWPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) ejemplo incluye una interfaz de usuario que proporciona varios ejemplos de cómo funciona esto:  
  
- Anexar un elemento a la lista  
  
- Eliminar el elemento seleccionado de la lista  
  
- Mostrar el texto del elemento actualmente seleccionado  
  
- Mostrar el número de elementos de la lista  
  
 El usuario también puede seleccionar un elemento en el cuadro de lista haciendo clic en él, tal como lo haría para una aplicación Win32 convencional. Los datos mostrados se actualizan cada vez que el usuario cambia el estado del cuadro de lista al seleccionar, agregar o anexar un elemento.  
  
 Para anexar elementos, envíe un [ `LB_ADDSTRING` mensaje](/windows/desktop/Controls/lb-addstring)al cuadro de lista. Para eliminar elementos, envíe [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) para obtener el [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) índice de la selección actual y, a continuación, para eliminar el elemento. El ejemplo [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)también envía y usa el valor devuelto para actualizar la presentación que muestra el número de elementos. Ambas instancias [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) de uso una de las declaraciones PInvoke descritas en la sección anterior.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Cuando el usuario selecciona un elemento o cambia su selección, el control notifica a <xref:System.Windows.Interop.HwndHost.MessageHook> la ventana host enviándole un [ `WM_COMMAND` mensaje,](/windows/desktop/menurc/wm-command)lo que provoca el evento de la página. El controlador recibe la misma información que el procedimiento de ventana principal de la ventana host. También pasa una referencia a un `handled`valor booleano, . Se `handled` establece `true` para indicar que ha manejado el mensaje y no es necesario ningún procesamiento adicional.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)se envía por una variedad de razones, por lo que debe examinar el identificador de notificación para determinar si es un evento que desea controlar. El ID está contenido en la `wParam` palabra alta del parámetro. El ejemplo utiliza operadores bit a bit para extraer el identificador. Si el usuario ha realizado o cambiado [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)su selección, el ID será .  
  
 Cuando [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) se recibe, el ejemplo obtiene el índice del [ `LB_GETCURSEL` ](/windows/desktop/Controls/lb-getcursel)elemento seleccionado enviando un mensaje al control. Para obtener el texto, <xref:System.Text.StringBuilder>primero debe crear un archivo . A continuación, envíe [ `LB_GETTEXT` ](/windows/desktop/Controls/lb-gettext)al control un mensaje . Pase el <xref:System.Text.StringBuilder> objeto `wParam` vacío como parámetro. Cuando [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) se <xref:System.Text.StringBuilder> devuelve, el contendrá el texto del elemento seleccionado. Este uso [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) de requiere otra declaración PInvoke.  
  
 Por último, establézalo `handled` para `true` indicar que se ha controlado el mensaje.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Interop.HwndHost>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
