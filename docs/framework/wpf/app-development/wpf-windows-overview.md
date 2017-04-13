---
title: "Informaci&#243;n general sobre ventanas de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "aplicaciones, hospedaje"
  - "contenido, mostrar"
  - "contenido, mostrar mediante código de procedimientos"
  - "contenido, mostrar mediante XAML"
  - "crear, ventanas"
  - "cuadros de diálogo"
  - "mostrar contenido"
  - "mostrar contenido mediante código de procedimientos"
  - "mostrar páginas XAML"
  - "eventos"
  - "hospedaje, aplicaciones"
  - "administrar ventanas"
  - "cuadros de diálogo modales"
  - "ventanas modales"
  - "NavigationWindow (objetos)"
  - "Page (objeto)"
  - "código de procedimientos, mostrar contenido mediante"
  - "eventos de ventanas"
  - "administración de ventanas"
  - "Window (objetos)"
  - "ventanas"
  - "XAML (páginas), mostrar"
  - "XAML, mostrar contenido mediante"
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
caps.latest.revision: 65
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 60
---
# Informaci&#243;n general sobre ventanas de WPF
Los usuarios interactúan con las aplicaciones independientes de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] por medio de ventanas.  El propósito principal de una ventana es hospedar contenido que visualiza los datos y permite a los usuarios interactuar con ellos. Las aplicaciones independientes de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporcionan sus propias ventanas mediante la clase <xref:System.Windows.Window>.  En este tema se presenta <xref:System.Windows.Window> antes de tratar los principios de la creación y administración de ventanas en aplicaciones independientes.  
  
> [!NOTE]
>  Las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hospedadas por explorador, incluso las [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] y las páginas [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] separadas, no proporcionan ventanas propias.  En su lugar, se hospedan en ventanas proporcionadas por [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)].  Vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="TheWindowClass"></a>   
## La clase Window  
 La figura siguiente muestra las partes constituyente de una ventana.  
  
 ![Elementos de ventana](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Una ventana está dividida en dos áreas: el área de no cliente y área cliente.  
  
 El *área de no cliente* de una ventana se implementa mediante [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] e incluye las partes de una ventana que son comunes a la mayoría de las ventanas, incluidas las siguientes:  
  
-   Borde.  
  
-   Barra de título.  
  
-   Icono.  
  
-   Botones para minimizar, maximizar y restaurar.  
  
-   Botón Cerrar.  
  
-   Menú Sistema con elementos de menú que permiten a los usuarios minimizar, maximice, restaurar, mover, cambiar de tamaño y cerrar una ventana.  
  
 El *área cliente* de una ventana es el área dentro del área de no cliente de una ventana y es utilizada por los programadores para agregar contenido específico de la aplicación, tal como barras de menús, barras de herramientas y controles.  
  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], las ventanas se encapsulan en la clase <xref:System.Windows.Window>, que se utiliza para hacer lo siguiente:  
  
-   Mostrar una ventana.  
  
-   Configurar el tamaño, posición y aspecto de una ventana.  
  
-   Hospedar contenido específico de la aplicación.  
  
-   Administrar la duración de una ventana.  
  
<a name="DefiningAWindow"></a>   
## Implementar una ventana  
 La implementación de una ventana típica abarca tanto su aspecto como su comportamiento, donde el *aspecto* define la apariencia de la ventana para los usuarios y el *comportamiento* define cómo funciona una ventana cuando los usuarios interactúan con ella.  En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], puede implementar el aspecto y el comportamiento de una ventana utilizando código o marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 En general, sin embargo, el aspecto de una ventana se implementa utilizando el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], y su comportamiento se implementa utilizando código subyacente, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Para permitir que un archivo de marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y un archivo de código subyacente funcionen juntos, se requiere lo siguiente:  
  
-   En el marcado, el elemento `Window` debe incluir el atributo `x:Class`.  Al generar la aplicación, la existencia de `x:Class` en el archivo de marcado permite que [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] cree una clase `partial` que se deriva de <xref:System.Windows.Window>y tenga el nombre especificado por el atributo `x:Class`.  Para ello, es necesario agregar una declaración de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] para el esquema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  La clase `partial` generada implementa el método `InitializeComponent`, al que se llama para registrar los eventos y establecer las propiedades implementadas en el marcado.  
  
