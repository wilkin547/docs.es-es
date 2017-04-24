---
title: "Tutorial: Hospedar contenido de WPF en Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "hospedar contenido de WPF en ventana de Win32"
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Tutorial: Hospedar contenido de WPF en Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones.  Sin embargo, si se tiene una inversión sustancial en código [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], quizá sea más eficaz agregar funcionalidad de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación en lugar de reescribir el código original.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un mecanismo sencillo para hospedar contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 En este tutorial se describe cómo escribir una aplicación de [ejemplo de hospedaje de contenido WPF en una ventana de Win32](http://go.microsoft.com/fwlink/?LinkID=160004), que hospeda contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Puede extender este ejemplo para hospedar cualquier ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Dado que implica combinar código administrado y no administrado, la aplicación se escribe en [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  
  
   
  
<a name="requirements"></a>   
## Requisitos  
 En este tutorial se da por supuesto un conocimiento básico de la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Para una introducción básica a la programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Introducción](../../../../docs/framework/wpf/getting-started/index.md).  Para obtener una introducción a la programación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], consulte cualquiera de los numerosos libros sobre el tema, en particular *Programming Windows*, de Charles Petzold.  
  
 Dado que el ejemplo que acompaña a este tutorial se implementa en [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], el tutorial supone que está familiarizado con el uso de [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] para programar la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], y que además conoce la programación de código administrado.  Tener un conocimiento de [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] es útil, pero no esencial.  
  
