---
title: 'Tutorial: Hospedar contenido de WPF en Win32'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 3a0a6d09fe34fed9f5b0d353252461fdffbeb5e1
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484616"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Tutorial: Hospedar contenido de WPF en Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si se tiene una inversión sustancial en código [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], quizá sea más eficaz agregar funcionalidad de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación en lugar de reescribir el código original. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona un mecanismo sencillo para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.  
  
 En este tutorial se describe cómo escribir una aplicación de ejemplo, [hospedar contenido de WPF en un ejemplo de ventana de Win32](https://go.microsoft.com/fwlink/?LinkID=160004), que hospeda [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana de. Puede extender este ejemplo para hospedar cualquier ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Dado que implica combinar código administrado y no administrado, la aplicación se escribe en C++/CLI.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 En este tutorial se da por supuesto un conocimiento básico de la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Para obtener una introducción básica [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la programación, vea [Introducción](../getting-started/index.md). Para obtener una introducción [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] a la programación, debe hacer referencia a cualquiera de los numerosos libros del asunto, en determinadas *ventanas de programación* , de Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tutorial se implementa C++en/CLI, en este tutorial se da por supuesto que C++ está familiarizado con el uso de para programar la API de Windows y comprender la programación de código administrado. La familiaridad C++con/CLI es útil, pero no esencial.  
  
> [!NOTE]
>  En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para obtener el código de ejemplo completo, vea [ejemplo de hospedaje de contenido de WPF en una ventana de Win32](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico que se usa para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedar contenido [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en una ventana de. Las secciones restantes explican los detalles de cada paso.  
  
 La clave para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana es <xref:System.Windows.Interop.HwndSource> la clase. Esta clase ajusta el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido de una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, lo que permite que se incorpore a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] su como una ventana secundaria. El siguiente enfoque combina [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una única aplicación.  
  
1. Implemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] su contenido como una clase administrada.  
  
2. Implementar una aplicación de Windows C++con/CLI. Si está empezando con una aplicación existente y C++ código no administrado, normalmente puede habilitarlo para llamar a código administrado cambiando la configuración del proyecto para incluir la `/clr` marca del compilador.  
  
3. Establezca el modelo de subprocesos en contenedor uniproceso (STA).  
  
4. Controle la notificación [WM_CREATE](/windows/desktop/winmsg/wm-create)en el procedimiento de ventana y haga lo siguiente:  
  
    1. Cree un nuevo objeto <xref:System.Windows.Interop.HwndSource> con la ventana primaria como su `parent` parámetro.  
  
    2. Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Asigne una referencia al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido a la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de. <xref:System.Windows.Interop.HwndSource>  
  
    4. Obtenga el HWND para el contenido. La propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> del objeto <xref:System.Windows.Interop.HwndSource> contiene el identificador de ventana (HWND). Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.  
  
5. Implemente una clase administrada que contenga un campo estático para contener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esta clase le permite obtener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde su código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
6. Asigne el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al campo estático.  
  
7. Reciba notificaciones del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido adjuntando un controlador a uno o varios de los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos.  
  
8. Comuníquese con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, etc.  
  
> [!NOTE]
>  También puede usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para implementar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Sin embargo, tendrá que compilarlo por separado como una [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] y hacer referencia a esta [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] desde su aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. El resto del procedimiento es similar al descrito anteriormente.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host
 En esta sección se describe cómo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedar contenido en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] una aplicación básica. El propio contenido se implementa en C++/CLI como una clase administrada. En su mayor parte, se trata de programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sencilla. Los aspectos clave de la implementación del contenido se tratan en [implementación del contenido de WPF](#implementing_the_wpf_page).

<a name="autoNestedSectionsOUTLINE1"></a>
- [Aplicación básica](#the_basic_application)

- [Hospedaje de contenido WPF](#hosting_the_wpf_page)

- [Referencia al contenido WPF](#holding_a_reference)

- [Comunicación con el contenido WPF](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Aplicación básica
 El punto de partida para la aplicación host fue crear una plantilla de Visual Studio 2005.

1. Abra Visual Studio 2005 y seleccione **nuevo proyecto** en el menú **archivo** .

2. Seleccione **Win32** en la lista de [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)] tipos de proyecto. Si el idioma predeterminado no C++es, encontrará estos tipos de proyecto en **otros lenguajes**.

3. Seleccione una plantilla de **proyecto de Win32** , asigne un nombre al proyecto y haga clic en **Aceptar** para iniciar el **Asistente para aplicaciones Win32**.

4. Acepte la configuración predeterminada del asistente y haga clic en **Finalizar** para iniciar el proyecto.

 La plantilla crea una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] básica, que incluye:

- Un punto de entrada para la aplicación.

- Una ventana con un procedimiento de ventana asociado (WndProc).

- Un menú con los encabezados **archivo** y **ayuda** . El menú **archivo** tiene un elemento **salir** que cierra la aplicación. El menú **ayuda** tiene un elemento **acerca de** que inicia un cuadro de diálogo simple.

 Antes de empezar a escribir código para hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido, debe realizar dos modificaciones en la plantilla básica.

 La primera consiste en compilar el proyecto como código administrado. De forma predeterminada, el proyecto se compila como código no administrado. Sin embargo, dado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en código administrado, el proyecto debe estar compilado consecuentemente.

1. Haga clic con el botón secundario en el nombre del proyecto en **Explorador de soluciones** y seleccione **propiedades** en el menú contextual para abrir el cuadro de diálogo **páginas de propiedades** .

2. Seleccione **propiedades de configuración** en la vista de árbol del panel izquierdo.

3. Seleccione compatible con **Common Language Runtime** en la lista valores predeterminados del **proyecto** del panel derecho.

4. Seleccione **compatible con Common Language Runtime (/CLR)** en el cuadro de lista desplegable.

> [!NOTE]
>  Esta marca de compilador permite usar código administrado en la aplicación, pero el código no administrado seguirá compilándose como antes.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa el modelo de subprocesos de contenedor uniproceso (STA). Para que funcione correctamente con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] código de contenido, debe establecer el modelo de subprocesos de la aplicación en Sta aplicando un atributo al punto de entrada.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hospedaje de contenido WPF
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido es una aplicación de entrada de dirección simple. Consta de varios controles <xref:System.Windows.Controls.TextBox> para tomar el nombre de usuario, la dirección, etc. También hay dos <xref:System.Windows.Controls.Button> controles, **Aceptar** y **Cancelar**. Cuando el usuario hace clic en **Aceptar**, el controlador <xref:System.Windows.Controls.Primitives.ButtonBase.Click> de eventos del botón recopila los datos de <xref:System.Windows.Controls.TextBox> los controles, los asigna a las propiedades correspondientes y genera un evento personalizado,. `OnButtonClicked` Cuando el usuario hace clic en **Cancelar**, el controlador simplemente `OnButtonClicked`genera. El objeto de argumento de evento para `OnButtonClicked` contiene un campo booleano que indica en qué botón se hizo clic.

 El código para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el contenido se implementa en un controlador para la notificación [WM_CREATE](/windows/desktop/winmsg/wm-create) en la ventana host.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 El `GetHwnd` método toma la información de tamaño y posición más el identificador de la ventana primaria y devuelve el identificador [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de ventana del contenido hospedado.

> [!NOTE]
>  No se puede usar una directiva `#using` para el espacio de nombres `System::Windows::Interop`. Si lo hace, crearía un conflicto de nombres entre la estructura <xref:System.Windows.Interop.MSG> en ese espacio de nombres y la estructura MSG declarada en winuser.h. En su lugar, debe usar nombres completos para tener acceso al contenido de ese espacio de nombres.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 No se puede hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido directamente en la ventana de la aplicación. En su lugar, cree un objeto <xref:System.Windows.Interop.HwndSource> para encapsular el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Este objeto es básicamente una ventana diseñada para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Para hospedar <xref:System.Windows.Interop.HwndSource> el objeto en la ventana primaria, debe crearlo como un elemento [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] secundario de una ventana que forme parte de la aplicación. Los parámetros de constructor <xref:System.Windows.Interop.HwndSource> contienen casi la misma información que se pasaría a CreateWindow al crear una ventana secundaria [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].

 A continuación, cree una instancia del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido. En este caso, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido se implementa como una clase independiente, `WPFPage`, mediante C++/CLI. También puede implementar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Sin embargo, para ello deberá configurar un proyecto independiente y compilar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]como. Puede agregar una referencia a esa [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] en su proyecto y usar esa referencia para crear una instancia del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Para mostrar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en la ventana secundaria, asigne una referencia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al contenido a la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de. <xref:System.Windows.Interop.HwndSource>

 La siguiente línea de código adjunta un controlador de eventos, `WPFButtonClicked`, al evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del contenido `OnButtonClicked`. Se llama a este controlador cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** . Vea el [contenido de WPF](#communicating_with_the_page) para obtener más información sobre este controlador de eventos.

 La línea final del código mostrado devuelve el identificador de ventana (HWND) que está asociado al objeto <xref:System.Windows.Interop.HwndSource>. Puede usar este identificador desde su código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para enviar mensajes a la ventana hospedada, aunque el ejemplo no lo hace. El objeto <xref:System.Windows.Interop.HwndSource> genera un evento cada vez que recibe un mensaje. Para procesar los mensajes, llame al método <xref:System.Windows.Interop.HwndSource.AddHook%2A> para adjuntar un controlador de mensajes y, a continuación, procese los mensajes en ese controlador.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Referencia al contenido WPF
 En muchas aplicaciones, deseará comunicarse con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] más adelante. Por ejemplo, quizá desee modificar las propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o quizás quiera que el objeto <xref:System.Windows.Interop.HwndSource> hospede contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diferente. Para ello, necesita una referencia al objeto <xref:System.Windows.Interop.HwndSource> o al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El objeto <xref:System.Windows.Interop.HwndSource> y su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado permanecen en memoria hasta que se destruya el identificador de ventana. Sin embargo, la variable que asigne al objeto <xref:System.Windows.Interop.HwndSource> saldrá del ámbito tan pronto se devuelva un resultado desde el procedimiento de ventana. La forma habitual de afrontar este problema con aplicaciones [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] consiste en usar una variable global o estática. Por desgracia, no es posible asignar un objeto administrado a esos tipos de variables. Puede asignar el identificador de ventana asociado al objeto <xref:System.Windows.Interop.HwndSource> a una variable global o estática, pero eso no proporciona acceso al objeto mismo.

 La solución más sencilla para este problema es implementar una clase administrada con un conjunto de campos estáticos que contengan referencias a los objetos administrados a los que es necesario tener acceso. En el ejemplo se usa la clase `WPFPageHost` para incluir una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], además de los valores iniciales de una serie de sus propiedades que el usuario puede cambiar posteriormente. Esto se define en el encabezado.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 La última parte de la función `GetHwnd` asigna valores a esos campos para su uso posterior mientras `myPage` está todavía en el ámbito.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Comunicación con el contenido WPF
 Hay dos tipos de comunicación con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La aplicación recibe información del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido cuando el usuario hace clic en los botones **Aceptar** o **Cancelar** . La aplicación también tiene una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que permite al usuario cambiar diversas propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como el tamaño de fuente predeterminado o el color de fondo.

 Como se mencionó anteriormente, cuando el usuario hace clic en cualquiera de los botones, el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genera un evento `OnButtonClicked`. La aplicación adjunta un controlador a este evento para recibir estas notificaciones. Si se hizo clic en el botón **Aceptar** , el controlador obtiene la información de usuario [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del contenido y la muestra en un conjunto de controles estáticos.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 El controlador recibe un objeto de argumento de evento personalizado del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], `MyPageEventArgs`. La propiedad del `IsOK` objeto se establece en `true` si se hizo clic en el botón **Aceptar** y `false` si se hizo clic en el botón **Cancelar** .

 Si se hizo clic en el botón **Aceptar** , el controlador obtiene una referencia al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido de la clase contenedora. A continuación, recopila la información del usuario incluida en las propiedades de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado y usa los controles estáticos para mostrar la información en la ventana primaria. Dado que los datos de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] están en forma de cadena administrada, deben serializarse para que pueda usarlos un control [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Si se hizo clic en el botón **Cancelar** , el controlador borra los datos de los controles estáticos.

 La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación proporciona un conjunto de botones de radio que permiten al usuario modificar el color de fondo del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y varias propiedades relacionadas con la fuente. El ejemplo siguiente es un extracto del procedimiento de ventana de la aplicación (WndProc) y su control de mensajes que establece varias propiedades en diferentes mensajes, incluido el color de fondo. Los demás son similares y no se muestran. Vea el ejemplo completo para obtener detalles y el contexto.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Para establecer el color de fondo, obtenga una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) de `WPFPageHost` y establezca la propiedad de color de fondo en el color apropiado. En el ejemplo se usan tres opciones de color: el color original, verde claro y salmón claro. El color de fondo original se almacena como un campo estático en la clase `WPFPageHost`. Para establecer los otros dos, se crea un nuevo objeto <xref:System.Windows.Media.SolidColorBrush> y se pasa al constructor un valor de colores estático desde el objeto <xref:System.Windows.Media.Colors>.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementación de la página WPF
 Puede hospedar y usar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido sin ningún conocimiento de la implementación real. Si el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido se hubiera empaquetado en un independiente [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], podría haberse compilado en cualquier lenguaje de Common Language Runtime (CLR). A continuación se muestra un breve tutorial C++de la implementación de/CLI que se usa en el ejemplo. Esta sección contiene las subsecciones siguientes.

<a name="autoNestedSectionsOUTLINE2"></a>
- [Diseño](#page_layout)

- [Devolución de datos a la ventana host](#returning_data_to_window)

- [Establecimiento de propiedades WPF](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Diseño
 Los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Label> del contenido se componen de cinco controles, con controles asociados: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Nombre, dirección, ciudad, estado y código postal. También hay dos <xref:System.Windows.Controls.Button> controles, **Aceptar** y **Cancelar** .

 El contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en la clase `WPFPage`. El diseño se controla con un elemento de diseño <xref:System.Windows.Controls.Grid>. La clase hereda de <xref:System.Windows.Controls.Grid>, lo que lo convierte en el elemento raíz del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] constructor de contenido toma el ancho y el alto necesarios y ajusta <xref:System.Windows.Controls.Grid> el tamaño del en consecuencia. A continuación, define el diseño básico mediante la creación de <xref:System.Windows.Controls.ColumnDefinition> un <xref:System.Windows.Controls.RowDefinition> conjunto de objetos y y su adición a <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> la <xref:System.Windows.Controls.Grid.RowDefinitions%2A> base de objetos y a las <xref:System.Windows.Controls.Grid> colecciones, respectivamente. Esto define una cuadrícula de cinco filas y siete columnas, con las dimensiones determinadas por el contenido de las celdas.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 A continuación, el constructor agrega los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a <xref:System.Windows.Controls.Grid>. El primer elemento es el texto del título, que es un control <xref:System.Windows.Controls.Label> que se centra en la primera fila de la cuadrícula.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 La siguiente fila contiene el control <xref:System.Windows.Controls.Label> de nombre y su control <xref:System.Windows.Controls.TextBox> asociado. Dado que se usa el mismo código para cada par de etiqueta/cuadro de texto, está colocado en un par de métodos privados y se usa para los cinco pares de etiqueta/cuadro de texto. Los métodos crean el control apropiado y llaman a los métodos estáticos <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Grid.SetColumn%2A> de la clase <xref:System.Windows.Controls.Grid.SetRow%2A> para colocar los controles en la celda correspondiente. Una vez creado el control, el ejemplo llama al método <xref:System.Windows.Controls.UIElementCollection.Add%2A> en la propiedad <xref:System.Windows.Controls.Panel.Children%2A> de <xref:System.Windows.Controls.Grid> para agregar el control a la cuadrícula. El código para agregar los pares restantes de etiqueta/cuadro de texto es similar. Vea el código de ejemplo para obtener más detalles.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 La implementación de los dos métodos es la siguiente:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Finalmente, el ejemplo agrega los botones **Aceptar** y **Cancelar** y asocia un controlador de eventos a sus <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Devolución de datos a la ventana host
 Cuando se hace clic en cualquiera de los botones, se genera su evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. La ventana host simplemente podría asociar controladores a estos eventos y obtener los datos directamente desde los controles <xref:System.Windows.Controls.TextBox>. En el ejemplo se usa un enfoque algo menos directo. Controla la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dentro del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido y, a continuación, genera un evento `OnButtonClicked`personalizado para notificar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el contenido. Esto permite que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el contenido realice alguna validación de parámetros antes de notificar al host. El controlador obtiene el texto de los controles <xref:System.Windows.Controls.TextBox> y lo asigna a propiedades públicas, desde las que el host puede recuperar la información.

 La declaración de evento, en WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, en WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Establecimiento de propiedades WPF
 El [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] host permite al usuario cambiar varias [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades de contenido. Desde el lado [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], se trata simplemente de una cuestión de cambiar las propiedades. La implementación en la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un poco más complicada, porque no hay ninguna propiedad global única que controle las fuentes de todos los controles. En su lugar, se cambia la propiedad adecuada para cada control en los descriptores del conjunto de propiedades. En el ejemplo siguiente se muestra el código `DefaultFontFamily` de la propiedad. Al establecer la propiedad, se llama a un método privado que a su vez establece las propiedades <xref:System.Windows.Controls.Control.FontFamily%2A> de los diversos controles.

 Desde WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Desde WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
