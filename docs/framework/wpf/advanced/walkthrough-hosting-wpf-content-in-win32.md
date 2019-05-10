---
title: 'Tutorial: Hospedar contenido de WPF en Win32'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 01ac0e2cafc704b64634f1fb36145387b49c34a0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650788"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Tutorial: Hospedar contenido de WPF en Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si se tiene una inversión sustancial en código [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], quizá sea más eficaz agregar funcionalidad de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación en lugar de reescribir el código original. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Proporciona un mecanismo sencillo para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana.  
  
 Este tutorial describe cómo escribir una aplicación de ejemplo, [hospedar contenido WPF en un ejemplo de ventana de Win32](https://go.microsoft.com/fwlink/?LinkID=160004), que hosts [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana. Puede extender este ejemplo para hospedar cualquier ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Dado que implica combinar código administrado y no administrado, la aplicación se escribe en [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisitos  
 En este tutorial se da por supuesto un conocimiento básico de la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Para obtener una introducción básica a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] programación, vea [Introducción](../getting-started/index.md). Para obtener una introducción a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de programación, debe hacer referencia a cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows* por Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tutorial se implementa en [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], este tutorial supone que está familiarizado con el uso de [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] al programa la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] y que además conoce la programación de código administrado. Tener un conocimiento de [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] es útil, pero no esencial.  
  