-   En el archivo de código subyacente, la clase debe ser una clase `partial` con el mismo nombre que el que especificó el atributo `x:Class` en el marcado, y debe derivarse de <xref:System.Windows.Window>.  Esto permite que el archivo de código subyacente se asocie a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación \(vea [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\).  
  
-   En el archivo de código subyacente, la clase <xref:System.Windows.Window> debe implementar un constructor que llame al método `InitializeComponent`.  La clase `InitializeComponent` se implementa mediante la clase `partial` generada del archivo de marcado para registrar eventos y establecer las propiedades que se definen en el marcado.  
  
> [!NOTE]
>  Al agregar un nuevo objeto <xref:System.Windows.Window> a su proyecto con [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se implementa <xref:System.Windows.Window> utilizando el marcado y el código subyacente; este control incluye la configuración necesaria para crear la asociación entre los archivos de código subyacente y de marcado tal como aquí se describe.  
  
 Con esta configuración activa, puede centrarse en definir el aspecto de la ventana en el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y en implementar su comportamiento en el código subyacente.  En el ejemplo siguiente se muestra una ventana con un botón, implementado en marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y un controlador de eventos para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón, implementado en código subyacente.  
  
 [!code-xml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## Configurar una definición de ventana para MSBuild  
 La forma de implementar la ventana determina cómo se configura para [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].  Para una ventana que se define utilizando tanto marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como código subyacente:  
  
-   Los archivos de marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se configuran como elementos [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page`.  
  
-   Los archivos de código subyacente se configuran como elementos [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Compile`.  
  
 Esto se muestra en el siguiente archivo de proyecto [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].  
  
```  
<Project ... xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Para obtener información sobre la compilación de aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vea [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## Duración de la ventana  
 Como con cualquier clase, una ventana tiene una duración que comienza cuando se crea por primera vez la instancia, después de lo cual se abre, se activa, se desactiva y, finalmente, se cierra.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Opening_a_Window"></a>   
### Abrir una ventana  
 Para abrir una ventana, crea primero una instancia de ella, como se muestra en el ejemplo siguiente.  
  
 [!code-xml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 En este ejemplo, se crea una instancia de `MarkupAndCodeBehindWindow` cuando se inicia la aplicación, lo que ocurre cuando se produce el evento <xref:System.Windows.Application.Startup>.  
  
 Cuando se crea una instancia de una ventana, automáticamente se agrega una referencia a la ventana a la lista de ventanas administrada por el objeto <xref:System.Windows.Application> \(vea <xref:System.Windows.Application.Windows%2A?displayProperty=fullName>\).  Además, <xref:System.Windows.Application> establece la primera ventana de la que se crea una instancia, de forma predeterminada, como la ventana principal de la aplicación \(vea <xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName>\).  
  
 La ventana se abre finalmente llamando al método <xref:System.Windows.Window.Show%2A>; el resultado se muestra en la figura siguiente.  
  
 ![Ventana abierta mediante una llamada a Window.Show](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Una ventana que se abre llamando a <xref:System.Windows.Window.Show%2A> es una ventana no modal, lo que significa que la aplicación funciona en un modo que permite a los usuarios activar otras ventanas en la misma aplicación.  
  
> [!NOTE]
>  Para abrir tales ventanas como cuadros de diálogo, modalmente, se llama a <xref:System.Windows.Window.ShowDialog%2A>.  Vea [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) para obtener más información.  
  
 Cuando se llama a <xref:System.Windows.Window.Show%2A>, una ventana realiza antes de mostrarse un trabajo de inicialización que establece la infraestructura necesaria para recibir la entrada del usuario.  Cuando se inicializa la ventana, se provoca el evento <xref:System.Windows.Window.SourceInitialized> y se muestra la ventana.  
  
 Como método abreviado, se puede establecer <xref:System.Windows.Application.StartupUri%2A> para especificar la primera ventana que se abre automáticamente cuando se inicia una aplicación.  
  
 [!code-xml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Cuando se inicia la aplicación, la ventana especificada por el valor de <xref:System.Windows.Application.StartupUri%2A> se abre de forma no modal; internamente, la ventana se abre llamando a su método <xref:System.Windows.Window.Show%2A>.  
  
<a name="Ownership"></a>   
#### Propiedad de la ventana  
 Una ventana que se abre utilizando el método <xref:System.Windows.Window.Show%2A> no tiene una relación implícita con la ventana que la creó; los usuarios pueden interactuar con cualquier ventana independientemente de las demás, lo que significa que cualquier ventana puede hacer lo siguiente:  
  
-   Cubrir las demás \(a menos que una de las ventanas tenga su propiedad <xref:System.Windows.Window.Topmost%2A> establecida en `true`\).  
  
-   Minimizarse, maximizarse y restaurarse sin afectar a las demás.  
  
 Algunas ventanas requieren una relación con la ventana que las abre.  Por ejemplo, una aplicación [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] puede abrir ventanas de propiedades y ventanas de herramientas cuyo comportamiento típico es cubrir la ventana que las crea.  Además, tales ventanas siempre se deben cerrar, minimizar, maximizar y restaurar de acuerdo con la ventana que las creó.  Este tipo de relación se puede establecer haciendo que una ventana *posea* otra y se logra estableciendo la propiedad <xref:System.Windows.Window.Owner%2A> de la *ventana poseída* con una referencia a la *ventana propietaria*.  El ejemplo siguiente muestra esta opción.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Una vez establecida la propiedad:  
  
-   La ventana poseída puede hacer referencia a su ventana propietaria inspeccionando el valor de su propiedad <xref:System.Windows.Window.Owner%2A>.  
  
-   La ventana propietaria puede detectar todas las ventanas que posee inspeccionando el valor de su propiedad <xref:System.Windows.Window.OwnedWindows%2A>.  
  
<a name="Preventing"></a>   
#### Evitar la activación de ventanas  
 Hay escenarios en que las ventanas no deben activarse al mostrarlas, como las ventanas de conversación de una aplicación de mensajería de Internet o las ventanas de notificación de una aplicación de correo electrónico.  
  
 Si la aplicación tiene una ventana que no debe activarse al mostrarla, puede establecer su propiedad <xref:System.Windows.Window.ShowActivated%2A> en `false` antes de llamar por primera vez al método <xref:System.Windows.Window.Show%2A>.  Como consecuencia:  
  
-   No se activa la ventana.  
  
-   No se provoca el evento <xref:System.Windows.Window.Activated> de la ventana.  
  
-   La ventana que esté activada en ese momento, permanece activada.  
  
 No obstante, la ventana se activará en cuanto el usuario la active haciendo clic en el área cliente o no cliente.  En este caso:  
  
-   Se activa la ventana.  
  
-   Se provoca el evento <xref:System.Windows.Window.Activated> de la ventana.  
  
-   La ventana activada previamente se desactiva.  
  
-   En lo sucesivo, los eventos <xref:System.Windows.Window.Deactivated> y <xref:System.Windows.Window.Activated> de la ventana se provocan como cabe esperar, en respuesta a las acciones del usuario.  
  
<a name="Window_Activation"></a>   
### Activación de la ventana  
 Cuando se abre una ventana por primera vez, pasa a ser la ventana activa \(a menos que se muestre con la propiedad <xref:System.Windows.Window.ShowActivated%2A> establecida en `false`\).  La *ventana activa* es la ventana que está capturando los datos proporcionados por el usuario, tales como la presión de las teclas y los clics del mouse.  Cuando una ventana se activa, provoca el evento <xref:System.Windows.Window.Activated>.  
  
> [!NOTE]
>  Cuando una ventana se abre por primera vez, se producen los eventos <xref:System.Windows.FrameworkElement.Loaded> y <xref:System.Windows.Window.ContentRendered> una vez que se produce el evento <xref:System.Windows.Window.Activated>.  Con esta perspectiva, una ventana puede considerarse abierta cuando se produce <xref:System.Windows.Window.ContentRendered>.  
  
 Una vez que una ventana se activa, un usuario puede activar otra ventana de la misma aplicación o activar otra aplicación.  Cuando ocurre así, la ventana activa actualmente se desactiva y produce el evento <xref:System.Windows.Window.Deactivated>.  Igualmente, cuando el usuario selecciona una ventana actualmente desactivada, la ventana se vuelve a activar y se produce <xref:System.Windows.Window.Activated>.  
  
 Una razón común para administrar <xref:System.Windows.Window.Activated> y <xref:System.Windows.Window.Deactivated> es habilitar y deshabilitar funcionalidad que solamente se puede ejecutar cuando una ventana está activa.  Por ejemplo, algunas ventanas muestran contenido interactivo que requiere constantemente los datos proporcionados por el usuario o su atención, por ejemplo los juegos y los reproductores de vídeo.  El ejemplo siguiente es un reproductor de vídeo simplificado que muestra cómo administrar <xref:System.Windows.Window.Activated> y <xref:System.Windows.Window.Deactivated> para implementar este comportamiento.  
  
 [!code-xml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Otros tipos de aplicación pueden continuar ejecutando código en segundo plano cuando se desactiva una ventana.  Por ejemplo, un cliente de correo puede continuar sondeando el servidor de correo mientras el usuario está utilizando otras aplicaciones.  Aplicaciones como éstas suelen ofrecer un comportamiento diferente o adicional mientras la ventana principal está desactivada.  Con respecto al programa de correo, esto puede significar tanto agregar el nuevo elemento de correo a la bandeja de entrada como agregar un icono de notificación a la bandeja del sistema.  Solamente es necesario mostrar un icono de notificación cuando la ventana de correo no está activa, lo que se puede determinar inspeccionando la propiedad <xref:System.Windows.Window.IsActive%2A>.  
  
 Si se completa una tarea en segundo plano, puede ser preferible que una ventana avise al usuario más urgentemente llamando al método <xref:System.Windows.Window.Activate%2A>.  Si el usuario está interactuando con otra aplicación activada cuando se llama a <xref:System.Windows.Window.Activate%2A>, el botón de la barra de tareas de la ventana parpadea.  Si un usuario está interactuando con la aplicación actual, al llamar a <xref:System.Windows.Window.Activate%2A>, se trae la ventana al primero plano.  
  
> [!NOTE]
>  Puede administrar la activación del ámbito de la aplicación mediante los eventos <xref:System.Windows.Application.Activated?displayProperty=fullName> y <xref:System.Windows.Application.Deactivated?displayProperty=fullName>.  
  
<a name="Closing_a_Window"></a>   
### Cerrar una ventana  
 La duración de una ventana empieza a acabarse cuando un usuario la cierra.  Una ventana se puede cerrar utilizando los elementos del área de no cliente, incluidos los siguientes:  
  
-   El elemento **Cerrar** del menú **Sistema**.  
  
-   Presionar ALT \+ F4.  
  
-   Presionar el botón **Cerrar**.  
  
 Puede proporcionar mecanismos adicionales al área cliente para cerrar una ventana; algunos de los más comunes son los siguientes:  
  
-   Un elemento **Salir** en el menú **Archivo**, normalmente para las ventanas principales de la aplicación.  
  
-   Un elemento **Cerrar** en el menú **Archivo**, normalmente en una ventana secundaria de la aplicación.  
  
-   Un botón **Cancelar**, normalmente en un cuadro de diálogo modal.  
  
-   Un botón **Cerrar**, normalmente en un cuadro de diálogo no modal.  
  
 Para cerrar una ventana en respuesta a uno de estos mecanismos personalizados, debe llamar al método <xref:System.Windows.Window.Close%2A>.  En el ejemplo siguiente se implementa la capacidad de cerrar una ventana eligiendo **Salir** en el menú **Archivo**.  
  
 [!code-xml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Cuando una ventana se cierra, provoca dos eventos: <xref:System.Windows.Window.Closing> y <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> se provoca antes de que la ventana se cierre y proporciona un mecanismo para evitar el cierre de la ventana.  Una razón común para evitar el cierre de la ventana es que el contenido de la ventana contenga datos modificados.  En esta situación, se puede administrar el evento <xref:System.Windows.Window.Closing> para determinar si los datos se han modificado y, en ese caso, preguntar al usuario si desea continuar cerrando la ventana sin guardar los datos o si desea cancelar el cierre de la ventana.  En el ejemplo siguiente se muestran los aspectos clave de la administración de <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind1)]
 [!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind1)]  
[!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind2)]
[!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind2)]  
  
 Al controlador del evento <xref:System.Windows.Window.Closing> se le pasa un objeto <xref:System.ComponentModel.CancelEventArgs>, que implementa la propiedad `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> que se establece en `true` para evitar que una ventana se cierre.  
  
 Si no se administra <xref:System.Windows.Window.Closing>, o se administra pero no se cancela, la ventana se cierra.  El evento <xref:System.Windows.Window.Closed> se produce inmediatamente antes de que una ventana se cierre realmente.  En este punto, no se puede evitar que la ventana se cierre.  
  
> [!NOTE]
>  Una aplicación se puede configurar para que se cierre automáticamente cuando se cierre la ventana de la aplicación principal \(vea <xref:System.Windows.Application.MainWindow%2A>\) o cuando se cierre la última ventana.  Para obtener información detallada, vea <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Aunque una ventana se puede cerrar explícitamente a través de los mecanismos proporcionados en las áreas cliente y no cliente, una ventana también se puede cerrar implícitamente como resultado del comportamiento de otras partes de la aplicación o de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], incluido lo siguiente:  
  
-   Un usuario cierra la sesión o apaga [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
-   Se cierra la ventana propietaria de una ventana \(vea <xref:System.Windows.Window.Owner%2A>\).  
  
-   La ventana principal de la aplicación se cierra y <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode>.  
  
-   Se llama a <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
>  Una ventana no se puede volver a abrir una vez cerrada.  
  
<a name="Window_Lifetime_Events"></a>   
### Eventos de duración de ventana  
 La ilustración siguiente muestra la secuencia de eventos principales en la duración de una ventana.  
  
 ![Duración de ventana](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 En la ilustración siguiente se muestra la secuencia de eventos principales en la duración de una ventana que se muestra sin activarla \(con la propiedad <xref:System.Windows.Window.ShowActivated%2A> establecida en `false` antes de mostrar la ventana\).  
  
 ![Duración de ventana &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## Ubicación de la ventana  
 Mientras una ventana está abierta, tiene una ubicación en las dimensiones x e y respecto al escritorio.  Esta ubicación se puede determinar inspeccionando las propiedades <xref:System.Windows.Window.Left%2A> y <xref:System.Windows.Window.Top%2A>, respectivamente.  Puede establecer estas propiedades para cambiar la ubicación de la ventana.  
  
 También puede especificar la ubicación inicial de un objeto <xref:System.Windows.Window> la primera vez que aparece estableciendo la propiedad <xref:System.Windows.Window.WindowStartupLocation%2A> en uno de los siguientes valores de la enumeración <xref:System.Windows.WindowStartupLocation>:  
  
-   <xref:System.Windows.WindowStartupLocation> \(valor predeterminado\)  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
 Si la ubicación de inicio se especifica como <xref:System.Windows.WindowStartupLocation>, y no se han establecido las propiedades <xref:System.Windows.Window.Left%2A> y <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window> preguntará a [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] dónde debe aparecer.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### Ventanas de nivel superior y orden z  
 Además de tener una ubicación x e y, una ventana tiene también una ubicación en la dimensión z, que determina su posición vertical con respecto a otras ventanas.  Esto se conoce como el orden z de la ventana y hay dos tipos: orden z normal y orden z superior.  La ubicación de una ventana en el *orden z normal* se determina por si está actualmente activa o no.  De forma predeterminada, una ventana se encuentra en el orden z normal.  La ubicación de una ventana en el *orden z superior* también se determina por si está actualmente activa o no.  Además, las ventanas del orden z superior siempre se encuentran por encima de las ventanas del orden z normal.  Una ventana se encuentra en orden z superior estableciendo su propiedad <xref:System.Windows.Window.Topmost%2A> en `true`.  
  
 [!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup2)]  
  
 Dentro de cada orden z, ventana actualmente activa aparece por encima de todas las demás ventanas del mismo orden z.  
  
<a name="WindowSize"></a>   
## Tamaño de la ventana  
 Además de tener una ubicación en el escritorio, una ventana tiene un tamaño determinado por varias propiedades, incluidas las diversas propiedades de alto y ancho, y <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>y <xref:System.Windows.FrameworkElement.MaxWidth%2A> se utilizan para administrar el intervalo de anchos que una ventana puede tener durante su duración y se configuran como se muestra en el ejemplo siguiente.  
  
 [!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup2)]  
  
 El alto de la ventana se administra mediante <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A>, y se configura como se muestra en el ejemplo siguiente.  
  
 [!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup2)]  
  
 Dado que los diversos valores de ancho y alto especifican cada uno un intervalo, es posible que el ancho y alto de una ventana de tamaño variable estén en cualquier punto dentro del intervalo especificado para la dimensión respectiva.  Para detectar su ancho y alto actuales, inspeccione <xref:System.Windows.FrameworkElement.ActualWidth%2A> y <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectivamente.  
  
 Si desea que el ancho y el alto de la ventana tengan un tamaño que se ajuste al tamaño del contenido de la ventana, puede utilizar la propiedad <xref:System.Windows.Window.SizeToContent%2A>, que tiene los valores siguientes:  
  
-   <xref:System.Windows.SizeToContent>.  Ningún efecto \(valor predeterminado\).  
  
-   <xref:System.Windows.SizeToContent>.  Ajustar al ancho del contenido, que tiene el mismo efecto que establecer tanto <xref:System.Windows.FrameworkElement.MinWidth%2A> como <xref:System.Windows.FrameworkElement.MaxWidth%2A> en el ancho del contenido.  
  
-   <xref:System.Windows.SizeToContent>.  Ajustar al alto del contenido, que tiene el mismo efecto que establecer <xref:System.Windows.FrameworkElement.MinHeight%2A> y <xref:System.Windows.FrameworkElement.MaxHeight%2A> en el alto del contenido.  
  
-   <xref:System.Windows.SizeToContent>.  Ajustar al ancho y al alto del contenido, que tiene el mismo efecto que establecer tanto <xref:System.Windows.FrameworkElement.MinHeight%2A> como <xref:System.Windows.FrameworkElement.MaxHeight%2A> en el alto del contenido, y establecer tanto <xref:System.Windows.FrameworkElement.MinWidth%2A> como <xref:System.Windows.FrameworkElement.MaxWidth%2A> en el ancho del contenido.  
  
 El ejemplo siguiente se muestra una ventana cuyo tamaño se ajusta automáticamente a su contenido, tanto vertical como horizontalmente, cuando se muestra por primera vez.  
  
 [!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup2)]  
  
 El ejemplo siguiente muestra cómo establecer la propiedad de <xref:System.Windows.Window.SizeToContent%2A> en código para especificar cómo una ventana ajusta su tamaño para ajustar su contenido.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## Orden de prioridad para las propiedades de tamaño  
 Esencialmente, las diversas propiedades de tamaño de una ventana se combinan para definir el intervalo de ancho y alto para una ventana de tamaño variable.  Para asegurarse de que se mantenga un intervalo válido, <xref:System.Windows.Window> evalúa los valores de las propiedades de tamaño utilizando los órdenes de prioridad siguientes.  
  
 **Para las propiedades de alto:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=fullName>  
  
 **Para las propiedades de ancho:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=fullName>  
  
 El orden de prioridad también puede determinar el tamaño de una ventana cuando se maximiza, lo que se administra con la propiedad <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="WindowState"></a>   
## Estado de la ventana  
 Durante la duración de una ventana de tamaño variable, puede tener tres estados: normal, minimizado y maximizado.  Una ventana con un estado *normal* es el estado predeterminado de una ventana.  Una ventana con este estado permite al usuario moverla y cambiar su tamaño utilizando los controladores de tamaño o el borde, si es de tamaño variable.  
  
 Una ventana con el estado *minimizado* se contrae a su botón de la barra de tareas si <xref:System.Windows.Window.ShowInTaskbar%2A> está establecido en `true`; de lo contrario, se contrae al mínimo tamaño posible y se reubica en la esquina inferior izquierda del escritorio.  Ningún tipo de ventana minimizada puede cambiar su tamaño mediante el borde ni controladores de tamaño, aunque una ventana minimizada que no se muestre en la barra de tareas puede arrastrarse por el escritorio.  
  
 Una ventana con un estado *maximizado* se expande a su tamaño máximo, que solamente puede ser tan grande como dicten sus propiedades <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> y <xref:System.Windows.Window.SizeToContent%2A>.  Como ocurre con una ventana minimizada, no se puede cambiar el tamaño de una ventana maximizada utilizando un controlador de tamaño ni arrastrando el borde.  
  
> [!NOTE]
>  Los valores de las propiedades <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> de una ventana siempre representan los valores del estado normal, incluso cuando la ventana se maximiza o minimiza.  
  
 El estado de una ventana se puede configurar estableciendo su propiedad <xref:System.Windows.Window.WindowState%2A>, que puede tener uno de los siguientes valores de la enumeración <xref:System.Windows.WindowState>:  
  
-   <xref:System.Windows.WindowState> \(valor predeterminado\)  
  
-   <xref:System.Windows.WindowState>  
  
-   <xref:System.Windows.WindowState>  
  
 En el ejemplo siguiente se muestra cómo crear una ventana que se muestra como maximizada al abrirse.  
  
 [!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup2)]  
  
 En general, es recomendable establecer <xref:System.Windows.Window.WindowState%2A> para configurar el estado inicial de una ventana.  Una vez mostrada una ventana de tamaño variable, los usuarios pueden presionar los botones de minimizar, maximizar y restablecer de la barra de título de la ventana para cambiar el estado de la ventana.  
  
<a name="WindowAppearance"></a>   
## Aspecto de la ventana  
 Para cambiar el aspecto del área cliente de una ventana, agréguele contenido específico tal como botones, etiquetas y cuadros de texto.  Para configurar el área no cliente, <xref:System.Windows.Window> proporciona varias propiedades, entre las que se incluye <xref:System.Windows.Window.Icon%2A> para establecer el icono de una ventana y <xref:System.Windows.Window.Title%2A> para establecer su título.  
  
 También puede cambiar el aspecto y comportamiento del borde del área de no cliente configurando el modo de cambio de tamaño de la ventana, su estilo y si aparece como un botón de la barra de tarea del escritorio.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Resize_Mode"></a>   
### Modo de cambio de tamaño  
 En función de la propiedad <xref:System.Windows.Window.WindowStyle%2A>, puede controlar cómo \(y si\) los usuarios pueden cambiar el tamaño de la ventana.  La elección de estilo de ventana determina si un usuario puede cambiar el tamaño de la ventana arrastrando su borde con el mouse, si los botones **Minimizar**, **Maximizar** y **Cambiar tamaño** aparecen en el área de no cliente, y, si aparecen, si están habilitados.  
  
 Puede configurar cómo cambia de tamaño una ventana estableciendo su propiedad <xref:System.Windows.Window.ResizeMode%2A>, que puede ser uno de los siguientes valores de la enumeración <xref:System.Windows.ResizeMode>:  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode> \(valor predeterminado\)  
  
-   <xref:System.Windows.ResizeMode>  
  
 Como ocurre con <xref:System.Windows.Window.WindowStyle%2A>, es improbable que el modo de cambio de tamaño de una ventana cambie durante su duración, los que significa que probablemente se establecerá desde el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup2)]  
  
 Observe que puede detectar si una ventana está maximizada, minimizada o restaurada inspeccionando la propiedad <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="Window_Style"></a>   
