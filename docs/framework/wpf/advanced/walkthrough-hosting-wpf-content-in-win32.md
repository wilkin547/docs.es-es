---
title: 'Tutorial: Hospedar contenido de WPF en Win32'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 4ac1690e7b11d908af9354e9d72097ab7db7fc61
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740253"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Tutorial: Hospedar contenido de WPF en Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en código Win32, podría ser más eficaz agregar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funcionalidad a la aplicación en lugar de volver a escribir el código original. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo sencillo para hospedar contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de Win32.  
  
 En este tutorial se describe cómo escribir una aplicación de ejemplo, [hospedar contenido de WPF en un ejemplo de ventana de Win32](https://go.microsoft.com/fwlink/?LinkID=160004), que hospeda [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una ventana de Win32. Puede extender este ejemplo para hospedar cualquier ventana de Win32. Dado que implica combinar código administrado y no administrado, la aplicación se escribe en C++/CLI.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos de  
 En este tutorial se da por supuesto que está familiarizado con la programación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Win32. Para obtener una introducción básica a la programación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Introducción](../getting-started/index.md). Para obtener una introducción a la programación de Win32, debe hacer referencia a cualquiera de los numerosos libros del asunto, en determinadas *ventanas de programación* , de Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tutorial se implementa C++en/CLI, en este tutorial se da por supuesto que C++ está familiarizado con el uso de para programar la API de Windows y comprender la programación de código administrado. La familiaridad C++con/CLI es útil, pero no esencial.  
  
> [!NOTE]
> En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para obtener el código de ejemplo completo, vea [ejemplo de hospedaje de contenido de WPF en una ventana de Win32](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico que se usa para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una ventana de Win32. Las secciones restantes explican los detalles de cada paso.  
  
 La clave para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una ventana de Win32 es la clase <xref:System.Windows.Interop.HwndSource>. Esta clase ajusta el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una ventana de Win32, lo que permite que se incorpore en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria. El siguiente enfoque combina el Win32 y el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una sola aplicación.  
  
1. Implemente el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como una clase administrada.  
  
2. Implementar una aplicación de Windows C++con/CLI. Si está empezando con una aplicación existente y C++ código no administrado, normalmente puede habilitarlo para llamar a código administrado cambiando la configuración del proyecto para incluir la marca de compilador `/clr`.  
  
3. Establezca el modelo de subprocesos en contenedor uniproceso (STA).  
  
4. Controle la notificación de [WM_CREATE](/windows/desktop/winmsg/wm-create)en el procedimiento de ventana y haga lo siguiente:  
  
    1. Cree un nuevo objeto <xref:System.Windows.Interop.HwndSource> con la ventana primaria como su `parent` parámetro.  
  
    2. Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Asigne una referencia al objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> de la <xref:System.Windows.Interop.HwndSource>.  
  
    4. Obtenga el HWND para el contenido. La propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> del objeto <xref:System.Windows.Interop.HwndSource> contiene el identificador de ventana (HWND). Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.  
  
5. Implemente una clase administrada que contenga un campo estático para contener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esta clase le permite obtener una referencia al contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde el código de Win32.  
  
6. Asigne el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al campo estático.  
  
7. Reciba notificaciones del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] adjuntando un controlador a uno o varios de los eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8. Comuníquese con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, etc.  
  