> [!NOTE]
>  En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado. Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo. Para el código de ejemplo completo, vea [hospedar el contenido de WPF en una ventana de Win32 Sample](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedimiento básico  
 En esta sección se describe el procedimiento básico que usa para host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana. Las secciones restantes explican los detalles de cada paso.  
  
 La clave para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana es la <xref:System.Windows.Interop.HwndSource> clase. Esta clase encapsula el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana, lo que le permite incorporarlo en su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria. El siguiente enfoque combina [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una única aplicación.  
  
1. Implemente su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido como una clase administrada.  
  
2. Implemente una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. Si está empezando con una aplicación existente y código [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] no administrado, lo normal es que lo habilite para llamar al código administrado; para ello, cambie la configuración del proyecto para incluir la marca de compilador `/clr`.  
  
3. Establezca el modelo de subprocesos en contenedor uniproceso (STA).  
  
4. Controlar la [WM_CREATE](/windows/desktop/winmsg/wm-create)notificación en el procedimiento de ventana y haga lo siguiente:  
  
    1. Cree un nuevo objeto <xref:System.Windows.Interop.HwndSource> con la ventana primaria como su `parent` parámetro.  
  
    2. Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Asigne una referencia a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido para el <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de la <xref:System.Windows.Interop.HwndSource>.  
  
    4. Obtenga el HWND para el contenido. La propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> del objeto <xref:System.Windows.Interop.HwndSource> contiene el identificador de ventana (HWND). Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.  
  
5. Implemente una clase administrada que contenga un campo estático para contener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esta clase le permite obtener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde su código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
6. Asigne el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al campo estático.  
  
7. Recibir notificaciones desde el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido adjunte un identificador a uno o varios de los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos.  
  
8. Comuníquese con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, etc.  
  
> [!NOTE]
>  También puede usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para implementar su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Sin embargo, tendrá que compilarlo por separado como una [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] y hacer referencia a esta [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] desde su aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. El resto del procedimiento es similar al descrito anteriormente.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host
 Esta sección se describe cómo hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en un basic [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación. El propio contenido se implementa en [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] como una clase administrada. En su mayor parte, se trata de programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sencilla. Se tratan los aspectos clave de la implementación del contenido en [implementación de contenido WPF](#implementing_the_wpf_page).

<a name="autoNestedSectionsOUTLINE1"></a>
- [Aplicación básica](#the_basic_application)

- [Hospedaje de contenido WPF](#hosting_the_wpf_page)

- [Referencia al contenido WPF](#holding_a_reference)

- [Comunicación con el contenido WPF](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Aplicación básica
 El punto de partida para la aplicación host fue crear una plantilla de Visual Studio 2005.

1. Abra Visual Studio 2005 y seleccione **nuevo proyecto** desde el **archivo** menú.

2. Seleccione **Win32** en la lista de [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)] tipos de proyecto. Si el lenguaje predeterminado no es [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)], encontrará estos tipos de proyecto en **otros lenguajes**.

3. Seleccione un **proyecto Win32** plantilla, asigne un nombre al proyecto y haga clic en **Aceptar** para iniciar el **Asistente para aplicaciones Win32**.

4. Acepte la configuración predeterminada del asistente y haga clic en **finalizar** para iniciar el proyecto.

 La plantilla crea una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] básica, que incluye:

- Un punto de entrada para la aplicación.

- Una ventana con un procedimiento de ventana asociado (WndProc).

- Un menú con **archivo** y **ayuda** encabezados. El **archivo** menú tiene un **Exit** elemento que se cierra la aplicación. El **ayuda** menú tiene un **sobre** elemento que se abre un cuadro de diálogo simple.

 Antes de empezar a escribir código para hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido, deberá realizar dos modificaciones en la plantilla básica.

 La primera consiste en compilar el proyecto como código administrado. De forma predeterminada, el proyecto se compila como código no administrado. Sin embargo, dado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en código administrado, el proyecto debe estar compilado consecuentemente.

1. Haga clic en el nombre del proyecto en **el Explorador de soluciones** y seleccione **propiedades** en el menú contextual para iniciar el **páginas de propiedades** cuadro de diálogo.

2. Seleccione **propiedades de configuración** desde la vista de árbol en el panel izquierdo.

3. Seleccione **Common Language Runtime** soporte técnico de la **valores predeterminados del proyecto** lista en el panel derecho.

4. Seleccione **compatible con Common Language Runtime (/ clr)** en el cuadro de lista desplegable.

> [!NOTE]
>  Esta marca de compilador permite usar código administrado en la aplicación, pero el código no administrado seguirá compilándose como antes.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa el modelo de subprocesos de contenedor uniproceso (STA). Para que funcione correctamente con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] código de contenido, debe establecer un modelo de subprocesos de la aplicación en STA, aplique un atributo al punto de entrada.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hospedaje de contenido WPF
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido es una aplicación de entrada de dirección simple. Consta de varios controles <xref:System.Windows.Controls.TextBox> para tomar el nombre de usuario, la dirección, etc. Hay dos <xref:System.Windows.Controls.Button> controles, **Aceptar** y **cancelar**. Cuando el usuario hace clic en **Aceptar**, el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos recopila los datos desde el <xref:System.Windows.Controls.TextBox> controla, lo asigna a las propiedades correspondientes y genera un evento personalizado, `OnButtonClicked`. Cuando el usuario hace clic en **cancelar**, el controlador simplemente genera `OnButtonClicked`. El objeto de argumento de evento para `OnButtonClicked` contiene un campo booleano que indica en qué botón se hizo clic.

 El código para hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido se implementa en un controlador para el [WM_CREATE](/windows/desktop/winmsg/wm-create) notificación en la ventana host.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 El `GetHwnd` método toma la información de tamaño y posición más el elemento primario identificador de ventana y devuelve el identificador de ventana de hospedado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido.

> [!NOTE]
>  No se puede usar una directiva `#using` para el espacio de nombres `System::Windows::Interop`. Si lo hace, crearía un conflicto de nombres entre la estructura <xref:System.Windows.Interop.MSG> en ese espacio de nombres y la estructura MSG declarada en winuser.h. En su lugar, debe usar nombres completos para tener acceso al contenido de ese espacio de nombres.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 No puede hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido directamente en la ventana de la aplicación. En su lugar, cree un objeto <xref:System.Windows.Interop.HwndSource> para encapsular el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Este objeto es básicamente una ventana diseñada para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Hospeda el <xref:System.Windows.Interop.HwndSource> objeto en la ventana primaria debe crearlo como elemento secundario de un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana que forma parte de la aplicación. Los parámetros de constructor <xref:System.Windows.Interop.HwndSource> contienen casi la misma información que se pasaría a CreateWindow al crear una ventana secundaria [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].

 A continuación cree una instancia de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido. En este caso, el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa como una clase independiente, `WPFPage`, mediante [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. También puede implementar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Sin embargo, para ello deberá configurar un proyecto independiente y compilar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido como un [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]. Puede agregar una referencia a esa [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] en su proyecto y usar esa referencia para crear una instancia del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Para mostrar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en la ventana secundaria, asigne una referencia a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido a la <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad de la <xref:System.Windows.Interop.HwndSource>.

 La siguiente línea de código adjunta un controlador de eventos, `WPFButtonClicked`, al evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del contenido `OnButtonClicked`. Este controlador se llama cuando el usuario hace clic en el **Aceptar** o **cancelar** botón. Consulte [comunicación con el contenido](#communicating_with_the_page) para obtener más información sobre este controlador de eventos.

 La línea final del código mostrado devuelve el identificador de ventana (HWND) que está asociado al objeto <xref:System.Windows.Interop.HwndSource>. Puede usar este identificador desde su código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para enviar mensajes a la ventana hospedada, aunque el ejemplo no lo hace. El objeto <xref:System.Windows.Interop.HwndSource> genera un evento cada vez que recibe un mensaje. Para procesar los mensajes, llame al método <xref:System.Windows.Interop.HwndSource.AddHook%2A> para adjuntar un controlador de mensajes y, a continuación, procese los mensajes en ese controlador.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Referencia al contenido WPF
 En muchas aplicaciones, deseará comunicarse con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] más adelante. Por ejemplo, quizá desee modificar las propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o quizás quiera que el objeto <xref:System.Windows.Interop.HwndSource> hospede contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diferente. Para ello, necesita una referencia al objeto <xref:System.Windows.Interop.HwndSource> o al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El objeto <xref:System.Windows.Interop.HwndSource> y su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado permanecen en memoria hasta que se destruya el identificador de ventana. Sin embargo, la variable que asigne al objeto <xref:System.Windows.Interop.HwndSource> saldrá del ámbito tan pronto se devuelva un resultado desde el procedimiento de ventana. La forma habitual de afrontar este problema con aplicaciones [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] consiste en usar una variable global o estática. Por desgracia, no es posible asignar un objeto administrado a esos tipos de variables. Puede asignar el identificador de ventana asociado al objeto <xref:System.Windows.Interop.HwndSource> a una variable global o estática, pero eso no proporciona acceso al objeto mismo.

 La solución más sencilla para este problema es implementar una clase administrada con un conjunto de campos estáticos que contengan referencias a los objetos administrados a los que es necesario tener acceso. En el ejemplo se usa la clase `WPFPageHost` para incluir una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], además de los valores iniciales de una serie de sus propiedades que el usuario puede cambiar posteriormente. Esto se define en el encabezado.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 La última parte de la función `GetHwnd` asigna valores a esos campos para su uso posterior mientras `myPage` está todavía en el ámbito.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Comunicación con el contenido WPF
 Hay dos tipos de comunicación con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La aplicación recibe información de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido cuando el usuario hace clic en el **Aceptar** o **cancelar** botones. La aplicación también tiene una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que permite al usuario cambiar diversas propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como el tamaño de fuente predeterminado o el color de fondo.

 Como se mencionó anteriormente, cuando el usuario hace clic en cualquiera de los botones, el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genera un evento `OnButtonClicked`. La aplicación adjunta un controlador a este evento para recibir estas notificaciones. Si el **Aceptar** botón se hizo clic, el controlador obtiene la información de usuario desde el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de contenido y lo muestra en un conjunto de controles estáticos.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 El controlador recibe un objeto de argumento de evento personalizado del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], `MyPageEventArgs`. El objeto `IsOK` propiedad está establecida en `true` si el **Aceptar** botón se hizo clic, y `false` si el **cancelar** botón se hizo clic.

 Si el **Aceptar** botón se hizo clic, el controlador obtiene una referencia a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido de la clase de contenedor. A continuación, recopila la información del usuario incluida en las propiedades de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado y usa los controles estáticos para mostrar la información en la ventana primaria. Dado que los datos de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] están en forma de cadena administrada, deben serializarse para que pueda usarlos un control [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Si el **cancelar** botón se hizo clic, el controlador borra los datos de los controles estáticos.

 La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación proporciona un conjunto de botones de radio que permiten al usuario modificar el color de fondo del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y varias propiedades relacionadas con la fuente. El ejemplo siguiente es un extracto del procedimiento de ventana de la aplicación (WndProc) y su control de mensajes que establece varias propiedades en diferentes mensajes, incluido el color de fondo. Los demás son similares y no se muestran. Vea el ejemplo completo para obtener detalles y el contexto.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Para establecer el color de fondo, obtenga una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (`hostedPage`) de `WPFPageHost` y establezca la propiedad de color de fondo en el color apropiado. En el ejemplo se usan tres opciones de color: el color original, verde claro y salmón claro. El color de fondo original se almacena como un campo estático en la clase `WPFPageHost`. Para establecer los otros dos, se crea un nuevo objeto <xref:System.Windows.Media.SolidColorBrush> y se pasa al constructor un valor de colores estático desde el objeto <xref:System.Windows.Media.Colors>.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementación de la página WPF
 Puede hospedar y utilizar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido sin ningún conocimiento de la implementación real. Si el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se empaquetó en otro contenido [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], podría haber compilado en cualquier [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] lenguaje. A continuación se incluye una breve explicación de la implementación de [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] que se usa en el ejemplo. Esta sección contiene las subsecciones siguientes.

<a name="autoNestedSectionsOUTLINE2"></a>
- [Diseño](#page_layout)

- [Devolución de datos a la ventana host](#returning_data_to_window)

- [Establecimiento de propiedades WPF](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Diseño
 El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido constan de cinco <xref:System.Windows.Controls.TextBox> controla, con asociados <xref:System.Windows.Controls.Label> controles: Nombre, dirección, ciudad, estado y Zip. Hay dos <xref:System.Windows.Controls.Button> controles, **Aceptar** y **Cancelar**

 El contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en la clase `WPFPage`. El diseño se controla con un elemento de diseño <xref:System.Windows.Controls.Grid>. La clase hereda de <xref:System.Windows.Controls.Grid>, lo que lo convierte en el elemento raíz del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido constructor toma la requiere ancho y alto y tamaños de la <xref:System.Windows.Controls.Grid> en consecuencia. A continuación, define el diseño básico creando un conjunto de <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> objetos y agregarlos a la <xref:System.Windows.Controls.Grid> objeto base <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> y <xref:System.Windows.Controls.Grid.RowDefinitions%2A> colecciones, respectivamente. Esto define una cuadrícula de cinco filas y siete columnas, con las dimensiones determinadas por el contenido de las celdas.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 A continuación, el constructor agrega los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a <xref:System.Windows.Controls.Grid>. El primer elemento es el texto del título, que es un control <xref:System.Windows.Controls.Label> que se centra en la primera fila de la cuadrícula.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 La siguiente fila contiene el control <xref:System.Windows.Controls.Label> de nombre y su control <xref:System.Windows.Controls.TextBox> asociado. Dado que se usa el mismo código para cada par de etiqueta/cuadro de texto, está colocado en un par de métodos privados y se usa para los cinco pares de etiqueta/cuadro de texto. Los métodos crean el control apropiado y llaman a los métodos estáticos <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.Grid.SetColumn%2A> de la clase <xref:System.Windows.Controls.Grid.SetRow%2A> para colocar los controles en la celda correspondiente. Una vez creado el control, el ejemplo llama al método <xref:System.Windows.Controls.UIElementCollection.Add%2A> en la propiedad <xref:System.Windows.Controls.Panel.Children%2A> de <xref:System.Windows.Controls.Grid> para agregar el control a la cuadrícula. El código para agregar los pares restantes de etiqueta/cuadro de texto es similar. Vea el código de ejemplo para obtener más detalles.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 La implementación de los dos métodos es la siguiente:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Por último, el ejemplo agrega el **Aceptar** y **cancelar** botones y adjunta un controlador de eventos para sus <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Devolución de datos a la ventana host
 Cuando se hace clic en cualquiera de los botones, se genera su evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. La ventana host simplemente podría asociar controladores a estos eventos y obtener los datos directamente desde los controles <xref:System.Windows.Controls.TextBox>. En el ejemplo se usa un enfoque algo menos directo. Controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dentro de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de contenido y, a continuación, genera un evento personalizado `OnButtonClicked`para notificar la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Esto permite la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] satisfecho con realizar alguna validación de parámetros antes de notificar al host. El controlador obtiene el texto de los controles <xref:System.Windows.Controls.TextBox> y lo asigna a propiedades públicas, desde las que el host puede recuperar la información.

 La declaración de evento, en WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, en WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Establecimiento de propiedades WPF
 El [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] host permite al usuario cambiar varias [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades de contenido. Desde el lado [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], se trata simplemente de una cuestión de cambiar las propiedades. La implementación en la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un poco más complicada, porque no hay ninguna propiedad global única que controle las fuentes de todos los controles. En su lugar, se cambia la propiedad adecuada para cada control en los descriptores del conjunto de propiedades. El ejemplo siguiente muestra el código para el `DefaultFontFamily` propiedad. Al establecer la propiedad, se llama a un método privado que a su vez establece las propiedades <xref:System.Windows.Controls.Control.FontFamily%2A> de los diversos controles.

 Desde WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Desde WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