### Estilo de ventana  
 El borde que se expone desde el área de no cliente de una ventana es adecuado para la mayoría de las aplicaciones.  Sin embargo, hay circunstancias en las que se necesitan diferentes tipos de borde, o no se necesita ningún borde en absoluto, según el tipo de ventana.  
  
 Para controlar qué tipo de borde obtiene una ventana, establezca su propiedad <xref:System.Windows.Window.WindowStyle%2A> con uno de los siguientes valores de la enumeración <xref:System.Windows.WindowStyle>:  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle> \(valor predeterminado\)  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle>  
  
 El efecto de estos estilos de ventana se muestra en la figura siguiente.  
  
 ![Estilos de ventana](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.png "WindowOverviewFigure6")  
  
 Puede establecer <xref:System.Windows.Window.WindowStyle%2A> mediante marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] o mediante código; dado que es improbable que cambie durante la duración de una ventana, lo más probable es que lo configure utilizando el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup2)]  
  
#### Estilo de ventana no rectangular  
 También hay situaciones en las que los estilos de borde que permite <xref:System.Windows.Window.WindowStyle%2A> no serán suficientes.  Por ejemplo, quizá desee crear una aplicación con un borde no rectangular, como el que utiliza [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)].  
  
 Por ejemplo, considere la ventana de burbuja de voz que se muestra en la figura siguiente.  
  
 ![Ventana no rectangular](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Este tipo de ventana se puede crear estableciendo la propiedad <xref:System.Windows.Window.WindowStyle%2A> en <xref:System.Windows.WindowStyle> y utilizando la compatibilidad especial de <xref:System.Windows.Window> para la transparencia.  
  
 [!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup2)]  
  
 Esta combinación de valores indica a la ventana que debe representarse completamente transparente.  En este estado, las opciones gráficas del área de no cliente de la ventana \(el menú Cerrar, los botones Minimizar, Maximizar y Restaurar, etc.\) no se pueden utilizar.  Por consiguiente, necesita proporcionar opciones propias.  
  