> [!NOTE]
>  En el tutorial se incluye una serie de ejemplos de código del ejemplo asociado.  Sin embargo, para una mejor lectura, no se incluye el código de ejemplo completo.  Puede ver el código de ejemplo completo en el [ejemplo de hospedaje de contenido WPF en una ventana de Win32](http://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## Procedimiento básico  
 En esta sección se describe el procedimiento básico que se usa para hospedar contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Las secciones restantes explican los detalles de cada paso.  
  
 La clave para hospedar contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] es la clase <xref:System.Windows.Interop.HwndSource>.  Esta clase encapsula el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], lo que le permite incorporarlo en su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria.  El siguiente enfoque combina [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una única aplicación.  
  
1.  Implemente su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como una clase administrada.  
  
2.  Implemente una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  Si está empezando con una aplicación existente y código [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] no administrado, lo normal es que lo habilite para llamar al código administrado; para ello, cambie la configuración del proyecto para incluir la marca de compilador `/clr`.  
  
3.  Establezca el modelo de subprocesos en contenedor uniproceso \(STA\).  
  
4.  Administre la notificación [WM\_CREATE](http://msdn.microsoft.com/library/ms632619.aspx) en el procedimiento de ventana y haga lo siguiente:  
  
    1.  Cree un nuevo objeto <xref:System.Windows.Interop.HwndSource> con la ventana primaria como su `parent` parámetro.  
  
    2.  Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3.  Asigne una referencia al objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> de <xref:System.Windows.Interop.HwndSource>.  
  
    4.  Obtenga el HWND para el contenido.  La propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> del objeto <xref:System.Windows.Interop.HwndSource> contiene el identificador de ventana \(HWND\).  Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.  
  
5.  Implemente una clase administrada que contenga un campo estático para contener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Esta clase le permite obtener una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde su código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
6.  Asigne el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al campo estático.  
  
7.  Adjunte un identificador a uno o varios de los eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8.  Comuníquese con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, etc.  
  
> [!NOTE]
>  También puede usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para implementar su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Sin embargo, tendrá que compilarlo por separado como una [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] y hacer referencia a esta [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] desde su aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  El resto del procedimiento es similar al descrito anteriormente.  
  
<a name="implementing_the_application"></a>   
## Implementación de la aplicación host  
 En esta sección se describe cómo hospedar contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una aplicación de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] básica.  El propio contenido se implementa en [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] como una clase administrada.  En su mayor parte, se trata de programación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sencilla.  Los aspectos clave de la implementación del contenido se tratan en el apartado [Implementación de contenido WPF](#implementing_the_wpf_page).  
  
<a name="autoNestedSectionsOUTLINE1"></a>   
-   [Aplicación básica](#the_basic_application)  
  
-   [Hospedaje de contenido WPF](#hosting_the_wpf_page)  
  
-   [Referencia al contenido WPF](#holding_a_reference)  
  
-   [Comunicación con el contenido WPF](#communicating_with_the_page)  
  
<a name="the_basic_application"></a>   
### Aplicación básica  
 El punto de partida para la aplicación host fue crear una plantilla [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
1.  Abra [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] y seleccione **Nuevo proyecto** en **Archivo**.  
  
2.  Seleccione **Win32** en la lista de tipos de proyecto de [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)].  Si el lenguaje predeterminado no es [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)], encontrará estos tipos de proyecto en **Otros lenguajes**.  
  
3.  Seleccione una plantilla de **Proyecto Win32**, asigne un nombre al proyecto y haga clic en **Aceptar** para iniciar el **Asistente para aplicaciones Win32**.  
  
4.  Acepte la configuración predeterminada del asistente y haga clic en **Finalizar** para iniciar el proyecto.  
  
 La plantilla crea una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] básica, que incluye:  
  
-   Un punto de entrada para la aplicación.  
  
-   Una ventana con un procedimiento de ventana asociado \(WndProc\).  
  
-   Un menú con los encabezados **Archivo** y **Ayuda**.  El menú **Archivo** tiene un elemento **Salir** que cierra la aplicación.  El menú **Ayuda** tiene un elemento **Acerca de** que inicia un cuadro de diálogo simple.  
  
 Antes de empezar a escribir código para hospedar el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], realice dos modificaciones en la plantilla básica.  
  
 La primera consiste en compilar el proyecto como código administrado.  De forma predeterminada, el proyecto se compila como código no administrado.  Sin embargo, dado que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en código administrado, el proyecto debe estar compilado consecuentemente.  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nombre del proyecto y seleccione **Propiedades** en el menú contextual para iniciar el cuadro de diálogo **Páginas de propiedades**.  
  
2.  Seleccione **Propiedades de configuración** en la vista de árbol del panel izquierdo.  
  
3.  Seleccione **Compatible con Common Language Runtime** en la lista **Valores predeterminados del proyecto** del panel derecho.  
  
4.  Seleccione **Compatible con Common Language Runtime \(\/clr\)** en el cuadro de lista desplegable.  
  
> [!NOTE]
>  Esta marca de compilador permite usar código administrado en la aplicación, pero el código no administrado seguirá compilándose como antes.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa el modelo de subprocesos de contenedor uniproceso \(STA\).  Para que funcione correctamente con el código de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe establecer el modelo de subprocesos de la aplicación en STA; para ello, aplique un atributo al punto de entrada.  
  
 [!code-cpp[Win32HostingWPFPage#WinMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]  
  
<a name="hosting_the_wpf_page"></a>   
### Hospedaje de contenido WPF  
 El contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es una aplicación de entrada de dirección simple.  Consta de varios controles <xref:System.Windows.Controls.TextBox> para tomar el nombre de usuario, la dirección, etc.  También hay dos controles <xref:System.Windows.Controls.Button>, **Aceptar** y **Cancelar**.  Cuando el usuario hace clic en **Aceptar**, el controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón recopila los datos de los controles <xref:System.Windows.Controls.TextBox>, los asigna a las propiedades correspondientes y genera un evento personalizado, `OnButtonClicked`.  Cuando el usuario hace clic en **Cancelar**, el controlador simplemente genera un `OnButtonClicked`.  El objeto de argumento de evento para `OnButtonClicked` contiene un campo booleano que indica en qué botón se hizo clic.  
  
 El código para hospedar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa en un controlador para la notificación [WM\_CREATE](http://msdn.microsoft.com/library/ms632619.aspx) en la ventana del host.  
  
 [!code-cpp[Win32HostingWPFPage#WMCreate](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]  
  
 El método `GetHwnd` toma la información de tamaño y posición más el elemento primario identificador de ventana y devuelve el identificador de ventana del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado.  
  
> [!NOTE]
>  No se puede usar una directiva `#using` para el espacio de nombres `System::Windows::Interop`.  Si lo hace, crearía un conflicto de nombres entre la estructura <xref:System.Windows.Interop.MSG> en ese espacio de nombres y la estructura MSG declarada en winuser.h.  En su lugar, debe usar nombres completos para tener acceso al contenido de ese espacio de nombres.  
  
 [!code-cpp[Win32HostingWPFPage#GetHwnd](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]  
  
 No se puede hospedar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] directamente en la ventana de la aplicación.  En su lugar, cree un objeto <xref:System.Windows.Interop.HwndSource> para encapsular el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Este objeto es básicamente una ventana diseñada para hospedar un contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para que el objeto <xref:System.Windows.Interop.HwndSource> se hospede en la ventana primaria, hay que crearlo como elemento secundario de una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] que forme parte de la aplicación.  Los parámetros de constructor <xref:System.Windows.Interop.HwndSource> contienen casi la misma información que se pasaría a CreateWindow al crear una ventana secundaria [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
 A continuación, cree una instancia del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En este caso, el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se implementa como una clase independiente, `WPFPage`, mediante [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  También puede implementar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Sin embargo, para ello deberá configurar un proyecto independiente y compilar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como una [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)].  Puede agregar una referencia a esa [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] en su proyecto y usar esa referencia para crear una instancia del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para mostrar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en la ventana secundaria, asigne una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del <xref:System.Windows.Interop.HwndSource>.  
  
 La siguiente línea de código adjunta un controlador de eventos, `WPFButtonClicked`, al evento `OnButtonClicked` del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Este controlador se llama cuando el usuario hace clic en el botón **Aceptar** o **Cancelar**.  Consulte la sección [Comunicación con el contenido WPF](#communicating_with_the_page) para obtener más información sobre este controlador de eventos.  
  
 La línea final del código mostrado devuelve el identificador de ventana \(HWND\) que está asociado al objeto <xref:System.Windows.Interop.HwndSource>.  Puede usar este identificador desde su código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para enviar mensajes a la ventana hospedada, aunque el ejemplo no lo hace.  El objeto <xref:System.Windows.Interop.HwndSource> genera un evento cada vez que recibe un mensaje.  Para procesar los mensajes, llame al método <xref:System.Windows.Interop.HwndSource.AddHook%2A> para adjuntar un controlador de mensajes y, a continuación, procese los mensajes en ese controlador.  
  
<a name="holding_a_reference"></a>   
### Referencia al contenido WPF  
 En muchas aplicaciones, deseará comunicarse con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] más adelante.  Por ejemplo, quizá desee modificar las propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o quizás quiera que el objeto <xref:System.Windows.Interop.HwndSource> hospede contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diferente.  Para ello, necesita una referencia al objeto <xref:System.Windows.Interop.HwndSource> o al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El objeto <xref:System.Windows.Interop.HwndSource> y su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado permanecen en memoria hasta que se destruya el identificador de ventana.  Sin embargo, la variable que asigne al objeto <xref:System.Windows.Interop.HwndSource> saldrá del ámbito tan pronto se devuelva un resultado desde el procedimiento de ventana.  La forma habitual de afrontar este problema con aplicaciones [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] consiste en usar una variable global o estática.  Por desgracia, no es posible asignar un objeto administrado a esos tipos de variables.  Puede asignar el identificador de ventana asociado al objeto <xref:System.Windows.Interop.HwndSource> a una variable global o estática, pero eso no proporciona acceso al objeto mismo.  
  
 La solución más sencilla para este problema es implementar una clase administrada con un conjunto de campos estáticos que contengan referencias a los objetos administrados a los que es necesario tener acceso.  En el ejemplo se usa la clase `WPFPageHost` para incluir una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], además de los valores iniciales de una serie de sus propiedades que el usuario puede cambiar posteriormente.  Esto se define en el encabezado.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageHost](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]  
  
 La última parte de la función `GetHwnd` asigna valores a esos campos para su uso posterior mientras `myPage` está todavía en el ámbito.  
  
<a name="communicating_with_the_page"></a>   
### Comunicación con el contenido WPF  
 Hay dos tipos de comunicación con el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La aplicación recibe información del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando el usuario hace clic en los botones **Aceptar** o **Cancelar**.  La aplicación también tiene una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que permite al usuario cambiar diversas propiedades del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como el tamaño de fuente predeterminado o el color de fondo.  
  
 Como se mencionó anteriormente, cuando el usuario hace clic en cualquiera de los botones, el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genera un evento `OnButtonClicked`.  La aplicación adjunta un controlador a este evento para recibir estas notificaciones.  Si se hizo clic en el botón **Aceptar**, el controlador obtiene la información de usuario del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y la muestra en un conjunto de controles estáticos.  
  
 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]  
  
 El controlador recibe un objeto de argumento de evento personalizado del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], `MyPageEventArgs`.  La propiedad `IsOK` del objeto está establecida en `true` si se hizo clic en el botón **Aceptar**, y en `false` si se hizo clic en el botón **Cancelar**.  
  
 Si se hizo clic en el botón **Aceptar**, el controlador obtiene una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la clase de contenedor.  A continuación, recopila la información del usuario incluida en las propiedades de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] asociado y usa los controles estáticos para mostrar la información en la ventana primaria.  Dado que los datos de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] están en forma de cadena administrada, deben serializarse para que pueda usarlos un control [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Si se hizo clic en el botón **Cancelar**, el controlador borra los datos de los controles estáticos.  
  
 La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación proporciona un conjunto de botones de radio que permiten al usuario modificar el color de fondo del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y varias propiedades relacionadas con la fuente.  El ejemplo siguiente es un extracto del procedimiento de ventana de la aplicación \(WndProc\) y su control de mensajes que establece varias propiedades en diferentes mensajes, incluido el color de fondo.  Los demás son similares y no se muestran.  Vea el ejemplo completo para obtener detalles y el contexto.  
  
 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]  
  
 Para establecer el color de fondo, obtenga una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(`hostedPage`\) de `WPFPageHost` y establezca la propiedad de color de fondo en el color apropiado.  En el ejemplo se usan tres opciones de color: el color original, verde claro y salmón claro.  El color de fondo original se almacena como un campo estático en la clase `WPFPageHost`.  Para establecer los otros dos, se crea un nuevo objeto <xref:System.Windows.Media.SolidColorBrush> y se pasa al constructor un valor de colores estático desde el objeto <xref:System.Windows.Media.Colors>.  
  
<a name="implementing_the_wpf_page"></a>   
## Implementación de la página WPF  
 Puede hospedar y usar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin ningún conocimiento de la implementación real.  Si el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se empaquetó en una [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] independiente, puede que se haya compilado en cualquier lenguaje [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  A continuación se incluye una breve explicación de la implementación de [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] que se usa en el ejemplo.  Esta sección contiene las subsecciones siguientes.  
  
<a name="autoNestedSectionsOUTLINE2"></a>   
-   [Diseño](#page_layout)  
  
-   [Devolución de datos a la ventana host](#returning_data_to_window)  
  
-   [Establecimiento de propiedades WPF](#set_page_properties)  
  
<a name="page_layout"></a>   
### Diseño  
 Los elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] constan de cinco controles <xref:System.Windows.Controls.TextBox>, con controles <xref:System.Windows.Controls.Label> asociados: nombre, dirección, ciudad, estado y código postal.  También hay dos controles <xref:System.Windows.Controls.Button>, **Aceptar** y **Cancelar**.  
  
 El contenido `WPFPage` se implementa en la clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El diseño se controla con un elemento de diseño <xref:System.Windows.Controls.Grid>.  La clase hereda de <xref:System.Windows.Controls.Grid>, lo que lo convierte en el elemento raíz del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 El constructor de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] toma el ancho y el alto necesarios y modifica en consecuencia el tamaño de <xref:System.Windows.Controls.Grid>.  A continuación, para definir el diseño básico, crea un conjunto de objetos <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> y los agrega a las colecciones <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> y <xref:System.Windows.Controls.Grid.RowDefinitions%2A> de la base de objeto <xref:System.Windows.Controls.Grid>, respectivamente.  Esto define una cuadrícula de cinco filas y siete columnas, con las dimensiones determinadas por el contenido de las celdas.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]  
  
 A continuación, el constructor agrega los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a <xref:System.Windows.Controls.Grid>.  El primer elemento es el texto del título, que es un control <xref:System.Windows.Controls.Label> que se centra en la primera fila de la cuadrícula.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]  
  
 La siguiente fila contiene el control <xref:System.Windows.Controls.Label> de nombre y su control <xref:System.Windows.Controls.TextBox> asociado.  Dado que se usa el mismo código para cada par de etiqueta\/cuadro de texto, está colocado en un par de métodos privados y se usa para los cinco pares de etiqueta\/cuadro de texto.  Los métodos crean el control apropiado y llaman a los métodos estáticos <xref:System.Windows.Controls.Grid.SetColumn%2A> y <xref:System.Windows.Controls.Grid.SetRow%2A> de la clase <xref:System.Windows.Controls.Grid> para colocar los controles en la celda correspondiente.  Una vez creado el control, el ejemplo llama al método <xref:System.Windows.Controls.UIElementCollection.Add%2A> en la propiedad <xref:System.Windows.Controls.Panel.Children%2A> de <xref:System.Windows.Controls.Grid> para agregar el control a la cuadrícula.  El código para agregar los pares restantes de etiqueta\/cuadro de texto es similar.  Vea el código de ejemplo para obtener más detalles.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]  
  
 La implementación de los dos métodos es la siguiente:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]  
  
 Finalmente, en el ejemplo se agregan los botones **Aceptar** y **Cancelar** y se adjunta un controlador de eventos para sus eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]  
  
