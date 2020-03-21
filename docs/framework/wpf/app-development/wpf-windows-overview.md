---
title: Visión general de Windows
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
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145545"
---
# <a name="wpf-windows-overview"></a>Información general sobre ventanas de WPF
Los usuarios interactúan con aplicaciones independientes de Windows Presentation Foundation (WPF) a través de Windows. El propósito principal de una ventana es hospedar contenido que permita visualizar datos y que permita a los usuarios interactuar con estos. Las aplicaciones WPF independientes proporcionan <xref:System.Windows.Window> sus propias ventanas mediante la clase. En este <xref:System.Windows.Window> tema se presenta antes de cubrir los fundamentos de la creación y administración de ventanas en aplicaciones independientes.  
  
> [!NOTE]
> Las aplicaciones WPF hospedadas en el explorador, incluidas las aplicaciones de explorador XAML (XBAP) y las páginas sueltas, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] no proporcionan sus propias ventanas. En su lugar, se hospedan en ventanas proporcionadas por Windows Internet Explorer. Consulte [Información general sobre aplicaciones de explorador XAML](wpf-xaml-browser-applications-overview.md)de WPF .  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a>Clase de la ventana  
 La figura siguiente ilustra las partes constitutivas de una ventana:  
  
 ![Captura de pantalla que muestra los elementos de la ventana.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Una ventana se divide en dos áreas: el área distinta del cliente y el área cliente.  
  
 WPFWPF implementa el *área no cliente* de una ventana e incluye las partes de una ventana que son comunes a la mayoría de las ventanas, incluidas las siguientes:  
  
- Un borde.  
  
- Una barra de título.  
  
- Un icono.  
  
- Botones Minimizar, Maximizar y Restaurar.  
  
- Un botón Cerrar.  
  
- Un menú de sistema con elementos de menú que permiten a los usuarios minimizar, maximizar, restaurar, mover, cambiar el tamaño y cerrar una ventana.  
  
 El área de *cliente* de una ventana es el área dentro del área no cliente de una ventana y los desarrolladores lo usan para agregar contenido específico de la aplicación, como barras de menús, barras de herramientas y controles.  
  
 En WPFWPF, la <xref:System.Windows.Window> clase que se usa para hacer lo siguiente encapsula una ventana:  
  
- Mostrar una ventana.  
  
- Configurar el tamaño, posición y aspecto de una ventana.  
  
- Hospedar contenido específico de la aplicación.  
  
- Administrar la duración de una ventana.  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a>Implementar una ventana  
 La implementación de una ventana típica comprende apariencia y comportamiento, donde la *apariencia* define cómo se ve una ventana para los usuarios y el *comportamiento* define la forma en que una ventana funciona a medida que los usuarios interactúan con ella. En WPFWPF, puede implementar la apariencia y el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] comportamiento de una ventana mediante código o marcado.  
  
 En general, sin embargo, la apariencia [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de una ventana se implementa mediante marcado y su comportamiento se implementa mediante código subyacente, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Para permitir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que un archivo de marcado y un archivo de código subyacente funcionen juntos, se requiere lo siguiente:  
  
- En el `Window` marcado, el `x:Class` elemento debe incluir el atributo. Cuando se compila la aplicación, la existencia del archivo `x:Class` de marcado hace `partial` que el motor <xref:System.Windows.Window> de compilación de Microsoft (MSBuild) cree una clase que deriva y tiene el nombre especificado por el `x:Class` atributo. Esto requiere la adición de una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] declaración de espacio de nombres XML para el esquema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). La clase `partial` generada implementa `InitializeComponent` el método, que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.  
  
- En el código subyacente, la `partial` clase debe ser una clase `x:Class` con el mismo nombre especificado <xref:System.Windows.Window>por el atributo en el marcado y debe derivar de . Esto permite que el archivo de `partial` código subyacente se asocie a la clase que se genera para el archivo de marcado cuando se compila la aplicación (consulte Creación de [una aplicación WPF](building-a-wpf-application-wpf.md)).  
  
