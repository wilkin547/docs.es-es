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
ms.openlocfilehash: 3bc31391d30b0724a480152aa7f1d0dc93380b8c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636411"
---
# <a name="wpf-windows-overview"></a>Información general sobre ventanas de WPF
Los usuarios interactúan con aplicaciones independientes de Windows Presentation Foundation (WPF) a través de Windows. El propósito principal de una ventana es hospedar contenido que permita visualizar datos y que permita a los usuarios interactuar con estos. Las aplicaciones de WPF independientes proporcionan sus propias ventanas mediante el uso de la clase <xref:System.Windows.Window>. En este tema se presentan <xref:System.Windows.Window> antes de tratar los aspectos básicos de la creación y administración de Windows en aplicaciones independientes.  
  
> [!NOTE]
> Las aplicaciones WPF hospedadas en el explorador, incluidas las aplicaciones de explorador XAML (XBAP) y las páginas de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] sueltos, no proporcionan sus propias ventanas. En su lugar, se hospedan en Windows proporcionado por Windows Internet Explorer. Vea [información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Clase de la ventana  
 En la ilustración siguiente se muestran los componentes de una ventana:  
  
 ![Captura de pantalla que muestra los elementos de ventana.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Una ventana se divide en dos áreas: el área distinta del cliente y el área cliente.  
  
 WPF implementa el *área no cliente* de una ventana e incluye las partes de una ventana que son comunes a la mayoría de las ventanas, incluidas las siguientes:  
  
- Un borde.  
  
- Una barra de título.  
  
- Un icono.  
  
- Botones Minimizar, Maximizar y Restaurar.  
  
- Un botón Cerrar.  
  
- Un menú de sistema con elementos de menú que permiten a los usuarios minimizar, maximizar, restaurar, mover, cambiar el tamaño y cerrar una ventana.  
  
 El *área de cliente* de una ventana es el área dentro del área no cliente de una ventana y la usan los desarrolladores para agregar contenido específico de la aplicación, como barras de menús, barras de herramientas y controles.  
  
 En WPF, una ventana se encapsula mediante la clase <xref:System.Windows.Window> que se utiliza para hacer lo siguiente:  
  
- Mostrar una ventana.  
  
- Configurar el tamaño, posición y aspecto de una ventana.  
  
- Hospedar contenido específico de la aplicación.  
  
- Administrar la duración de una ventana.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Implementar una ventana  
 La implementación de una ventana típica incluye el aspecto y el comportamiento, donde la *apariencia* define el aspecto de una ventana para los usuarios y el *comportamiento* define el modo en que una ventana funciona a medida que los usuarios interactúan con ella. En WPF, puede implementar la apariencia y el comportamiento de una ventana mediante código o [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 Sin embargo, en general, la apariencia de una ventana se implementa mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado y su comportamiento se implementa mediante código subyacente, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Para permitir que un archivo de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y el archivo de código subyacente funcionen juntos, se requiere lo siguiente:  
  
- En el marcado, el elemento `Window` debe incluir el atributo `x:Class`. Cuando se compila la aplicación, la existencia de `x:Class` en el archivo de marcado hace que el motor de compilación de Microsoft (MSBuild) cree una `partial` clase que deriva de <xref:System.Windows.Window> y tiene el nombre especificado por el atributo `x:Class`. Esto requiere la adición de una declaración de espacio de nombres XML para el esquema de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`). La clase `partial` generada implementa el método `InitializeComponent`, al que se llama para registrar los eventos y establecer las propiedades que se implementan en el marcado.  
  
- En el código subyacente, la clase debe ser una `partial` clase con el mismo nombre especificado por el atributo `x:Class` en el marcado y debe derivar de <xref:System.Windows.Window>. Esto permite asociar el archivo de código subyacente a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación (consulte [compilar una aplicación WPF](building-a-wpf-application-wpf.md)).  
  
- En el código subyacente, la clase <xref:System.Windows.Window> debe implementar un constructor que llame al método `InitializeComponent`. la clase `partial` generada por el archivo de marcado implementa `InitializeComponent` para registrar eventos y establecer las propiedades que se definen en el marcado.  
  
> [!NOTE]
> Cuando se agrega un nuevo <xref:System.Windows.Window> al proyecto mediante Visual Studio, el <xref:System.Windows.Window> se implementa mediante el marcado y el código subyacente, e incluye la configuración necesaria para crear la asociación entre el marcado y los archivos de código subyacente, como se describe aquí.  
  
 Con esta configuración en su lugar, puede centrarse en definir el aspecto de la ventana en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado e implementar su comportamiento en el código subyacente. En el ejemplo siguiente se muestra una ventana con un botón, implementado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado y un controlador de eventos para el evento de <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón, implementado en el código subyacente.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Configuración de una definición de ventana para MSBuild  
 Cómo se implementa la ventana determina cómo se configura para MSBuild. Para una ventana que se define con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado y código subyacente:  
  
- Los archivos de marcado XAML se configuran como elementos de `Page` de MSBuild.  
  
- Los archivos de código subyacente se configuran como elementos de `Compile` de MSBuild.  
  
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
  
 Para obtener información sobre cómo compilar aplicaciones de WPF, consulte [compilar una aplicación de WPF](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Duración de ventana  
 Como cualquier clase, una ventana tiene una vigencia que comienza cuando se crea una instancia por primera vez, después de lo cual se abre, activa y desactiva y, finalmente, se cierra.  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Abrir una ventana  
 Para abrir una ventana, primero hay que crear una instancia de esta, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 En este ejemplo, se crea una instancia del `MarkupAndCodeBehindWindow` cuando se inicia la aplicación, que se produce cuando se genera el evento <xref:System.Windows.Application.Startup>.  
  
 Cuando se crea una instancia de una ventana, se agrega automáticamente una referencia a la lista de ventanas administrada por el objeto <xref:System.Windows.Application> (vea <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Además, la primera ventana en la que se va a crear una instancia es, de forma predeterminada, establecida por <xref:System.Windows.Application> como la ventana principal de la aplicación (vea <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 La ventana se abre finalmente llamando al método <xref:System.Windows.Window.Show%2A>; el resultado se muestra en la ilustración siguiente.  
  
 ![Ventana abierta mediante una llamada a Window. show](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Una ventana que se abre mediante una llamada a <xref:System.Windows.Window.Show%2A> es una ventana no modal, lo que significa que la aplicación funciona en un modo que permite a los usuarios activar otras ventanas en la misma aplicación.  
  
> [!NOTE]
> se llama a <xref:System.Windows.Window.ShowDialog%2A> para abrir ventanas como cuadros de diálogo de forma modal. Vea [información general sobre cuadros de diálogo](dialog-boxes-overview.md) para obtener más información.  
  
 Cuando se llama a <xref:System.Windows.Window.Show%2A>, una ventana realiza el trabajo de inicialización antes de que se muestre para establecer la infraestructura que le permite recibir datos proporcionados por el usuario. Cuando se inicializa la ventana, se genera el evento <xref:System.Windows.Window.SourceInitialized> y se muestra la ventana.  
  
 Como método abreviado, <xref:System.Windows.Application.StartupUri%2A> se puede establecer para especificar la primera ventana que se abre automáticamente cuando se inicia una aplicación.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Cuando se inicia la aplicación, se abre la ventana especificada por el valor de <xref:System.Windows.Application.StartupUri%2A> forma no modal; internamente, la ventana se abre llamando a su método <xref:System.Windows.Window.Show%2A>.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Propiedad de la ventana  
 Una ventana que se abre mediante el método <xref:System.Windows.Window.Show%2A> no tiene una relación implícita con la ventana que la creó. los usuarios pueden interactuar con cualquier ventana independientemente de la otra, lo que significa que cualquier ventana puede hacer lo siguiente:  
  
- Abarque el otro (a menos que una de las ventanas tenga su propiedad <xref:System.Windows.Window.Topmost%2A> establecida en `true`).  
  
- Minimizarse, maximizarse y restaurarse sin que afecte a las demás.  
  
 Algunas ventanas requieren una relación con la ventana que las abre. Por ejemplo, una aplicación de entorno de desarrollo integrado (IDE) puede abrir ventanas de propiedades y ventanas de herramientas cuyo comportamiento típico es cubrir la ventana que las crea. Además, dichas ventanas se deben siempre cerrar, minimizar, maximizar y restaurar de acuerdo con la ventana que las creó. Este tipo de relación se puede establecer mediante la creación de una ventana *propia* , y se consigue estableciendo la propiedad <xref:System.Windows.Window.Owner%2A> de la *ventana de propiedad* con una referencia a la *ventana propietaria*. Esta implementación se muestra en el ejemplo siguiente.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Una vez establecida la propiedad:  
  
- La ventana propiedad puede hacer referencia a su ventana propietaria mediante la inspección del valor de su propiedad <xref:System.Windows.Window.Owner%2A>.  
  
- La ventana propietaria puede detectar todas las ventanas que posee mediante la inspección del valor de su propiedad <xref:System.Windows.Window.OwnedWindows%2A>.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Prevención de la activación de ventanas  
 Hay escenarios en los que las ventanas no se deben activar cuando se muestran, como las ventanas de conversación de una aplicación de estilo Messenger de Internet o las ventanas de notificación de una aplicación de correo electrónico.  
  
 Si la aplicación tiene una ventana que no se debe activar cuando se muestra, puede establecer su propiedad <xref:System.Windows.Window.ShowActivated%2A> en `false` antes de llamar al método <xref:System.Windows.Window.Show%2A> por primera vez. Como resultado:  
  
- La ventana no está activada.  
  
- El evento <xref:System.Windows.Window.Activated> de la ventana no se genera.  
  
- La ventana actualmente activada permanece activada.  
  
 Sin embargo, la ventana se activará tan pronto como el usuario la active haciendo clic en el área de cliente o en el área distinta del cliente. En ese caso:  
  
- La ventana se activa.  
  
- Se genera el evento <xref:System.Windows.Window.Activated> de la ventana.  
  
- La ventana activada previamente se desactiva.  
  
- Los eventos <xref:System.Windows.Window.Deactivated> y <xref:System.Windows.Window.Activated> de la ventana se generan posteriormente según lo previsto en respuesta a las acciones del usuario.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Activación de ventanas  
 Cuando se abre una ventana por primera vez, se convierte en la ventana activa (a menos que se muestre con <xref:System.Windows.Window.ShowActivated%2A> establecida en `false`). La *ventana activa* es la ventana que está capturando datos proporcionados por el usuario, como pulsaciones de teclas y clics del mouse. Cuando se activa una ventana, se genera el evento <xref:System.Windows.Window.Activated>.  
  
> [!NOTE]
> Cuando se abre una ventana por primera vez, los eventos <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.Window.ContentRendered> se generan solo después de que se genere el evento <xref:System.Windows.Window.Activated>. Teniendo esto en cuenta, una ventana se puede considerar eficazmente abierta cuando se genera <xref:System.Windows.Window.ContentRendered>.  
  
 Después de que se activa una ventana, un usuario puede activar otra ventana de la misma aplicación o activar otra aplicación. Cuando esto sucede, la ventana activa actualmente se desactiva y genera el evento <xref:System.Windows.Window.Deactivated>. Del mismo modo, cuando el usuario selecciona una ventana actualmente desactivada, la ventana vuelve a estar activa y se genera <xref:System.Windows.Window.Activated>.  
  
 Una razón común para controlar <xref:System.Windows.Window.Activated> y <xref:System.Windows.Window.Deactivated> es habilitar y deshabilitar la funcionalidad que solo se puede ejecutar cuando una ventana está activa. Por ejemplo, algunas ventanas muestran contenido interactivo que requiere la entrada o atención del usuario constante, incluidos los reproductores de vídeo y los juegos. El ejemplo siguiente es un reproductor de vídeo simplificado que muestra cómo controlar <xref:System.Windows.Window.Activated> y <xref:System.Windows.Window.Deactivated> para implementar este comportamiento.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Cuando se desactiva una ventana, otros tipos de aplicaciones pueden ejecutar código en segundo plano. Por ejemplo, un cliente de correo puede continuar sondeando el servidor de correo electrónico mientras el usuario está utilizando otras aplicaciones. Las aplicaciones como estas suelen ofrecen un comportamiento diferente o adicional mientras la ventana principal está desactivada. Con respecto al programa de correo electrónico, esto puede significar agregar el nuevo elemento de correo a la bandeja de entrada o agregar un icono de notificación a la bandeja del sistema. Solo es necesario mostrar un icono de notificación cuando la ventana de correo no está activa, lo que se puede determinar mediante la inspección de la propiedad <xref:System.Windows.Window.IsActive%2A>.  
  
 Si una tarea en segundo plano se completa, es posible que una ventana desee notificar al usuario de forma más urgente llamando a <xref:System.Windows.Window.Activate%2A> método. Si el usuario está interactuando con otra aplicación activada cuando se llama a <xref:System.Windows.Window.Activate%2A>, el botón de la barra de tareas de la ventana parpadea. Si un usuario está interactuando con la aplicación actual, al llamar a <xref:System.Windows.Window.Activate%2A> se abrirá la ventana en primer plano.  
  
> [!NOTE]
> Puede controlar la activación del ámbito de la aplicación mediante los eventos <xref:System.Windows.Application.Activated?displayProperty=nameWithType> y <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Cerrar una ventana  
 La vigencia de una ventana llega a su fin cuando un usuario la cierra. Se puede cerrar una ventana mediante elementos del área distinta del cliente, entre los que cabe incluir los siguientes:  
  
- Elemento **cerrar** del menú **del sistema** .  
  
- Presionar ALT+F4.  
  
- Presionar el botón **cerrar** .  
  
 Puede proporcionar mecanismos adicionales al área cliente para cerrar una ventana. Entre los más habituales se incluyen los siguientes:  
  
- Un elemento de **salida** en el menú **archivo** , normalmente para las ventanas de la aplicación principal.  
  
- Un elemento **cerrar** en el menú **archivo** , normalmente en una ventana de la aplicación secundaria.  
  
- Botón **Cancelar** , normalmente en un cuadro de diálogo modal.  
  
- Botón **cerrar** , normalmente en un cuadro de diálogo no modal.  
  
 Para cerrar una ventana en respuesta a uno de estos mecanismos personalizados, debe llamar al método <xref:System.Windows.Window.Close%2A>. En el ejemplo siguiente se implementa la capacidad de cerrar una ventana mediante la elección de la **salida** en el menú **archivo** .  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Cuando se cierra una ventana, genera dos eventos: <xref:System.Windows.Window.Closing> y <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> se genera antes de que se cierre la ventana y proporciona un mecanismo por el que se puede evitar el cierre de la ventana. Una razón común para evitar el cierre de la ventana se produce en caso de que el contenido de la ventana contenga datos modificados. En esta situación, se puede controlar el evento <xref:System.Windows.Window.Closing> para determinar si los datos están sucios y, en caso afirmativo, preguntar al usuario si desea continuar cerrando la ventana sin guardar los datos o cancelar el cierre de la ventana. En el ejemplo siguiente se muestran los aspectos clave de la administración de <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Se pasa al controlador de eventos <xref:System.Windows.Window.Closing> un <xref:System.ComponentModel.CancelEventArgs>, que implementa la `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad que se establece en `true` para evitar que una ventana se cierre.  
  
 Si <xref:System.Windows.Window.Closing> no está controlado, o si se controla pero no se cancela, la ventana se cerrará. Justo antes de que una ventana se cierre realmente, se genera <xref:System.Windows.Window.Closed>. En este momento, ya no se puede impedir el cierre de la ventana.  
  
> [!NOTE]
> Se puede configurar una aplicación para que se cierre automáticamente cuando se cierre la ventana principal de la aplicación (vea <xref:System.Windows.Application.MainWindow%2A>) o se cierre la última ventana. Para obtener información detallada, vea <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Aunque una ventana se puede cerrar explícitamente a través de los mecanismos proporcionados en las áreas cliente y no cliente, una ventana también se puede cerrar implícitamente como resultado de un comportamiento en otras partes de la aplicación o Windows, incluidas las siguientes:  
  
- Un usuario cierra la sesión o apaga Windows.  
  
- El propietario de una ventana se cierra (vea <xref:System.Windows.Window.Owner%2A>).  
  
- La ventana principal de la aplicación está cerrada y <xref:System.Windows.Application.ShutdownMode%2A> está <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
- Se llama a <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
> No se puede volver a abrir una ventana cuando se ha cerrado.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Eventos de vigencia de ventanas  
 En la ilustración siguiente se muestra la secuencia de los eventos principales en la duración de una ventana:  
  
 ![Diagrama que muestra los eventos de la duración de una ventana.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 En la ilustración siguiente se muestra la secuencia de eventos principales en la duración de una ventana que se muestra sin activación (<xref:System.Windows.Window.ShowActivated%2A> se establece en `false` antes de que se muestre la ventana):  
  
 ![Diagrama que muestra los eventos en la duración de una ventana sin activación.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Ubicación de la ventana  
 Mientras una ventana está abierta, tiene una ubicación en las dimensiones x e y en relación con el escritorio. Esta ubicación se puede determinar mediante la inspección de las propiedades <xref:System.Windows.Window.Left%2A> y <xref:System.Windows.Window.Top%2A>, respectivamente. Puede establecer estas propiedades para cambiar la ubicación de la ventana.  
  
 También puede especificar la ubicación inicial de un <xref:System.Windows.Window> cuando aparece por primera vez estableciendo la propiedad <xref:System.Windows.Window.WindowStartupLocation%2A> con uno de los siguientes valores de enumeración <xref:System.Windows.WindowStartupLocation>:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (predeterminado)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Si la ubicación de inicio se especifica como <xref:System.Windows.WindowStartupLocation.Manual>y no se han establecido las propiedades <xref:System.Windows.Window.Left%2A> y <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window> pedirá a Windows una ubicación para que aparezca en.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Ventanas de nivel superior y orden Z  
 Además de tener una ubicación x e y, una ventana también tiene una ubicación en la dimensión z, que determina su posición vertical con respecto a otras ventanas. Esto se conoce como el orden z de la ventana y hay dos tipos: orden z normal y orden z superior. La ubicación de una ventana en el *orden z normal* viene determinada por si está actualmente activa o no. De forma predeterminada, una ventana se encuentra en el orden z normal. La ubicación de una ventana en el *orden z superior* también viene determinada por si está actualmente activa o no. Además, las ventanas del orden z superior siempre se encuentran por encima de aquellas del orden z normal. Una ventana se encuentra en el orden z superior estableciendo su propiedad <xref:System.Windows.Window.Topmost%2A> en `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 Dentro de cada orden z, la ventana actualmente activa aparece encima de las demás ventanas del mismo orden z.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Tamaño de ventana  
 Además de tener una ubicación de escritorio, una ventana tiene un tamaño determinado por varias propiedades, incluidas las diversas propiedades de ancho y alto y <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>y <xref:System.Windows.FrameworkElement.MaxWidth%2A> se utilizan para administrar el intervalo de ancho que puede tener una ventana durante su duración, y se configuran como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>y <xref:System.Windows.FrameworkElement.MaxHeight%2A>administran el alto de la ventana, y se configuran como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Dado que los distintos valores de anchura y altura especifican cada uno de ellos un intervalo, es posible que la anchura y altura de una ventana de tamaño ajustable se encuentre dentro del intervalo especificado para la dimensión correspondiente. Para detectar su ancho y alto actuales, inspeccione <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectivamente.  
  
 Si desea que el ancho y el alto de la ventana tengan un tamaño que se ajuste al tamaño del contenido de la ventana, puede usar la propiedad <xref:System.Windows.Window.SizeToContent%2A>, que tiene los valores siguientes:  
  
- <xref:System.Windows.SizeToContent.Manual>. Ningún efecto (valor predeterminado).  
  
- <xref:System.Windows.SizeToContent.Width>. Ajustar al ancho del contenido, que tiene el mismo efecto que establecer <xref:System.Windows.FrameworkElement.MinWidth%2A> y <xref:System.Windows.FrameworkElement.MaxWidth%2A> en el ancho del contenido.  
  
- <xref:System.Windows.SizeToContent.Height>. Ajustar al alto del contenido, que tiene el mismo efecto que establecer <xref:System.Windows.FrameworkElement.MinHeight%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A> en el alto del contenido.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Ajustar al ancho y alto del contenido, que tiene el mismo efecto que establecer <xref:System.Windows.FrameworkElement.MinHeight%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A> en el alto del contenido, y establecer <xref:System.Windows.FrameworkElement.MinWidth%2A> y <xref:System.Windows.FrameworkElement.MaxWidth%2A> en el ancho del contenido.  
  
 En el ejemplo siguiente se muestra una ventana que se redimensiona automáticamente para ajustarse al contenido, tanto vertical como horizontalmente, cuando se muestra por primera vez.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:System.Windows.Window.SizeToContent%2A> en el código para especificar cómo se cambia el tamaño de una ventana para ajustarse a su contenido.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Orden de prioridad de las propiedades de tamaño  
 Esencialmente, las diversas propiedades de tamaño de una ventana se combinan para definir el intervalo de anchura y altura de una ventana de tamaño ajustable. Para asegurarse de que se mantiene un intervalo válido, <xref:System.Windows.Window> evalúa los valores de las propiedades de tamaño utilizando los siguientes pedidos de precedencia.  
  
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
  
 El orden de prioridad también puede determinar el tamaño de una ventana cuando está maximizada, que se administra con la propiedad <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Estado de la ventana  
 Durante la vigencia de una ventana de tamaño ajustable, esta puede tener tres estados: normal, minimizado y maximizado. Una ventana con un estado *normal* es el estado predeterminado de una ventana. Una ventana con este estado permite al usuario moverla y cambiar su tamaño mediante los controles de cambio de tamaño o el borde, si es de tamaño ajustable.  
  
 Una ventana con un estado *minimizado* se contrae en el botón de la barra de tareas si <xref:System.Windows.Window.ShowInTaskbar%2A> está establecido en `true`; de lo contrario, se contrae hasta el tamaño más pequeño posible y se reubica en la esquina inferior izquierda del escritorio. Ningún tipo de ventana minimizada puede cambiar de tamaño mediante el borde ni mediante los controles de cambio de tamaño, aunque si no aparece en la barra de tareas se podrá arrastrar a cualquier parte del escritorio.  
  
 Una ventana con un estado *maximizado* se expande hasta el tamaño máximo que puede ser, que solo será tan grande como las propiedades <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>y <xref:System.Windows.Window.SizeToContent%2A> determinan. Al igual que una ventana minimizada, no puede cambiarse el tamaño de una ventana maximizada mediante un control de cambio de tamaño ni arrastrando el borde.  
  
> [!NOTE]
> Los valores de las propiedades <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>y <xref:System.Windows.FrameworkElement.Height%2A> de una ventana siempre representan los valores para el estado normal, incluso cuando la ventana está maximizada o minimizada actualmente.  
  
 El estado de una ventana se puede configurar estableciendo su propiedad <xref:System.Windows.Window.WindowState%2A>, que puede tener uno de los siguientes valores de enumeración <xref:System.Windows.WindowState>:  
  
- <xref:System.Windows.WindowState.Normal> (predeterminado)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 En el ejemplo siguiente se muestra cómo crear una ventana que se muestra como maximizada cuando se abre.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 En general, debe establecer <xref:System.Windows.Window.WindowState%2A> para configurar el estado inicial de una ventana. Cuando aparece una ventana de tamaño ajustable, los usuarios pueden presionar los botones para minimizar, maximizar y restaurar situados en la barra de título de la ventana para cambiar el estado de esta.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Aspecto de la ventana  
 Puede cambiar el aspecto del área cliente de una ventana mediante la adición de contenido específico, como botones, etiquetas y cuadros de texto. Para configurar el área no cliente, <xref:System.Windows.Window> proporciona varias propiedades, entre las que se incluyen <xref:System.Windows.Window.Icon%2A> para establecer el icono de una ventana y <xref:System.Windows.Window.Title%2A> para establecer su título.  
  
 También puede cambiar el aspecto y comportamiento del borde del área distinta del cliente configurando el modo de cambio de tamaño de la ventana, el estilo de esta y si aparece como un botón en la barra de tareas del escritorio.  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Modo de cambio de tamaño  
 Dependiendo de la propiedad <xref:System.Windows.Window.WindowStyle%2A>, puede controlar cómo los usuarios (y si) pueden cambiar el tamaño de la ventana. La elección del estilo de ventana afecta a si un usuario puede cambiar el tamaño de la ventana arrastrando el borde con el mouse, si los botones **minimizar**, **maximizar**y **cambiar tamaño** aparecen en el área no cliente y, si aparecen, si están habilitados.  
  
 Puede configurar cómo cambia el tamaño de una ventana estableciendo su <xref:System.Windows.Window.ResizeMode%2A> propiedad, que puede ser uno de los siguientes valores de enumeración de <xref:System.Windows.ResizeMode>:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (predeterminado)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Al igual que con <xref:System.Windows.Window.WindowStyle%2A>, es poco probable que el modo de cambio de tamaño de una ventana cambie durante su duración, lo que significa que probablemente lo establezca desde [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Tenga en cuenta que puede detectar si una ventana está maximizada, minimizada o restaurada mediante la inspección de la propiedad <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Estilo de ventana  
 El borde que se expone desde el área distinta del cliente de una ventana es adecuado para la mayoría de las aplicaciones. Sin embargo, hay circunstancias donde se necesitan tipos diferentes de borde o no se necesita ningún borde en absoluto, dependiendo del tipo de ventana.  
  
 Para controlar qué tipo de borde obtiene una ventana, establezca su propiedad <xref:System.Windows.Window.WindowStyle%2A> con uno de los siguientes valores de la enumeración <xref:System.Windows.WindowStyle>:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (predeterminado)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 El efecto de estos estilos de ventana se muestra en la ilustración siguiente:  
  
 ![Ilustración de los estilos de borde de ventana.](./media/wpf-windows-overview/window-border-styles.png)  
  
 Puede establecer <xref:System.Windows.Window.WindowStyle%2A> mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado o código; Dado que es improbable que cambie durante la vigencia de una ventana, lo más probable es que la configure con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Estilo de ventana no rectangular  
 También hay situaciones en las que los estilos de borde que <xref:System.Windows.Window.WindowStyle%2A> permite tener no son suficientes. Por ejemplo, puede que desee crear una aplicación con un borde no rectangular, como Microsoft Windows Media Player usa.  
  
 Por ejemplo, considere la ventana burbuja de voz que se muestra en la ilustración siguiente:  
  
 ![Una ventana de burbujas de voz que dice arrastrarme.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Este tipo de ventana se puede crear estableciendo la propiedad <xref:System.Windows.Window.WindowStyle%2A> en <xref:System.Windows.WindowStyle.None>y usando compatibilidad especial que <xref:System.Windows.Window> tiene para la transparencia.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Esta combinación de valores indica a la ventana que se puede representar de forma totalmente transparente. En este estado, no se pueden usar las opciones del área distinta del cliente de la ventana (el menú Cerrar, los botones para minimizar, maximizar y restaurar, etc.). Por consiguiente, deberá proporcionar las suyas propias.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Presencia de la barra de tareas  

La apariencia predeterminada de una ventana incluye un botón de la barra de tareas, como el que se muestra en la ilustración siguiente:

 ![Captura de pantalla que muestra una ventana con un botón de la barra de tareas.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Algunos tipos de ventanas no tienen un botón de barra de tareas, como cuadros de mensaje y cuadros de diálogo (consulte [información general sobre cuadros de diálogo](dialog-boxes-overview.md)). Puede controlar si el botón de la barra de tareas de una ventana se muestra estableciendo la propiedad <xref:System.Windows.Window.ShowInTaskbar%2A> (`true` de forma predeterminada).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Consideraciones de seguridad  
 <xref:System.Windows.Window> requiere la creación de instancias de `UnmanagedCode` permiso de seguridad. Para aquellas aplicaciones instaladas e iniciadas desde la máquina local, esto pertenece al conjunto de permisos que se conceden a la aplicación.  
  
 Sin embargo, esto está fuera del conjunto de permisos concedidos a las aplicaciones que se inician desde la zona de Internet o Intranet local mediante ClickOnce. Por lo tanto, los usuarios recibirán una advertencia de seguridad de ClickOnce y deberán elevar el conjunto de permisos para que la aplicación sea de plena confianza.  
  
 Además, las XBAP no pueden mostrar ventanas o cuadros de diálogo de forma predeterminada. Para obtener información sobre las consideraciones de seguridad de aplicaciones independientes, vea [estrategia de seguridad de WPF: seguridad de plataforma](../wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Otros tipos de ventanas  
 <xref:System.Windows.Navigation.NavigationWindow> es una ventana diseñada para hospedar contenido navegable. Para obtener más información, vea [información general sobre navegación](navigation-overview.md)).  
  
 Los cuadros de diálogo son ventanas que se suelen utilizar para recopilar información de un usuario para completar una función. Por ejemplo, cuando un usuario desea abrir un archivo, la aplicación suele mostrar el cuadro de diálogo **Abrir archivo** para obtener el nombre de archivo del usuario. Para obtener más información, vea [Información general sobre cuadros de diálogo](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Información general sobre cuadros de diálogo](dialog-boxes-overview.md)
- [Compilar una aplicación de WPF](building-a-wpf-application-wpf.md)