<a name="returning_data_to_window"></a>   
### Devolución de datos a la ventana host  
 Cuando se hace clic en cualquiera de los botones, se genera su evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  La ventana host simplemente podría asociar controladores a estos eventos y obtener los datos directamente desde los controles <xref:System.Windows.Controls.TextBox>.  En el ejemplo se usa un enfoque algo menos directo.  Controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dentro del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, a continuación, genera un evento personalizado `OnButtonClicked` para notificar al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Esto permite al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] realizar alguna validación de parámetros antes de notificar al host.  El controlador obtiene el texto de los controles <xref:System.Windows.Controls.TextBox> y lo asigna a propiedades públicas, desde las que el host puede recuperar la información.  
  
 La declaración de evento, en WPFPage.h:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]  
  
 El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, en WPFPage.cpp:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]  
  
<a name="set_page_properties"></a>   
### Establecimiento de propiedades WPF  
 El host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] permite al usuario cambiar varias propiedades de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Desde el lado [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], se trata simplemente de una cuestión de cambiar las propiedades.  La implementación en la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es un poco más complicada, porque no hay ninguna propiedad global única que controle las fuentes de todos los controles.  En su lugar, se cambia la propiedad adecuada para cada control en los descriptores del conjunto de propiedades.  En el ejemplo siguiente se muestra el código para la propiedad `DefaultFontFamily`.  Al establecer la propiedad, se llama a un método privado que a su vez establece las propiedades <xref:System.Windows.Controls.Control.FontFamily%2A> de los diversos controles.  
  
 Desde WPFPage.h:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]  
  
 Desde WPFPage.cpp:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]  
  
## Vea también  
 <xref:System.Windows.Interop.HwndSource>   
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)