> [!NOTE]
> También puede usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para implementar el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Sin embargo, tendrá que compilarlo por separado como una biblioteca de vínculos dinámicos (DLL) y hacer referencia a ese archivo DLL desde la aplicación Win32. El resto del procedimiento es similar al descrito anteriormente.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host
 En esta sección se describe cómo hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una aplicación básica de Win32. El propio contenido se implementa en C++/CLI como una clase administrada. En su mayor parte, se trata de programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sencilla. Los aspectos clave de la implementación del contenido se tratan en [implementación del contenido de WPF](#implementing_the_wpf_page).

- [Aplicación básica](#the_basic_application)

- [Hospedaje de contenido WPF](#hosting_the_wpf_page)

- [Referencia al contenido WPF](#holding_a_reference)

- [Comunicación con el contenido WPF](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Aplicación básica
 El punto de partida para la aplicación host fue crear una plantilla de Visual Studio 2005.

1. Abra Visual Studio 2005 y seleccione **nuevo proyecto** en el menú **archivo** .

2. Seleccione **Win32** en la lista de tipos C++ de proyecto visual. Si el idioma predeterminado no C++es, encontrará estos tipos de proyecto en **otros lenguajes**.

3. Seleccione una plantilla de **proyecto de Win32** , asigne un nombre al proyecto y haga clic en **Aceptar** para iniciar el **Asistente para aplicaciones Win32**.

4. Acepte la configuración predeterminada del asistente y haga clic en **Finalizar** para iniciar el proyecto.

 La plantilla crea una aplicación básica de Win32, que incluye:

- Un punto de entrada para la aplicación.

- Una ventana con un procedimiento de ventana asociado (WndProc).

- Un menú con los encabezados **archivo** y **ayuda** . El menú **archivo** tiene un elemento **salir** que cierra la aplicación. El menú **ayuda** tiene un elemento **acerca de** que inicia un cuadro de diálogo simple.

 Antes de empezar a escribir código para hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido, debe realizar dos modificaciones en la plantilla básica.

 La primera consiste en compilar el proyecto como código administrado. De forma predeterminada, el proyecto se compila como código no administrado. Sin embargo, dado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en código administrado, el proyecto debe estar compilado consecuentemente.

1. Haga clic con el botón secundario en el nombre del proyecto en **Explorador de soluciones** y seleccione **propiedades** en el menú contextual para abrir el cuadro de diálogo **páginas de propiedades** .

2. Seleccione **propiedades de configuración** en la vista de árbol del panel izquierdo.

3. Seleccione compatible con **Common Language Runtime** en la lista **valores predeterminados del proyecto** del panel derecho.

4. Seleccione **compatible con Common Language Runtime (/CLR)** en el cuadro de lista desplegable.

> [!NOTE]
> Esta marca de compilador permite usar código administrado en la aplicación, pero el código no administrado seguirá compilándose como antes.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa el modelo de subprocesos de contenedor uniproceso (STA). Para que funcione correctamente con el código de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe establecer el modelo de subprocesos de la aplicación en STA aplicando un atributo al punto de entrada.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hospedaje de contenido WPF
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido es una aplicación de entrada de dirección simple. Consta de varios controles <xref:System.Windows.Controls.TextBox> para tomar el nombre de usuario, la dirección, etc. También hay dos controles <xref:System.Windows.Controls.Button>, **Aceptar** y **Cancelar**. Cuando el usuario hace clic en **Aceptar**, el controlador de eventos del <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón recopila los datos de los controles de <xref:System.Windows.Controls.TextBox>, los asigna a las propiedades correspondientes y genera un evento personalizado, `OnButtonClicked`. Cuando el usuario hace clic en **Cancelar**, el controlador simplemente genera `OnButtonClicked`. El objeto de argumento de evento para `OnButtonClicked` contiene un campo booleano que indica en qué botón se hizo clic.

 El código para hospedar el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en un controlador para la notificación de [WM_CREATE](/windows/desktop/winmsg/wm-create) en la ventana host.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 El método `GetHwnd` toma la información de tamaño y posición más el identificador de la ventana primaria y devuelve el identificador de ventana del contenido del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado.

> [!NOTE]
> No se puede usar una directiva `#using` para el espacio de nombres `System::Windows::Interop`. Si lo hace, crearía un conflicto de nombres entre la estructura <xref:System.Windows.Interop.MSG> en ese espacio de nombres y la estructura MSG declarada en winuser.h. En su lugar, debe usar nombres completos para tener acceso al contenido de ese espacio de nombres.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 No se puede hospedar el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] directamente en la ventana de la aplicación. En su lugar, cree un objeto <xref:System.Windows.Interop.HwndSource> para encapsular el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Este objeto es básicamente una ventana diseñada para hospedar un contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para hospedar el objeto de <xref:System.Windows.Interop.HwndSource> en la ventana primaria, debe crearlo como un elemento secundario de una ventana de Win32 que forme parte de la aplicación. Los parámetros del constructor <xref:System.Windows.Interop.HwndSource> contienen prácticamente la misma información que se pasaría a CreateWindow al crear una ventana secundaria de Win32.

 A continuación, cree una instancia del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En este caso, el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa como una clase independiente, `WPFPage`, C++mediante/CLI. También puede implementar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Sin embargo, para ello deberá configurar un proyecto independiente y compilar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido como un archivo DLL. Puede Agregar una referencia a ese archivo DLL al proyecto y usar esa referencia para crear una instancia del contenido del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Para mostrar el contenido de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en la ventana secundaria, asigne una referencia al contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del <xref:System.Windows.Interop.HwndSource>.

 La siguiente línea de código adjunta un controlador de eventos, `WPFButtonClicked`, al evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del contenido `OnButtonClicked`. Se llama a este controlador cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** . Consulte [communicating_with_the_WPF contenido](#communicating_with_the_page) para obtener más información sobre este controlador de eventos.

 La línea final del código mostrado devuelve el identificador de ventana (HWND) que está asociado al objeto <xref:System.Windows.Interop.HwndSource>. Puede usar este identificador desde el código de Win32 para enviar mensajes a la ventana hospedada, aunque el ejemplo no lo hace. El objeto <xref:System.Windows.Interop.HwndSource> genera un evento cada vez que recibe un mensaje. Para procesar los mensajes, llame al método <xref:System.Windows.Interop.HwndSource.AddHook%2A> para adjuntar un controlador de mensajes y, a continuación, procese los mensajes en ese controlador.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Referencia al contenido WPF
 En muchas aplicaciones, deseará comunicarse con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] más adelante. Por ejemplo, quizá desee modificar las propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o quizás quiera que el objeto <xref:System.Windows.Interop.HwndSource> hospede contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diferente. Para ello, necesita una referencia al objeto <xref:System.Windows.Interop.HwndSource> o al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El objeto <xref:System.Windows.Interop.HwndSource> y su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado permanecen en memoria hasta que se destruya el identificador de ventana. Sin embargo, la variable que asigne al objeto <xref:System.Windows.Interop.HwndSource> saldrá del ámbito tan pronto se devuelva un resultado desde el procedimiento de ventana. La forma más personalizada de tratar este problema con aplicaciones Win32 es usar una variable global o estática. Por desgracia, no es posible asignar un objeto administrado a esos tipos de variables. Puede asignar el identificador de ventana asociado al objeto <xref:System.Windows.Interop.HwndSource> a una variable global o estática, pero eso no proporciona acceso al objeto mismo.

 La solución más sencilla para este problema es implementar una clase administrada con un conjunto de campos estáticos que contengan referencias a los objetos administrados a los que es necesario tener acceso. En el ejemplo se usa la clase `WPFPageHost` para incluir una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], además de los valores iniciales de una serie de sus propiedades que el usuario puede cambiar posteriormente. Esto se define en el encabezado.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 La última parte de la función `GetHwnd` asigna valores a esos campos para su uso posterior mientras `myPage` está todavía en el ámbito.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Comunicación con el contenido WPF
 Hay dos tipos de comunicación con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La aplicación recibe información del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando el usuario hace clic en los botones **Aceptar** o **Cancelar** . La aplicación también tiene una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que permite al usuario cambiar diversas propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como el tamaño de fuente predeterminado o el color de fondo.

 Como se mencionó anteriormente, cuando el usuario hace clic en cualquiera de los botones, el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genera un evento `OnButtonClicked`. La aplicación adjunta un controlador a este evento para recibir estas notificaciones. Si se hizo clic en el botón **Aceptar** , el controlador obtiene la información de usuario del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido y la muestra en un conjunto de controles estáticos.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 El controlador recibe un objeto de argumento de evento personalizado del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], `MyPageEventArgs`. La propiedad `IsOK` del objeto se establece en `true` si se hizo clic en el botón **Aceptar** y `false` si se hizo clic en el botón **Cancelar** .

 Si se hizo clic en el botón **Aceptar** , el controlador obtiene una referencia al contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la clase contenedora. A continuación, recopila la información del usuario incluida en las propiedades de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado y usa los controles estáticos para mostrar la información en la ventana primaria. Dado que los datos de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen el formato de una cadena administrada, se deben calcular las referencias para que los use un control Win32. Si se hizo clic en el botón **Cancelar** , el controlador borra los datos de los controles estáticos.

 La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación proporciona un conjunto de botones de radio que permiten al usuario modificar el color de fondo del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y varias propiedades relacionadas con la fuente. El ejemplo siguiente es un extracto del procedimiento de ventana de la aplicación (WndProc) y su control de mensajes que establece varias propiedades en diferentes mensajes, incluido el color de fondo. Los demás son similares y no se muestran. Vea el ejemplo completo para obtener detalles y el contexto.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Para establecer el color de fondo, obtenga una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) de `WPFPageHost` y establezca la propiedad de color de fondo en el color apropiado. En el ejemplo se usan tres opciones de color: el color original, verde claro y salmón claro. El color de fondo original se almacena como un campo estático en la clase `WPFPageHost`. Para establecer los otros dos, se crea un nuevo objeto <xref:System.Windows.Media.SolidColorBrush> y se pasa al constructor un valor de colores estático desde el objeto <xref:System.Windows.Media.Colors>.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementación de la página WPF
 Puede hospedar y usar el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin ningún conocimiento de la implementación real. Si el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se hubiera empaquetado en un archivo DLL independiente, podría haberse compilado en cualquier lenguaje de Common Language Runtime (CLR). A continuación se muestra un breve tutorial C++de la implementación de/CLI que se usa en el ejemplo. Esta sección contiene las subsecciones siguientes.

- [Diseño](#page_layout)

- [Devolución de datos a la ventana host](#returning_data_to_window)

- [Establecimiento de propiedades WPF](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Presentación
 Los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del contenido del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] constan de cinco controles de <xref:System.Windows.Controls.TextBox>, con controles de <xref:System.Windows.Controls.Label> asociados: nombre, dirección, ciudad, estado y código postal. También hay dos controles <xref:System.Windows.Controls.Button>, **Aceptar** y **Cancelar** .

 El contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en la clase `WPFPage`. El diseño se controla con un elemento de diseño <xref:System.Windows.Controls.Grid>. La clase hereda de <xref:System.Windows.Controls.Grid>, lo que lo convierte en el elemento raíz del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 El constructor de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] toma el ancho y el alto necesarios y ajusta el tamaño del <xref:System.Windows.Controls.Grid> en consecuencia. A continuación, define el diseño básico mediante la creación de un conjunto de objetos <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> y su adición a las colecciones base <xref:System.Windows.Controls.Grid> objeto <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> y <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, respectivamente. Esto define una cuadrícula de cinco filas y siete columnas, con las dimensiones determinadas por el contenido de las celdas.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 A continuación, el constructor agrega los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a <xref:System.Windows.Controls.Grid>. El primer elemento es el texto del título, que es un control <xref:System.Windows.Controls.Label> que se centra en la primera fila de la cuadrícula.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 La siguiente fila contiene el control <xref:System.Windows.Controls.Label> de nombre y su control <xref:System.Windows.Controls.TextBox> asociado. Dado que se usa el mismo código para cada par de etiqueta/cuadro de texto, está colocado en un par de métodos privados y se usa para los cinco pares de etiqueta/cuadro de texto. Los métodos crean el control apropiado y llaman a los métodos estáticos <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Grid.SetColumn%2A> de la clase <xref:System.Windows.Controls.Grid.SetRow%2A> para colocar los controles en la celda correspondiente. Una vez creado el control, el ejemplo llama al método <xref:System.Windows.Controls.UIElementCollection.Add%2A> en la propiedad <xref:System.Windows.Controls.Panel.Children%2A> de <xref:System.Windows.Controls.Grid> para agregar el control a la cuadrícula. El código para agregar los pares restantes de etiqueta/cuadro de texto es similar. Vea el código de ejemplo para obtener más detalles.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 La implementación de los dos métodos es la siguiente:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Por último, el ejemplo agrega los botones **Aceptar** y **Cancelar** y asocia un controlador de eventos a sus <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Devolución de datos a la ventana host
 Cuando se hace clic en cualquiera de los botones, se genera su evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. La ventana host simplemente podría asociar controladores a estos eventos y obtener los datos directamente desde los controles <xref:System.Windows.Controls.TextBox>. En el ejemplo se usa un enfoque algo menos directo. Controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dentro del contenido del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, a continuación, genera un `OnButtonClicked`de eventos personalizado, para notificar el contenido del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esto permite que el contenido de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] realice alguna validación de parámetros antes de notificar al host. El controlador obtiene el texto de los controles <xref:System.Windows.Controls.TextBox> y lo asigna a propiedades públicas, desde las que el host puede recuperar la información.

 La declaración de evento, en WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, en WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Establecimiento de propiedades WPF
 El host de Win32 permite al usuario cambiar varias propiedades de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Desde el lado de Win32, es simplemente cuestión de cambiar las propiedades. La implementación en la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un poco más complicada, porque no hay ninguna propiedad global única que controle las fuentes de todos los controles. En su lugar, se cambia la propiedad adecuada para cada control en los descriptores del conjunto de propiedades. En el ejemplo siguiente se muestra el código de la propiedad `DefaultFontFamily`. Al establecer la propiedad, se llama a un método privado que a su vez establece las propiedades <xref:System.Windows.Controls.Control.FontFamily%2A> de los diversos controles.

 Desde WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Desde WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
