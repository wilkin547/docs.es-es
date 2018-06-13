---
title: Información general sobre ventanas de WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: ad7d5225dbaaae544ab463a8f4f16bc43bdf4098
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558127"
---
# <a name="wpf-windows-overview"></a>Información general sobre ventanas de WPF
Los usuarios interactúan con aplicaciones de Windows Presentation Foundation (WPF) independiente a través de windows. El propósito principal de una ventana es hospedar contenido que permita visualizar datos y que permita a los usuarios interactuar con estos. Independiente [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones proporcionan sus propias ventanas mediante la <xref:System.Windows.Window> clase. Este tema se presentan <xref:System.Windows.Window> antes de tratar los conceptos básicos de creación y administración de windows en las aplicaciones independientes.  
  
> [!NOTE]
>  Hospedadas en explorador [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones, incluidos [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] y malas [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] páginas, no proporcionan sus propias ventanas. En su lugar, se hospedan en ventanas proporcionadas por [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]. Vea [información general de las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
  
<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Clase de la ventana  
 La ilustración siguiente muestra las partes constituyentes de una ventana.  
  
 ![Elementos de la ventana](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Una ventana se divide en dos áreas: el área distinta del cliente y el área cliente.  
  
 El *área no cliente* de una ventana se implementa mediante [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e incluye las partes de una ventana que son comunes a la mayoría de las ventanas, incluidos los siguientes:  
  
-   Un borde.  
  
-   Una barra de título.  
  
-   Un icono.  
  
-   Botones Minimizar, Maximizar y Restaurar.  
  
-   Un botón Cerrar.  
  
-   Un menú de sistema con elementos de menú que permiten a los usuarios minimizar, maximizar, restaurar, mover, cambiar el tamaño y cerrar una ventana.  
  
 El *área cliente* de una ventana es el área dentro del área no cliente de una ventana y lo utilizan los desarrolladores para agregar contenido específico de la aplicación, como barras de menús, barras de herramientas y controles.  
  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], una ventana es encapsulada por el <xref:System.Windows.Window> clase que usa para hacer lo siguiente:  
  
-   Mostrar una ventana.  
  
-   Configurar el tamaño, posición y aspecto de una ventana.  
  
-   Hospedar contenido específico de la aplicación.  
  
-   Administrar la duración de una ventana.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Implementar una ventana  
 La implementación de una ventana típica consta de apariencia y comportamiento, donde *apariencia* define el aspecto de una ventana para usuarios y *comportamiento* define la forma en que las funciones de una ventana cuando los usuarios interactúan con él. En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], puede implementar la apariencia y comportamiento de una ventana con codificar o [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 En general, sin embargo, la apariencia de una ventana se implementa mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado y su comportamiento se implementa mediante código subyacente, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Para habilitar un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de marcado y el archivo de código subyacente para trabajar conjuntamente, se necesita lo siguiente:  
  
-   En el marcado, el `Window` elemento debe incluir el `x:Class` atributo. Cuando se compila la aplicación, la existencia de `x:Class` en el marcado hace archivo [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] para crear un `partial` clase que deriva de <xref:System.Windows.Window> y tiene el nombre especificado por el `x:Class` atributo. Esto requiere la adición de un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] declaración de espacio de nombres para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esquema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Generado `partial` la clase implementa la `InitializeComponent` método, que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.  
  
-   En el código subyacente, la clase debe ser un `partial` clase con el mismo nombre que se especifica mediante la `x:Class` atributo en el marcado y se debe derivar de <xref:System.Windows.Window>. Esto permite que el archivo de código subyacente asociar a la `partial` clase que se genera para el archivo de marcado cuando se compila la aplicación (consulte [compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   En el código subyacente, el <xref:System.Windows.Window> clase debe implementar un constructor que llama el `InitializeComponent` método. `InitializeComponent` se implementa mediante el marcado generado de archivo `partial` clase para registrar eventos y establecer las propiedades que se definen en el marcado.  
  
> [!NOTE]
>  Cuando se agrega un nuevo <xref:System.Windows.Window> al proyecto mediante el uso de [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], el <xref:System.Windows.Window> se implementa mediante marcado y código subyacente e incluye la configuración necesaria para crear la asociación entre los archivos de código subyacente y marcado como se describe aquí.  
  
 Con esta configuración en su lugar, puede centrarse en definir el aspecto de la ventana de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado e implementar su comportamiento en el código subyacente. En el ejemplo siguiente se muestra una ventana con un botón, implementado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado y un controlador de eventos para el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, implementado en código subyacente.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Configuración de una definición de ventana para MSBuild  
 Cómo implementar la ventana determina cómo está configurada para [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]. Para una ventana que se define utilizando tanto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado y código subyacente:  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos de marcado se configuran como [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementos.  
  
-   Archivos de código subyacente se configuran como [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` elementos.  
  
 Esto se muestra en la siguiente [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] archivo de proyecto.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Para obtener información sobre la compilación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] las aplicaciones, vea [compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Duración de ventana  
 Como cualquier clase, una ventana tiene una vigencia que comienza cuando se crea una instancia por primera vez, después de lo cual se abre, activa y desactiva y, finalmente, se cierra.  
  
  
<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Abrir una ventana  
 Para abrir una ventana, primero hay que crear una instancia de esta, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 En este ejemplo, el `MarkupAndCodeBehindWindow` se crea una instancia cuando se inicia la aplicación, que se produce cuando el <xref:System.Windows.Application.Startup> evento se desencadena.  
  
 Cuando se crea una instancia de una ventana, automáticamente se agrega una referencia a él a una lista de windows que administra el <xref:System.Windows.Application> objeto (consulte <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Además, la primera ventana que se creará una instancia, de forma predeterminada, establece <xref:System.Windows.Application> como la ventana de la aplicación principal (vea <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 Por último, se abre la ventana mediante una llamada a la <xref:System.Windows.Window.Show%2A> método; el resultado se muestra en la ilustración siguiente.  
  
 ![Ventana abierta mediante una llamada a Window.Show](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Una ventana que se abre mediante una llamada a <xref:System.Windows.Window.Show%2A> es una ventana no modal, lo que significa que la aplicación funciona en un modo que permite a los usuarios activar otras ventanas en la misma aplicación.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> se llama para abrir ventanas como cuadros de diálogo de forma modal. Vea [información general de cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) para obtener más información.  
  
 Cuando <xref:System.Windows.Window.Show%2A> es llama, una ventana realiza trabajo de inicialización antes de que se muestra para establecer una infraestructura que le permite recibir proporcionados por el usuario. Cuando se inicializa la ventana, el <xref:System.Windows.Window.SourceInitialized> se genera el evento y se muestra la ventana.  
  
 Como método abreviado, <xref:System.Windows.Application.StartupUri%2A> se puede establecer para especificar la primera ventana que se abre automáticamente cuando se inicia una aplicación.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Cuando se inicia la aplicación, la ventana especificada por el valor de <xref:System.Windows.Application.StartupUri%2A> se abre forma no modal; internamente, la ventana se abre mediante una llamada a su <xref:System.Windows.Window.Show%2A> método.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Propiedad de la ventana  
 Una ventana que se abre mediante el <xref:System.Windows.Window.Show%2A> método no tiene una relación implícita con la ventana que lo creó; los usuarios pueden interactuar con cualquier ventana independientemente de la otra, lo que significa que cualquier ventana puede hacer lo siguiente:  
  
-   Cubrir las demás (a menos que una de las ventanas tenga su <xref:System.Windows.Window.Topmost%2A> propiedad establecida en `true`).  
  
-   Minimizarse, maximizarse y restaurarse sin que afecte a las demás.  
  
 Algunas ventanas requieren una relación con la ventana que las abre. Por ejemplo, un [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] aplicación puede abrir ventanas de propiedades y las ventanas de herramientas cuyo comportamiento típico es cubrir la ventana que las crea. Además, dichas ventanas se deben siempre cerrar, minimizar, maximizar y restaurar de acuerdo con la ventana que las creó. Este tipo de relación se puede establecer mediante la realización de una ventana *propio* otro y se logra estableciendo la <xref:System.Windows.Window.Owner%2A> propiedad de la *propiedad de la ventana* con una referencia a la *propietario ventana*. Esta implementación se muestra en el ejemplo siguiente.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Una vez establecida la propiedad:  
  
-   La ventana de propiedad puede hacer referencia a su ventana propietaria inspeccionando el valor de su <xref:System.Windows.Window.Owner%2A> propiedad.  
  
-   La ventana propietaria puede detectar todas las ventanas que posee inspeccionando el valor de su <xref:System.Windows.Window.OwnedWindows%2A> propiedad.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Prevención de la activación de ventanas  
 Existen escenarios donde windows no deben activarse si se muestran como ventanas de conversación de una aplicación de estilo de mensajería de Internet o ventanas de notificación de una aplicación de correo electrónico.  
  
 Si la aplicación tiene una ventana que no debería activarse cuando se muestra, puede establecer su <xref:System.Windows.Window.ShowActivated%2A> propiedad `false` antes de llamar a la <xref:System.Windows.Window.Show%2A> método por primera vez. Como resultado:  
  
-   La ventana no está activada.  
  
-   La ventana <xref:System.Windows.Window.Activated> no se produce el evento.  
  
-   La ventana actualmente activada permanece activada.  
  
 Sin embargo, la ventana se activará tan pronto como el usuario la active haciendo clic en el área de cliente o en el área distinta del cliente. En este caso:  
  
-   La ventana se activa.  
  
-   La ventana <xref:System.Windows.Window.Activated> evento se desencadena.  
  
-   La ventana activada previamente se desactiva.  
  
-   La ventana <xref:System.Windows.Window.Deactivated> y <xref:System.Windows.Window.Activated> posteriormente se generan eventos según lo previsto en respuesta a las acciones del usuario.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Activación de ventanas  
 Cuando se abre una ventana por primera vez, se convierte en la ventana activa (a menos que se muestra con <xref:System.Windows.Window.ShowActivated%2A> establecido en `false`). El *ventana activa* es la ventana que está capturando los proporcionados por el usuario, como las pulsaciones de teclas y los clics del mouse. Cuando se convierte en una ventana activa, se produce la <xref:System.Windows.Window.Activated> eventos.  
  
> [!NOTE]
>  Cuando se abre una ventana por primera vez, el <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.Window.ContentRendered> se generan eventos sólo después el <xref:System.Windows.Window.Activated> evento se desencadena. Con esto en mente, una ventana de forma eficaz se puede considerar abierto cuando <xref:System.Windows.Window.ContentRendered> se genera.  
  
 Después de que se activa una ventana, un usuario puede activar otra ventana de la misma aplicación o activar otra aplicación. Cuando esto ocurre, la ventana actualmente activa se convierte en desactivado y genera el <xref:System.Windows.Window.Deactivated> eventos. Del mismo modo, cuando el usuario selecciona una ventana actualmente desactivada, la ventana se vuelve activa y <xref:System.Windows.Window.Activated> se genera.  
  
 Un motivo habitual para controlar <xref:System.Windows.Window.Activated> y <xref:System.Windows.Window.Deactivated> es habilitar y deshabilitar la funcionalidad que se puede ejecutar sólo cuando una ventana está activa. Por ejemplo, algunas ventanas muestran contenido interactivo que requiere la entrada o atención del usuario constante, incluidos los reproductores de vídeo y los juegos. El ejemplo siguiente es un Reproductor de vídeo simplificado que muestra cómo controlar <xref:System.Windows.Window.Activated> y <xref:System.Windows.Window.Deactivated> para implementar este comportamiento.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Cuando se desactiva una ventana, otros tipos de aplicaciones pueden ejecutar código en segundo plano. Por ejemplo, un cliente de correo puede continuar sondeando el servidor de correo electrónico mientras el usuario está utilizando otras aplicaciones. Las aplicaciones como estas suelen ofrecen un comportamiento diferente o adicional mientras la ventana principal está desactivada. Con respecto al programa de correo electrónico, esto puede significar agregar el nuevo elemento de correo a la bandeja de entrada o agregar un icono de notificación a la bandeja del sistema. Solamente es necesario mostrar un icono de notificación cuando la ventana de correo electrónico no está activo, que se puede determinar mediante la inspección del <xref:System.Windows.Window.IsActive%2A> propiedad.  
  
 Si se completa una tarea en segundo plano, una ventana que desee notificar al usuario más urgente mediante una llamada a <xref:System.Windows.Window.Activate%2A> método. Si el usuario está interactuando con otra aplicación activada cuando <xref:System.Windows.Window.Activate%2A> se llama, parpadeará el botón de barra de tareas de la ventana. Si un usuario está interactuando con la aplicación actual, la llamada a <xref:System.Windows.Window.Activate%2A> aparecerá la ventana a primer plano.  
  
> [!NOTE]
>  Puede administrar la activación del ámbito de la aplicación utilizando la <xref:System.Windows.Application.Activated?displayProperty=nameWithType> y <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> eventos.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Cerrar una ventana  
 La vigencia de una ventana llega a su fin cuando un usuario la cierra. Se puede cerrar una ventana mediante elementos del área distinta del cliente, entre los que cabe incluir los siguientes:  
  
-   El **cerrar** elemento de la **System** menú.  
  
-   Presionar ALT+F4.  
  
-   Al presionar la **cerrar** botón.  
  
 Puede proporcionar mecanismos adicionales al área cliente para cerrar una ventana. Entre los más habituales se incluyen los siguientes:  
  
-   Un **Exit** de elemento en el **archivo** menú, normalmente para ventanas de la aplicación principal.  
  
-   A **cerrar** de elemento en el **archivo** menú, normalmente en una ventana secundaria de la aplicación.  
  
-   A **cancelar** botón, normalmente en un cuadro de diálogo modal.  
  
-   A **cerrar** botón, normalmente en un cuadro de diálogo no modal.  
  
 Para cerrar una ventana en respuesta a uno de estos mecanismos personalizados, debe llamar a la <xref:System.Windows.Window.Close%2A> método. En el ejemplo siguiente se implementa la capacidad de cerrar una ventana eligiendo la **Exit** en el **archivo** menú.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Cuando se cierra una ventana, genera dos eventos: <xref:System.Windows.Window.Closing> y <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> se produce antes de que se cierra la ventana y proporciona un mecanismo de qué ventana se puede evitar la cierre. Una razón común para evitar el cierre de la ventana se produce en caso de que el contenido de la ventana contenga datos modificados. En esta situación, el <xref:System.Windows.Window.Closing> se puede controlar el evento para determinar si los datos están desfasadas y, si es así, para preguntar al usuario si desea continuar cerrando la ventana sin guardar los datos o cancelar el cierre de la ventana. En el ejemplo siguiente se muestra los aspectos clave del control <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  
 
  
 El <xref:System.Windows.Window.Closing> controlador de eventos se pasa un <xref:System.ComponentModel.CancelEventArgs>, que implementa el `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad que se establece en `true` para impedir que se cierre una ventana.  
  
 Si <xref:System.Windows.Window.Closing> no está controlado, o se administra pero no cancela, la ventana se cerrará. Justo antes de que realmente se cierra una ventana, <xref:System.Windows.Window.Closed> se genera. En este momento, ya no se puede impedir el cierre de la ventana.  
  
> [!NOTE]
>  Una aplicación puede configurarse para apagar automáticamente cuando se cierra la ventana de aplicación principal (vea <xref:System.Windows.Application.MainWindow%2A>) o se cierra la última ventana. Para obtener información detallada, vea <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Mientras que una ventana se puede cerrar explícitamente a través de los mecanismos proporcionados en las áreas de cliente y no cliente, una ventana también se puede cerrar implícitamente como resultado un comportamiento en otras partes de la aplicación o [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], incluidos los siguientes:  
  
-   Un usuario cierra la sesión o se cierra Windows.  
  
-   Propietario de la ventana se cierra (consulte <xref:System.Windows.Window.Owner%2A>).  
  
-   Se cierra la ventana de la aplicación principal y <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
-   Se llama a <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
>  No se puede volver a abrir una ventana cuando se ha cerrado.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Eventos de vigencia de ventanas  
 La ilustración siguiente muestra la secuencia de eventos principales en la vigencia de una ventana.  
  
 ![Window Lifetime](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 En la siguiente ilustración muestra la secuencia de eventos principales en la duración de una ventana que se muestra sin activación (<xref:System.Windows.Window.ShowActivated%2A> está establecido en `false` antes de que se muestra la ventana).  
  
 ![Window Lifetime &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Ubicación de la ventana  
 Mientras una ventana está abierta, tiene una ubicación en las dimensiones x e y en relación con el escritorio. Esta ubicación puede determinarse inspeccionando la <xref:System.Windows.Window.Left%2A> y <xref:System.Windows.Window.Top%2A> propiedades, respectivamente. Puede establecer estas propiedades para cambiar la ubicación de la ventana.  
  
 También puede especificar la ubicación inicial de un <xref:System.Windows.Window> cuando aparece por primera vez estableciendo la <xref:System.Windows.Window.WindowStartupLocation%2A> propiedad con uno de los siguientes <xref:System.Windows.WindowStartupLocation> valores de enumeración:  
  
-   <xref:System.Windows.WindowStartupLocation.CenterOwner> (valor predeterminado)  
  
-   <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
-   <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Si se especifica la ubicación de inicio como <xref:System.Windows.WindowStartupLocation.Manual>y el <xref:System.Windows.Window.Left%2A> y <xref:System.Windows.Window.Top%2A> no se han establecido propiedades, <xref:System.Windows.Window> le preguntará Windows para una ubicación que aparezcan en.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Ventanas de nivel superior y orden Z  
 Además de tener una ubicación x e y, una ventana también tiene una ubicación en la dimensión z, que determina su posición vertical con respecto a otras ventanas. Esto se conoce como el orden z de la ventana y hay dos tipos: orden z normal y orden z superior. La ubicación de una ventana en la *orden z normal* se determina por si está actualmente activa o no. De forma predeterminada, una ventana se encuentra en el orden z normal. La ubicación de una ventana en la *orden z superior* también se determina por si está actualmente activa o no. Además, las ventanas del orden z superior siempre se encuentran por encima de aquellas del orden z normal. Una ventana se encuentra en el orden z superior estableciendo su <xref:System.Windows.Window.Topmost%2A> propiedad `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 Dentro de cada orden z, la ventana actualmente activa aparece encima de las demás ventanas del mismo orden z.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Tamaño de ventana  
 Además de tener una ubicación en el escritorio, una ventana tiene un tamaño determinado por varias propiedades, incluidas las distintas propiedades de ancho y alto y <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, y <xref:System.Windows.FrameworkElement.MaxWidth%2A> se utilizan para administrar el intervalo de anchos una ventana puede tener durante su duración y que están configuradas tal como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Alto de la ventana está administrado por <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, y <xref:System.Windows.FrameworkElement.MaxHeight%2A>y están configuradas tal como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Dado que los distintos valores de anchura y altura especifican cada uno de ellos un intervalo, es posible que la anchura y altura de una ventana de tamaño ajustable se encuentre dentro del intervalo especificado para la dimensión correspondiente. Para detectar su ancho y alto actuales, inspeccione <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectivamente.  
  
 Si desea que el ancho y alto de la ventana para tener un tamaño que se ajuste al tamaño de la ventana del contenido, puede usar el <xref:System.Windows.Window.SizeToContent%2A> propiedad, que tiene los siguientes valores:  
  
-   <xref:System.Windows.SizeToContent.Manual>. Ningún efecto (valor predeterminado).  
  
-   <xref:System.Windows.SizeToContent.Width>. Ajustar al ancho del contenido, que tiene el mismo efecto que establecer ambos <xref:System.Windows.FrameworkElement.MinWidth%2A> y <xref:System.Windows.FrameworkElement.MaxWidth%2A> el ancho del contenido.  
  
-   <xref:System.Windows.SizeToContent.Height>. Ajustar al alto del contenido, que tiene el mismo efecto que establecer ambos <xref:System.Windows.FrameworkElement.MinHeight%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A> el alto del contenido.  
  
-   <xref:System.Windows.SizeToContent.WidthAndHeight>. Ajustar al ancho del contenido y el alto, que tiene el mismo efecto que establecer ambos <xref:System.Windows.FrameworkElement.MinHeight%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A> el alto del contenido y configuración de ambos <xref:System.Windows.FrameworkElement.MinWidth%2A> y <xref:System.Windows.FrameworkElement.MaxWidth%2A> el ancho del contenido.  
  
 En el ejemplo siguiente se muestra una ventana que se redimensiona automáticamente para ajustarse al contenido, tanto vertical como horizontalmente, cuando se muestra por primera vez.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Window.SizeToContent%2A> propiedad en el código para especificar cómo cambia el tamaño de una ventana para ajustar su contenido.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Orden de prioridad de las propiedades de tamaño  
 Esencialmente, las diversas propiedades de tamaño de una ventana se combinan para definir el intervalo de anchura y altura de una ventana de tamaño ajustable. Para asegurarse de que se mantiene un intervalo válido, <xref:System.Windows.Window> evalúa los valores de las propiedades de tamaño utilizando las órdenes de prioridad siguientes.  
  
 **Para las propiedades de altura:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Para las propiedades de anchura:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 El orden de precedencia puede determinar el tamaño de una ventana cuando está maximizado, que se administran mediante el <xref:System.Windows.Window.WindowState%2A> propiedad.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Estado de la ventana  
 Durante la vigencia de una ventana de tamaño ajustable, esta puede tener tres estados: normal, minimizado y maximizado. Una ventana con un *normal* estado es el estado predeterminado de una ventana. Una ventana con este estado permite al usuario moverla y cambiar su tamaño mediante los controles de cambio de tamaño o el borde, si es de tamaño ajustable.  
  
 Una ventana con un *minimizado* estado se contrae hasta su botón de barra de tareas si <xref:System.Windows.Window.ShowInTaskbar%2A> está establecido en `true`; en caso contrario, contrae hasta el tamaño más pequeño posible puede ser y reubica en la esquina inferior izquierda del escritorio. Ningún tipo de ventana minimizada puede cambiar de tamaño mediante el borde ni mediante los controles de cambio de tamaño, aunque si no aparece en la barra de tareas se podrá arrastrar a cualquier parte del escritorio.  
  
 Una ventana con un *maximizado* estado se expande hasta el tamaño máximo que puede ser, que solo será tan grande como su <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, y <xref:System.Windows.Window.SizeToContent%2A> dictan de propiedades. Al igual que una ventana minimizada, no puede cambiarse el tamaño de una ventana maximizada mediante un control de cambio de tamaño ni arrastrando el borde.  
  
> [!NOTE]
>  Los valores de la <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, y <xref:System.Windows.FrameworkElement.Height%2A> propiedades de una ventana siempre representan los valores para el estado normal, incluso cuando la ventana actualmente está maximizada o minimizada.  
  
 El estado de una ventana se puede configurar estableciendo su <xref:System.Windows.Window.WindowState%2A> propiedad, que puede tener uno de los siguientes <xref:System.Windows.WindowState> valores de enumeración:  
  
-   <xref:System.Windows.WindowState.Normal> (valor predeterminado)  
  
-   <xref:System.Windows.WindowState.Maximized>  
  
-   <xref:System.Windows.WindowState.Minimized>  
  
 En el ejemplo siguiente se muestra cómo crear una ventana que se muestra como maximizada cuando se abre.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 En general, debería establecer <xref:System.Windows.Window.WindowState%2A> para configurar el estado inicial de una ventana. Cuando aparece una ventana de tamaño ajustable, los usuarios pueden presionar los botones para minimizar, maximizar y restaurar situados en la barra de título de la ventana para cambiar el estado de esta.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Aspecto de la ventana  
 Puede cambiar el aspecto del área cliente de una ventana mediante la adición de contenido específico, como botones, etiquetas y cuadros de texto. Para configurar el área no cliente, <xref:System.Windows.Window> proporciona varias propiedades, que incluyen <xref:System.Windows.Window.Icon%2A> para establecer el icono de una ventana y <xref:System.Windows.Window.Title%2A> para establecer su título.  
  
 También puede cambiar el aspecto y comportamiento del borde del área distinta del cliente configurando el modo de cambio de tamaño de la ventana, el estilo de esta y si aparece como un botón en la barra de tareas del escritorio.  
  
  
<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Modo de cambio de tamaño  
 En función de la <xref:System.Windows.Window.WindowStyle%2A> propiedad, puede controlar cómo (y si) se puede cambiar el tamaño de la ventana. La opción de estilo de ventana determina si un usuario puede cambiar el tamaño de la ventana arrastrando su borde con el mouse, si la **minimizar**, **maximizar**, y **cambiar el tamaño de** botones aparecen en el área no cliente, y, si aparecen, si están habilitadas.  
  
 Puede configurar cómo cambia el tamaño de una ventana estableciendo su <xref:System.Windows.Window.ResizeMode%2A> propiedad, que puede ser uno de los siguientes <xref:System.Windows.ResizeMode> valores de enumeración:  
  
-   <xref:System.Windows.ResizeMode.NoResize>  
  
-   <xref:System.Windows.ResizeMode.CanMinimize>  
  
-   <xref:System.Windows.ResizeMode.CanResize> (valor predeterminado)  
  
-   <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Al igual que con <xref:System.Windows.Window.WindowStyle%2A>, es improbable que cambie durante su duración, lo que significa que es más probable es que configuran desde el modo de cambio de tamaño de una ventana [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Tenga en cuenta que puede detectar si una ventana está maximizada, minimizada o restaurada inspeccionando el <xref:System.Windows.Window.WindowState%2A> propiedad.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Estilo de ventana  
 El borde que se expone desde el área distinta del cliente de una ventana es adecuado para la mayoría de las aplicaciones. Sin embargo, hay circunstancias donde se necesitan tipos diferentes de borde o no se necesita ningún borde en absoluto, dependiendo del tipo de ventana.  
  
 Para controlar qué tipo de borde de una ventana obtiene, establecer su <xref:System.Windows.Window.WindowStyle%2A> propiedad con uno de los siguientes valores de la <xref:System.Windows.WindowStyle> enumeración:  
  
-   <xref:System.Windows.WindowStyle.None>  
  
-   <xref:System.Windows.WindowStyle.SingleBorderWindow> (valor predeterminado)  
  
-   <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
-   <xref:System.Windows.WindowStyle.ToolWindow>  
  
 El efecto de estos estilos de ventana se muestra en la ilustración siguiente.  
  
 ![Estilos de ventana](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.PNG "WindowOverviewFigure6")  
  
 Puede establecer <xref:System.Windows.Window.WindowStyle%2A> mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o marcado del código; porque es improbable que cambie durante la duración de una ventana, más probable es que configurará con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Estilo de ventana no rectangular  
 También hay situaciones donde el borde estilos que <xref:System.Windows.Window.WindowStyle%2A> permite tener no es suficientes. Por ejemplo, puede que desee crear una aplicación con un borde no rectangular, como [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] usa.  
  
 Considere, por ejemplo, la ventana de globo que se muestra en la ilustración siguiente.  
  
 ![Ventana no rectangular](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Se puede crear este tipo de ventana estableciendo la <xref:System.Windows.Window.WindowStyle%2A> propiedad <xref:System.Windows.WindowStyle.None>y mediante el comando especial compatible con esto <xref:System.Windows.Window> tiene para la transparencia.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Esta combinación de valores indica a la ventana que se puede representar de forma totalmente transparente. En este estado, no se pueden usar las opciones del área distinta del cliente de la ventana (el menú Cerrar, los botones para minimizar, maximizar y restaurar, etc.). Por consiguiente, deberá proporcionar las suyas propias.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Presencia de la barra de tareas  
 El aspecto predeterminado de una ventana incluye un botón de barra de tareas, como el que se muestra en la siguiente ilustración.  
  
 ![Ventana con un botón de barra de tareas](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.PNG "WindowOverviewFigure7")  
  
 Algunos tipos de windows no tienen un botón de barra de tareas, como cuadros de mensaje y cuadros de diálogo (vea [información general de cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)). Puede controlar si se muestra el botón de barra de tareas para una ventana estableciendo la <xref:System.Windows.Window.ShowInTaskbar%2A> propiedad (`true` de forma predeterminada).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Consideraciones de seguridad  
 <xref:System.Windows.Window> requiere `UnmanagedCode` permiso de seguridad que se creará una instancia. Para aquellas aplicaciones instaladas e iniciadas desde la máquina local, esto pertenece al conjunto de permisos que se conceden a la aplicación.  
  
 Sin embargo, esto no entra en el conjunto de permisos concedidos a las aplicaciones que se inician desde la Internet o Local intranet zona utilizando [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]. Por lo tanto, los usuarios recibirán un [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] advertencia de seguridad y tendrá que elevar el conjunto de permisos para la aplicación en plena confianza.  
  
 Además, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no se pueden mostrar ventanas o cuadros de diálogo de forma predeterminada. Para obtener información sobre las consideraciones de seguridad de aplicación independiente, consulte [estrategia de seguridad de WPF: seguridad de la plataforma](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Otros tipos de ventanas  
 <xref:System.Windows.Navigation.NavigationWindow> es una ventana diseñada para hospedar contenido navegable. Para obtener más información, consulte [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md)).  
  
 Los cuadros de diálogo son ventanas que se suelen utilizar para recopilar información de un usuario para completar una función. Por ejemplo, cuando un usuario desea abrir un archivo, el **abrir archivo** cuadro de diálogo se muestra normalmente una aplicación para obtener el nombre de archivo del usuario. Para obtener más información, vea [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Window>  
 <xref:System.Windows.MessageBox>  
 <xref:System.Windows.Navigation.NavigationWindow>  
 <xref:System.Windows.Application>  
 [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)  
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