<a name="Task_Bar_Presence"></a>   
### Presencia de la barra de tareas  
 El aspecto predeterminado de una ventana incluye un botón de barra de tareas, como el que se muestra en la figura siguiente.  
  
 ![Ventana con un botón de barra de tareas](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.png "WindowOverviewFigure7")  
  
 Algunos tipos de ventana no tienen botón de barra de tareas, como los cuadros de mensaje y los cuadros de diálogo \(vea [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)\).  Puede controlar si se muestra el botón de barra de tareas para una ventana estableciendo la propiedad <xref:System.Windows.Window.ShowInTaskbar%2A> \(`true` de forma predeterminada\).  
  
 [!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup2)]  
  
<a name="SecurityConsiderations"></a>   
## Consideraciones de seguridad  
 <xref:System.Windows.Window> requiere permiso de seguridad `UnmanagedCode` para crear instancias.  Para las aplicaciones instaladas en el equipo local e iniciadas desde él, esto pertenece al conjunto de permisos que se conceden a la aplicación.  
  
 Sin embargo, esto no pertenece al conjunto de permisos concedido a las aplicaciones que se inician desde la zona de Internet o de Intranet local mediante [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].  Por consiguiente, los usuarios recibirán una advertencia de seguridad [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] y deberán elevar permisos establecido para la aplicación a plena confianza.  
  
 Además, las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no pueden mostrar ventanas ni cuadros de diálogo de forma predeterminada.  Para obtener una explicación sobre las consideraciones de seguridad de las aplicaciones independientes, vea [Estrategia de seguridad de WPF: Seguridad de plataforma](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## Otros tipos de ventanas  
 <xref:System.Windows.Navigation.NavigationWindow> es una ventana diseñada para hospedar contenido navegable.  Para obtener más información, vea [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Los cuadros de diálogo son ventanas que se suelen utilizar para recopilar información de un usuario para completar una función.  Por ejemplo, cuando un usuario desea abrir un archivo, una aplicación muestra normalmente el cuadro de diálogo **Abrir archivo** para obtener el nombre de archivo del usuario.  Para obtener más información, vea [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## Vea también  
 <xref:System.Windows.Window>   
 <xref:System.Windows.MessageBox>   
 <xref:System.Windows.Navigation.NavigationWindow>   
 <xref:System.Windows.Application>   
 [Información general sobre cuadros de diálogo](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)   
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)