- En el código <xref:System.Windows.Window> subyacente, la clase debe `InitializeComponent` implementar un constructor que llame al método. `InitializeComponent`se implementa mediante la clase generada `partial` del archivo de marcado para registrar eventos y establecer propiedades que se definen en el marcado.  
  
> [!NOTE]
> Cuando se agrega <xref:System.Windows.Window> un nuevo al proyecto <xref:System.Windows.Window> mediante Visual Studio, se implementa mediante el marcado y el código subyacente, e incluye la configuración necesaria para crear la asociación entre el marcado y los archivos de código subyacente como se describe aquí.  
  
 Con esta configuración en su lugar, puede centrarse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en definir la apariencia de la ventana en el marcado e implementar su comportamiento en el código subyacente. En el ejemplo siguiente se muestra una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ventana con un botón, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> implementado en el marcado, y un controlador de eventos para el evento del botón, implementado en el código subyacente.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a>Configuración de una definición de ventana para MSBuild  
 La forma de implementar la ventana determina cómo se configura para MSBuild. Para una ventana que [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se define mediante marcado y código subyacente:  
  
- Los archivos de marcado XAML `Page` se configuran como elementos de MSBuild.  
  
- Los archivos de código subyacente `Compile` se configuran como elementos de MSBuild.  
  
 Esto se muestra en el siguiente archivo de proyecto de MSBuild.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Para obtener información acerca de la creación de aplicaciones WPFWPF, vea [Crear una aplicación WPF](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a>Duración de ventana  
 Como cualquier clase, una ventana tiene una vigencia que comienza cuando se crea una instancia por primera vez, después de lo cual se abre, activa y desactiva y, finalmente, se cierra.  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a>Abrir una ventana  
 Para abrir una ventana, primero hay que crear una instancia de esta, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 En este ejemplo, `MarkupAndCodeBehindWindow` se crea una instancia cuando <xref:System.Windows.Application.Startup> se inicia la aplicación, que se produce cuando se genera el evento.  
  
 Cuando se crea una instancia de una ventana, se agrega automáticamente una <xref:System.Windows.Application> referencia <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>a ella a una lista de ventanas administradas por el objeto (consulte ). Además, la primera ventana que se crea <xref:System.Windows.Application> una instancia se establece, de forma predeterminada, como la ventana principal de la aplicación (consulte <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 La ventana se abre <xref:System.Windows.Window.Show%2A> finalmente llamando al método; el resultado se muestra en la siguiente figura.  
  
 ![Una ventana abierta llamando a Window.Show](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Una ventana que se <xref:System.Windows.Window.Show%2A> abre mediante una llamada es una ventana no parece, lo que significa que la aplicación funciona en un modo que permite a los usuarios activar otras ventanas en la misma aplicación.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>se llama para abrir ventanas como cuadros de diálogo de forma modal. Consulte Información general sobre [cuadros](dialog-boxes-overview.md) de diálogo para obtener más información.  
  
 Cuando <xref:System.Windows.Window.Show%2A> se llama, una ventana realiza el trabajo de inicialización antes de que se muestre para establecer la infraestructura que le permite recibir la entrada del usuario. Cuando se inicializa la <xref:System.Windows.Window.SourceInitialized> ventana, se genera el evento y se muestra la ventana.  
  
 Como método <xref:System.Windows.Application.StartupUri%2A> abreviado, se puede establecer para especificar la primera ventana que se abre automáticamente cuando se inicia una aplicación.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Cuando se inicia la aplicación, la <xref:System.Windows.Application.StartupUri%2A> ventana especificada por el valor de se abre noesamente; internamente, la ventana se <xref:System.Windows.Window.Show%2A> abre llamando a su método.  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a>Propiedad de la ventana  
 Una ventana que se <xref:System.Windows.Window.Show%2A> abre mediante el método no tiene una relación implícita con la ventana que la creó; los usuarios pueden interactuar con cualquiera de las ventanas independientemente de la otra, lo que significa que cualquiera de las ventanas puede hacer lo siguiente:  
  
- Cubra la otra (a menos <xref:System.Windows.Window.Topmost%2A> que una `true`de las ventanas tenga su propiedad establecida en ).  
  
- Minimizarse, maximizarse y restaurarse sin que afecte a las demás.  
  
 Algunas ventanas requieren una relación con la ventana que las abre. Por ejemplo, una aplicación de entorno de desarrollo integrado (IDE) puede abrir ventanas de propiedades y ventanas de herramientas cuyo comportamiento típico es cubrir la ventana que las crea. Además, dichas ventanas se deben siempre cerrar, minimizar, maximizar y restaurar de acuerdo con la ventana que las creó. Tal relación se puede establecer haciendo que una ventana *sea* <xref:System.Windows.Window.Owner%2A> propia otra, y se logra estableciendo la propiedad de la *ventana de propiedad* con una referencia a la ventana *propietaria.* Esto se muestra en el ejemplo siguiente.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Una vez establecida la propiedad:  
  
- La ventana de propiedad puede hacer referencia a <xref:System.Windows.Window.Owner%2A> su ventana propietaria inspeccionando el valor de su propiedad.  
  
- La ventana propietaria puede detectar todas las ventanas que <xref:System.Windows.Window.OwnedWindows%2A> posee inspeccionando el valor de su propiedad.  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a>Prevención de la activación de ventanas  
 Hay escenarios en los que las ventanas no deben activarse cuando se muestran, como las ventanas de conversación de una aplicación de estilo mensajero de Internet o las ventanas de notificación de una aplicación de correo electrónico.  
  
 Si la aplicación tiene una ventana que no se debe <xref:System.Windows.Window.ShowActivated%2A> activar `false` cuando <xref:System.Windows.Window.Show%2A> se muestra, puede establecer su propiedad en antes de llamar al método por primera vez. Como resultado:  
  
- La ventana no está activada.  
  
- No se <xref:System.Windows.Window.Activated> genera el evento de la ventana.  
  
- La ventana actualmente activada permanece activada.  
  
 Sin embargo, la ventana se activará tan pronto como el usuario la active haciendo clic en el área de cliente o en el área distinta del cliente. En este caso:  
  
- La ventana se activa.  
  
- Se genera <xref:System.Windows.Window.Activated> el evento de la ventana.  
  
- La ventana activada previamente se desactiva.  
  
- La ventana <xref:System.Windows.Window.Deactivated> y <xref:System.Windows.Window.Activated> los eventos se generan posteriormente según lo esperado en respuesta a las acciones del usuario.  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a>Activación de ventanas  
 Cuando se abre una ventana por primera vez, se <xref:System.Windows.Window.ShowActivated%2A> convierte `false`en la ventana activa (a menos que se muestre con establecido en ). La *ventana activa* es la ventana que actualmente está capturando la entrada del usuario, como los trazos de teclas y los clics del ratón. Cuando una ventana se activa, <xref:System.Windows.Window.Activated> provoca el evento.  
  
> [!NOTE]
> Cuando se abre una <xref:System.Windows.FrameworkElement.Loaded> ventana <xref:System.Windows.Window.ContentRendered> por primera vez, <xref:System.Windows.Window.Activated> los eventos y se generan solo después de que se genera el evento. Con esto en mente, una ventana <xref:System.Windows.Window.ContentRendered> se puede considerar efectivamente abierta cuando se levanta.  
  
 Después de que se activa una ventana, un usuario puede activar otra ventana de la misma aplicación o activar otra aplicación. Cuando esto sucede, la ventana activa actualmente <xref:System.Windows.Window.Deactivated> se desactiva y provoca el evento. Del mismo modo, cuando el usuario selecciona una ventana desactivada <xref:System.Windows.Window.Activated> actualmente, la ventana se vuelve activa de nuevo y se genera.  
  
 Una razón común <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> para controlar y es habilitar y deshabilitar la funcionalidad que solo se puede ejecutar cuando una ventana está activa. Por ejemplo, algunas ventanas muestran contenido interactivo que requiere la entrada o atención del usuario constante, incluidos los reproductores de vídeo y los juegos. El ejemplo siguiente es un reproductor de <xref:System.Windows.Window.Activated> vídeo <xref:System.Windows.Window.Deactivated> simplificado que muestra cómo controlar e implementar este comportamiento.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Cuando se desactiva una ventana, otros tipos de aplicaciones pueden ejecutar código en segundo plano. Por ejemplo, un cliente de correo puede continuar sondeando el servidor de correo electrónico mientras el usuario está utilizando otras aplicaciones. Las aplicaciones como estas suelen ofrecen un comportamiento diferente o adicional mientras la ventana principal está desactivada. Con respecto al programa de correo electrónico, esto puede significar agregar el nuevo elemento de correo a la bandeja de entrada o agregar un icono de notificación a la bandeja del sistema. Solo es necesario mostrar un icono de notificación cuando la ventana de correo <xref:System.Windows.Window.IsActive%2A> no está activa, lo que se puede determinar inspeccionando la propiedad.  
  
 Si se completa una tarea en segundo plano, es posible <xref:System.Windows.Window.Activate%2A> que una ventana desee notificar al usuario con más urgencia mediante una llamada al método. Si el usuario está interactuando <xref:System.Windows.Window.Activate%2A> con otra aplicación activada cuando se llama, el botón de la barra de tareas de la ventana parpadea. Si un usuario está interactuando <xref:System.Windows.Window.Activate%2A> con la aplicación actual, la llamada llevará la ventana al primer plano.  
  
> [!NOTE]
> Puede controlar la activación <xref:System.Windows.Application.Activated?displayProperty=nameWithType> del <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> ámbito de aplicación mediante los eventos y.  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a>Cerrar una ventana  
 La vigencia de una ventana llega a su fin cuando un usuario la cierra. Se puede cerrar una ventana mediante elementos del área distinta del cliente, entre los que cabe incluir los siguientes:  
  
- El elemento **Cerrar** del menú **Sistema.**  
  
- Presionar ALT+F4.  
  
- Pulse el botón **Cerrar.**  
  
 Puede proporcionar mecanismos adicionales al área cliente para cerrar una ventana. Entre los más habituales se incluyen los siguientes:  
  
- Un elemento **Salir** en el menú **Archivo,** normalmente para las ventanas principales de la aplicación.  
  
- Un **elemento Cerrar** en el menú **Archivo,** normalmente en una ventana de aplicación secundaria.  
  
- Un botón **Cancelar,** normalmente en un cuadro de diálogo modal.  
  
- Un botón **Cerrar,** normalmente en un cuadro de diálogo no basado en un elemento de diálogo.  
  
 Para cerrar una ventana en respuesta a uno de estos <xref:System.Windows.Window.Close%2A> mecanismos personalizados, debe llamar al método. En el ejemplo siguiente se implementa la capacidad de cerrar una ventana eligiendo **el salir** en el **archivo** menú.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Cuando se cierra una ventana, genera <xref:System.Windows.Window.Closing> <xref:System.Windows.Window.Closed>dos eventos: y .  
  
 <xref:System.Windows.Window.Closing>se levanta antes de que se cierre la ventana y proporciona un mecanismo mediante el cual se puede evitar el cierre de la ventana. Una razón común para evitar el cierre de la ventana se produce en caso de que el contenido de la ventana contenga datos modificados. En esta situación, el <xref:System.Windows.Window.Closing> evento se puede controlar para determinar si los datos están sucios y, si es así, para preguntar al usuario si desea continuar cerrando la ventana sin guardar los datos o cancelar el cierre de la ventana. En el ejemplo siguiente se <xref:System.Windows.Window.Closing>muestran los aspectos clave del control .  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 El <xref:System.Windows.Window.Closing> controlador de <xref:System.ComponentModel.CancelEventArgs>eventos se pasa `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> un , `true` que implementa la propiedad que se establece para evitar que una ventana se cierre.  
  
 Si <xref:System.Windows.Window.Closing> no se controla, o se controla pero no se cancela, la ventana se cerrará. Justo antes de que <xref:System.Windows.Window.Closed> se cierre una ventana, se levanta. En este momento, ya no se puede impedir el cierre de la ventana.  
  
> [!NOTE]
> Una aplicación se puede configurar para que se apague automáticamente <xref:System.Windows.Application.MainWindow%2A>cuando se cierra la ventana principal de la aplicación (consulte ) o la última ventana se cierra. Para obtener información detallada, consulte <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Aunque una ventana se puede cerrar explícitamente a través de los mecanismos proporcionados en las áreas no cliente y cliente, una ventana también se puede cerrar implícitamente como resultado del comportamiento en otras partes de la aplicación o Windows, incluidos los siguientes:  
  
- Un usuario cierra la sesión o cierra Windows.  
  
- El propietario de una ventana <xref:System.Windows.Window.Owner%2A>se cierra (consulte ).  
  
- La ventana principal de <xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnMainWindowClose>la aplicación está cerrada y es .  
  
- Se llama a <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
> No se puede volver a abrir una ventana cuando se ha cerrado.  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a>Eventos de vigencia de ventanas  
 En la ilustración siguiente se muestra la secuencia de los eventos principales en la duración de una ventana:  
  
 ![Diagrama que muestra los eventos en la vida útil de una ventana.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 La siguiente ilustración muestra la secuencia de los eventos principales en<xref:System.Windows.Window.ShowActivated%2A> la `false` duración de una ventana que se muestra sin activación (se establece en antes de que se muestre la ventana):  
  
 ![Diagrama que muestra los eventos en la vida útil de una ventana sin activación.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a>Ubicación de la ventana  
 Mientras una ventana está abierta, tiene una ubicación en las dimensiones x e y en relación con el escritorio. Esta ubicación se puede determinar <xref:System.Windows.Window.Left%2A> <xref:System.Windows.Window.Top%2A> inspeccionando las propiedades y, respectivamente. Puede establecer estas propiedades para cambiar la ubicación de la ventana.  
  
 También puede especificar la ubicación <xref:System.Windows.Window> inicial de una <xref:System.Windows.Window.WindowStartupLocation%2A> cuando aparece por <xref:System.Windows.WindowStartupLocation> primera vez estableciendo la propiedad con uno de los siguientes valores de enumeración:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (valor predeterminado)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Si la ubicación de <xref:System.Windows.WindowStartupLocation.Manual>inicio se <xref:System.Windows.Window.Left%2A> <xref:System.Windows.Window.Top%2A> especifica como , <xref:System.Windows.Window> y las propiedades y no se han establecido, pedirá a Windows una ubicación para que aparezca.  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a>Ventanas de nivel superior y orden Z  
 Además de tener una ubicación x e y, una ventana también tiene una ubicación en la dimensión z, que determina su posición vertical con respecto a otras ventanas. Esto se conoce como el orden z de la ventana y hay dos tipos: orden z normal y orden z superior. La ubicación de una ventana en el *orden z normal* viene determinada por si está activa actualmente o no. De forma predeterminada, una ventana se encuentra en el orden z normal. La ubicación de una ventana en el *orden z superior* también está determinada por si está activa actualmente o no. Además, las ventanas del orden z superior siempre se encuentran por encima de aquellas del orden z normal. Una ventana se encuentra en el orden <xref:System.Windows.Window.Topmost%2A> z `true`superior estableciendo su propiedad en .  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 Dentro de cada orden z, la ventana actualmente activa aparece encima de las demás ventanas del mismo orden z.  
  
<a name="WindowSize"></a>
## <a name="window-size"></a>Tamaño de ventana  
 Además de tener una ubicación de escritorio, una ventana tiene un tamaño <xref:System.Windows.Window.SizeToContent%2A>que está determinado por varias propiedades, incluyendo las diversas propiedades de anchura y altura y .  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> y se utilizan para administrar el rango de anchos que una ventana puede tener durante su vida útil y se configuran como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 La altura de <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.Height%2A>la <xref:System.Windows.FrameworkElement.MaxHeight%2A>ventana se administra mediante , , y , y se configuran como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Dado que los distintos valores de anchura y altura especifican cada uno de ellos un intervalo, es posible que la anchura y altura de una ventana de tamaño ajustable se encuentre dentro del intervalo especificado para la dimensión correspondiente. Para detectar su anchura y <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A>altura actuales, inspeccione y , respectivamente.  
  
 Si desea que el ancho y alto de la ventana tenga un tamaño que se ajuste <xref:System.Windows.Window.SizeToContent%2A> al tamaño del contenido de la ventana, puede usar la propiedad, que tiene los siguientes valores:  
  
- <xref:System.Windows.SizeToContent.Manual>. Ningún efecto (valor predeterminado).  
  
- <xref:System.Windows.SizeToContent.Width>. Ajuste al ancho del contenido, que <xref:System.Windows.FrameworkElement.MinWidth%2A> tiene <xref:System.Windows.FrameworkElement.MaxWidth%2A> el mismo efecto que establecer tanto como el ancho del contenido.  
  
- <xref:System.Windows.SizeToContent.Height>. Ajuste a la altura del contenido, <xref:System.Windows.FrameworkElement.MinHeight%2A> que <xref:System.Windows.FrameworkElement.MaxHeight%2A> tiene el mismo efecto que establecer tanto como a la altura del contenido.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Ajuste a la anchura y la altura del <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> contenido, que tiene el mismo <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> efecto que establecer tanto como a la altura del contenido, y establecer ambos y el ancho del contenido.  
  
 En el ejemplo siguiente se muestra una ventana que se redimensiona automáticamente para ajustarse al contenido, tanto vertical como horizontalmente, cuando se muestra por primera vez.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 En el ejemplo siguiente <xref:System.Windows.Window.SizeToContent%2A> se muestra cómo establecer la propiedad en el código para especificar cómo cambia el tamaño de una ventana para que se ajuste a su contenido.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a>Orden de prioridad de las propiedades de tamaño  
 Esencialmente, las diversas propiedades de tamaño de una ventana se combinan para definir el intervalo de anchura y altura de una ventana de tamaño ajustable. Para asegurarse de que <xref:System.Windows.Window> se mantiene un intervalo válido, evalúa los valores de las propiedades de tamaño mediante los siguientes órdenes de prioridad.  
  
 **Para las propiedades de altura:**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Para las propiedades de anchura:**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 El orden de prioridad también puede determinar el tamaño de una ventana <xref:System.Windows.Window.WindowState%2A> cuando se maximiza, que se administra con la propiedad.  
  
<a name="WindowState"></a>
## <a name="window-state"></a>Estado de la ventana  
 Durante la vigencia de una ventana de tamaño ajustable, esta puede tener tres estados: normal, minimizado y maximizado. Una ventana con un estado *normal* es el estado predeterminado de una ventana. Una ventana con este estado permite al usuario moverla y cambiar su tamaño mediante los controles de cambio de tamaño o el borde, si es de tamaño ajustable.  
  
 Una ventana con un estado *minimizado* se <xref:System.Windows.Window.ShowInTaskbar%2A> contrae `true`en su botón de barra de tareas si está establecido en ; de lo contrario, se contrae al tamaño más pequeño posible que puede ser y se reubica en la esquina inferior izquierda del escritorio. Ningún tipo de ventana minimizada puede cambiar de tamaño mediante el borde ni mediante los controles de cambio de tamaño, aunque si no aparece en la barra de tareas se podrá arrastrar a cualquier parte del escritorio.  
  
 Una ventana con un estado *maximizado* se expande al tamaño máximo que <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>puede <xref:System.Windows.Window.SizeToContent%2A> ser, que solo será tan grande como sus . , y las propiedades dictan. Al igual que una ventana minimizada, no puede cambiarse el tamaño de una ventana maximizada mediante un control de cambio de tamaño ni arrastrando el borde.  
  
> [!NOTE]
> Los valores <xref:System.Windows.Window.Top%2A>de <xref:System.Windows.Window.Left%2A> <xref:System.Windows.FrameworkElement.Width%2A>las <xref:System.Windows.FrameworkElement.Height%2A> propiedades , , y de una ventana siempre representan los valores del estado normal, incluso cuando la ventana está actualmente maximizada o minimizada.  
  
 El estado de una ventana se <xref:System.Windows.Window.WindowState%2A> puede configurar estableciendo su <xref:System.Windows.WindowState> propiedad, que puede tener uno de los siguientes valores de enumeración:  
  
- <xref:System.Windows.WindowState.Normal> (valor predeterminado)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 En el ejemplo siguiente se muestra cómo crear una ventana que se muestra como maximizada cuando se abre.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 En general, debe <xref:System.Windows.Window.WindowState%2A> establecer para configurar el estado inicial de una ventana. Cuando aparece una ventana de tamaño ajustable, los usuarios pueden presionar los botones para minimizar, maximizar y restaurar situados en la barra de título de la ventana para cambiar el estado de esta.  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a>Aspecto de la ventana  
 Puede cambiar el aspecto del área cliente de una ventana mediante la adición de contenido específico, como botones, etiquetas y cuadros de texto. Para configurar el área <xref:System.Windows.Window> no cliente, proporciona <xref:System.Windows.Window.Icon%2A> varias propiedades, que incluyen <xref:System.Windows.Window.Title%2A> establecer el icono de una ventana y establecer su título.  
  
 También puede cambiar el aspecto y comportamiento del borde del área distinta del cliente configurando el modo de cambio de tamaño de la ventana, el estilo de esta y si aparece como un botón en la barra de tareas del escritorio.  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a>Modo de cambio de tamaño  
 Dependiendo de <xref:System.Windows.Window.WindowStyle%2A> la propiedad, puede controlar cómo (y si) los usuarios pueden cambiar el tamaño de la ventana. La elección del estilo de ventana afecta a si un usuario puede cambiar el tamaño de la ventana arrastrando su borde con el ratón, si los botones **Minimizar**, **Maximizar**y **Cambiar tamaño** aparecen en el área no cliente y, si aparecen, si están habilitados.  
  
 Puede configurar cómo cambia el tamaño <xref:System.Windows.Window.ResizeMode%2A> de una ventana estableciendo <xref:System.Windows.ResizeMode> su propiedad, que puede ser uno de los siguientes valores de enumeración:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (valor predeterminado)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Al <xref:System.Windows.Window.WindowStyle%2A>igual que con , es poco probable que el modo de cambio de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tamaño de una ventana cambie durante su duración, lo que significa que lo más probable es que lo establezca a partir del marcado.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Tenga en cuenta que puede detectar si una ventana se maximiza, minimiza o restaura inspeccionando la <xref:System.Windows.Window.WindowState%2A> propiedad.  
  
<a name="Window_Style"></a>
### <a name="window-style"></a>Estilo de ventana  
 El borde que se expone desde el área distinta del cliente de una ventana es adecuado para la mayoría de las aplicaciones. Sin embargo, hay circunstancias donde se necesitan tipos diferentes de borde o no se necesita ningún borde en absoluto, dependiendo del tipo de ventana.  
  
 Para controlar qué tipo de borde obtiene <xref:System.Windows.Window.WindowStyle%2A> una ventana, establezca su <xref:System.Windows.WindowStyle> propiedad con uno de los siguientes valores de la enumeración:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (valor predeterminado)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 El efecto de estos estilos de ventana se ilustra en la figura siguiente:  
  
 ![Ilustración de estilos de borde de ventana.](./media/wpf-windows-overview/window-border-styles.png)  
  
 Puede establecer <xref:System.Windows.Window.WindowStyle%2A> mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado o código; porque es poco probable que cambie durante la duración de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] una ventana, lo más probable es que la configure mediante marcado.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Estilo de ventana no rectangular  
 También hay situaciones en <xref:System.Windows.Window.WindowStyle%2A> las que los estilos de borde que le permiten tener no son suficientes. Por ejemplo, es posible que desee crear una aplicación con un borde no rectangular, como usa el Reproductor de Microsoft Windows Media.  
  
 Por ejemplo, considere la ventana de burbuja de voz que se muestra en la siguiente figura:  
  
 ![Una ventana de burbujas de voz que dice Arrastrarme.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Este tipo de ventana se <xref:System.Windows.Window.WindowStyle%2A> puede <xref:System.Windows.WindowStyle.None>crear estableciendo la <xref:System.Windows.Window> propiedad en , y mediante el uso de la compatibilidad especial que tiene para la transparencia.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Esta combinación de valores indica a la ventana que se puede representar de forma totalmente transparente. En este estado, no se pueden usar las opciones del área distinta del cliente de la ventana (el menú Cerrar, los botones para minimizar, maximizar y restaurar, etc.). Por consiguiente, deberá proporcionar las suyas propias.  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a>Presencia de la barra de tareas  

La apariencia predeterminada de una ventana incluye un botón de la barra de tareas, como el que se muestra en la siguiente figura:

 ![Captura de pantalla que muestra una ventana con un botón de la barra de tareas.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Algunos tipos de ventanas no tienen un botón de barra de tareas, como cuadros de mensaje y cuadros de diálogo (consulte Información general de [cuadros](dialog-boxes-overview.md)de diálogo ). Puede controlar si el botón de la barra <xref:System.Windows.Window.ShowInTaskbar%2A> de`true` tareas de una ventana se muestra estableciendo la propiedad (de forma predeterminada).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a>Consideraciones sobre la seguridad  
 <xref:System.Windows.Window>requiere `UnmanagedCode` permiso de seguridad para crear instancias. Para aquellas aplicaciones instaladas e iniciadas desde la máquina local, esto pertenece al conjunto de permisos que se conceden a la aplicación.  
  
 Sin embargo, esto queda fuera del conjunto de permisos concedidos a las aplicaciones que se inician desde Internet o zona de intranet local mediante ClickOnce. Por lo tanto, los usuarios recibirán una advertencia de seguridad ClickOnce y tendrán que elevar el conjunto de permisos para la aplicación a plena confianza.  
  
 Además, los XBAP no pueden mostrar ventanas o cuadros de diálogo de forma predeterminada. Para obtener una explicación sobre las consideraciones de seguridad de aplicaciones independientes, vea Estrategia de [seguridad de WPF - Seguridad](../wpf-security-strategy-platform-security.md)de plataforma .  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a>Otros tipos de ventanas  
 <xref:System.Windows.Navigation.NavigationWindow>es una ventana que está diseñada para alojar contenido navegable. Para obtener más información, vea [Información general sobre la navegación](navigation-overview.md)).  
  
 Los cuadros de diálogo son ventanas que se suelen utilizar para recopilar información de un usuario para completar una función. Por ejemplo, cuando un usuario desea abrir un archivo, una aplicación muestra normalmente el cuadro de diálogo **Abrir archivo** para obtener el nombre de archivo del usuario. Para obtener más información, vea [Información general sobre cuadros de diálogo](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Información general sobre cuadros de diálogo](dialog-boxes-overview.md)
- [Compilar una aplicación WPF](building-a-wpf-application-wpf.md)
