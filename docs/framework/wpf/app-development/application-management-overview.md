---
title: "Informaci&#243;n general sobre la administraci&#243;n de aplicaciones | Microsoft Docs"
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
  - "administración de aplicaciones [WPF]"
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
caps.latest.revision: 56
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 52
---
# Informaci&#243;n general sobre la administraci&#243;n de aplicaciones
Todas las aplicaciones suelen compartir un conjunto común de funcionalidad que se aplican a la implementación y la administración de la aplicación.  Este tema proporciona información general sobre la funcionalidad de la clase de <xref:System.Windows.Application> para crear y administrar aplicaciones.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
## Clase Application  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], la funcionalidad común de ámbito de aplicación se encapsula en la clase de <xref:System.Windows.Application> .  la clase de <xref:System.Windows.Application> incluye la funcionalidad siguiente:  
  
-   Realizar el seguimiento e interactuar con la duración de la aplicación.  
  
-   Recuperar y procesar los parámetros de la línea de comandos.  
  
-   Detectar y responder a las excepciones no controladas.  
  
-   Compartir propiedades y recursos del ámbito de la aplicación.  
  
-   Administrar las ventanas en las aplicaciones independientes.  
  
-   Seguimiento y administrar la navegación.  
  
<a name="The_Application_Class"></a>   
## Cómo realizar las tareas comunes Con la clase de aplicación  
 Si no está interesado en todos los detalles de la clase de <xref:System.Windows.Application> , la tabla siguiente muestra algunas de las tareas comunes para <xref:System.Windows.Application> y cómo realizarlas.  Viendo API y los temas relacionados, puede buscar más información y código de ejemplo.  
  
|Tarea|Método|  
|-----------|------------|  
|Obtiene un objeto que representa la aplicación actual|Utilice la propiedad <xref:System.Windows.Application.Current%2A?displayProperty=fullName>.|  
|Agregue una pantalla de inicio a una aplicación|Vea [Agregar una pantalla de presentación a una aplicación WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Iniciar una aplicación|Utilice el método <xref:System.Windows.Application.Run%2A?displayProperty=fullName>.|  
|Detener una aplicación|Utilice el método <xref:System.Windows.Application.Shutdown%2A> del objeto <xref:System.Windows.Application.Current%2A?displayProperty=fullName>.|  
|Obtener los argumentos de la línea de comandos|Controla el evento de <xref:System.Windows.Application.Startup?displayProperty=fullName> y utilice la propiedad de <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=fullName> .  Para obtener un ejemplo, vea el evento de <xref:System.Windows.Application.Startup?displayProperty=fullName> .|  
|Obtiene y establece el código de salida de la aplicación|Establezca la propiedad de <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=fullName> en el controlador de eventos de <xref:System.Windows.Application.Exit?displayProperty=fullName> o llame al método de <xref:System.Windows.Application.Shutdown%2A> y páselo en un entero.|  
|Detectar y responder a las excepciones no controladas|Controle el evento <xref:System.Windows.Application.DispatcherUnhandledException>.|  
|Obtener y establecer recursos de la aplicación|Utilice la propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>.|  
|Utilice un diccionario de recursos del ámbito de aplicación|Vea [Usar un diccionario de recursos en el ámbito de aplicación](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md).|  
|Obtener y establecer las propiedades de la aplicación|Utilice la propiedad <xref:System.Windows.Application.Properties%2A?displayProperty=fullName>.|  
|Recopile y guardar el estado de una aplicación|Vea [Conservar y restaurar propiedades en el ámbito de aplicación a través de sesiones de aplicación](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).|  
|Administrar archivos de datos que no son de código, como los archivos de recursos, los archivos de contenido, y los archivos de sitio de origen.|Vea [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).|  
|Administrar las ventanas en las aplicaciones independientes|Vea [Información general sobre ventanas de WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).|  
|Siga y administrar la navegación|Vea [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## Definición de aplicación  
 Para utilizar la funcionalidad de la clase de <xref:System.Windows.Application> , debe implementar una definición de aplicación.  Una definición de aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es una clase que deriva de <xref:System.Windows.Application> y se configura con un valor de [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] especial.  
  
### Implementar una definición de aplicación  
 Una definición de aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] típica se implementa utilizando tanto marcado como código subyacente.  Esto permite utilizar marcado para establecer mediante declaración propiedades, recursos y eventos de registro de la aplicación, mientras que el control de eventos y la implementación del comportamiento específico de la aplicación se realizan en el código subyacente.  
  
 En el ejemplo siguiente se muestra cómo implementar una definición de aplicación utilizando tanto marcado como código subyacente:  
  
 [!code-xml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Para que un archivo de marcado y un archivo de código subyacente funcionen conjuntamente, debe ocurrir lo siguiente:  
  
-   En el marcado, el elemento `Application` debe incluir el atributo `x:Class`.  Al compilar la aplicación, la existencia de `x:Class` en el archivo de marcado permite que [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] cree una clase `partial` que se derive de <xref:System.Windows.Application> y tenga el nombre especificado por el atributo `x:Class`.  Para ello, es necesario agregar una declaración de espacio de nombres [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] para el esquema [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  
  
-   En el archivo de código subyacente, la clase debe ser una clase `partial` con el mismo nombre que el especificado por el atributo `x:Class` en el marcado, y debe derivarse de <xref:System.Windows.Application>.  Esto permite que el archivo de código subyacente se asocie a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación \(vea [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\).  
  
> [!NOTE]
>  Al crearse un nuevo proyecto de Aplicación WPF o Aplicación de explorador WPF mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], se incluye de forma predeterminada una definición de aplicación, que se define utilizando tanto marcado como código subyacente.  
  
 Este código es el mínimo necesario para implementar una definición de aplicación.  Sin embargo, es necesario realizar una configuración adicional de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] en la definición de aplicación antes de compilar y ejecutar la aplicación.  
  
### Configurar la definición de aplicación para MSBuild  
 Las aplicaciones independientes y [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] requieren la implementación de un cierto nivel de infraestructura para poderse ejecutar.  La parte más importante de esta infraestructura es el punto de entrada.  Cuando un usuario inicia una aplicación, el sistema operativo llama al punto de entrada, que es una función conocida para iniciar las aplicaciones.  
  
 Tradicionalmente, los desarrolladores necesitaban escribir todo o parte de este código, según la tecnología.  Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se encarga de generar este código cuando el archivo de marcado de la definición de aplicación está configurado como un elemento [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`ApplicationDefinition`, tal como se muestra en el siguiente archivo de proyecto de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]:  
  
```  
<Project   
  DefaultTargets="Build"  
  xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 Dado que el archivo de código subyacente contiene código, se marca como un elemento [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Compile`, lo cual es normal.  
  
 La aplicación de estas configuraciones de [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] a los archivos de código subyacente y marcado de una definición de aplicación hace que [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] genere código como el siguiente:  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 El código resultante amplía la definición de aplicación con código de infraestructura adicional, que incluye el método de punto de entrada `Main`.  El atributo <xref:System.STAThreadAttribute> se aplica al método `Main` para indicar que el subproceso principal de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para la aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es un subproceso STA, necesario para las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Cuando se invoca, `Main` crea una nueva instancia de `App` antes de llamar al método `InitializeComponent` para registrar los eventos y establecer las propiedades que se implementan en el marcado.  Dado que se genera `InitializeComponent`, no es necesario llamar explícitamente a `InitializeComponent` desde una definición de aplicación tal y como se hace para las implementaciones de <xref:System.Windows.Controls.Page> y <xref:System.Windows.Window>.  Finalmente, se llama al método <xref:System.Windows.Application.Run%2A> para iniciar la aplicación.  
  
<a name="Getting_the_Current_Application"></a>   
## Obtener la aplicación actual  
 Dado que la funcionalidad de la clase de <xref:System.Windows.Application> se comparten en una aplicación, solo puede haber una instancia de la clase de <xref:System.Windows.Application> por <xref:System.AppDomain>.  Para exigir esto, la clase <xref:System.Windows.Application> se implementa como una clase singleton \(vea [Implementing Singleton in C\#](http://go.microsoft.com/fwlink/?LinkId=100567)\), que crea una única instancia de sí misma y proporciona acceso compartido a ella con la propiedad `static` <xref:System.Windows.Application.Current%2A>.  
  
 En el código siguiente se muestra cómo adquirir una referencia al objeto <xref:System.Windows.Application> para el objeto <xref:System.AppDomain> actual.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> devuelve una referencia a una instancia de la clase <xref:System.Windows.Application>.  Si desea obtener una referencia a la clase derivada de <xref:System.Windows.Application>, debe convertir el valor de la propiedad <xref:System.Windows.Application.Current%2A>, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Puede inspeccionar el valor de <xref:System.Windows.Application.Current%2A> en cualquier punto de la duración de un objeto <xref:System.Windows.Application>.  Sin embargo, se recomienda tener cuidado.  Tras crearse una instancia de la clase <xref:System.Windows.Application>, el estado del objeto <xref:System.Windows.Application> es incoherente durante un período de tiempo.  Durante este período, <xref:System.Windows.Application> realiza las diversas tareas de inicialización necesarias para que se ejecute el código, incluido el establecimiento de la infraestructura de la aplicación, la configuración de las propiedades y el registro de los eventos.  Si intenta utilizar el objeto <xref:System.Windows.Application> durante este período, el código puede generar resultados inesperados, en particular si depende de las diversas propiedades de <xref:System.Windows.Application> que se están estableciendo.  
  
 Cuando <xref:System.Windows.Application> completa sus tareas de inicialización, se inicia realmente su duración.  
  
<a name="Application_Lifetime"></a>   
## Duración de la aplicación  
 La duración de una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] está marcada por varios eventos que <xref:System.Windows.Application> provoca para indicar cuándo se inicia la aplicación, cuándo se activa y se desactiva, y cuándo se cierra.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Splash_Screen"></a>   
### Pantalla de presentación  
 A partir de [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], puede especificar una imagen para usarla en una ventana de inicio o *pantalla de presentación*.  La clase <xref:System.Windows.SplashScreen> facilita el mostrar una ventana de inicio mientras se carga la aplicación.  La ventana <xref:System.Windows.SplashScreen>se crea y muestra antes de que se llame a <xref:System.Windows.Application.Run%2A>.  Para obtener más información, vea [Tiempo de inicio de una aplicación](../../../../docs/framework/wpf/advanced/application-startup-time.md) y [Agregar una pantalla de presentación a una aplicación WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### Iniciar una aplicación  
 Después de llamarse a <xref:System.Windows.Application.Run%2A> e inicializarse la aplicación, esta está lista para ejecutarse.  El evento <xref:System.Windows.Application.Startup> indica este momento:  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 En este punto de la duración de una aplicación, se suele mostrar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Showing_a_User_Interface"></a>   
### Mostrar una interfaz de usuario  
 La mayoría de las aplicaciones independientes para [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] abren un objeto <xref:System.Windows.Window> cuando comienzan a ejecutarse.  El controlador de eventos <xref:System.Windows.Application.Startup> es una de las ubicaciones donde se puede hacer esto, tal como se muestra en el código siguiente.  
  
 [!code-xml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  El primer objeto <xref:System.Windows.Window> del que se va a crear una instancia en una aplicación independiente se convierte de forma predeterminada en la ventana principal de la aplicación.  A este objeto <xref:System.Windows.Window> se hace referencia mediante la propiedad <xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName>.  El valor de la propiedad <xref:System.Windows.Application.MainWindow%2A> se puede cambiar mediante programación si una ventana diferente del primer objeto <xref:System.Windows.Window> del que se creó una instancia debe ser la ventana principal.  
  
 Cuando se inicia por primera vez una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], lo más probable es que navegue a un objeto <xref:System.Windows.Controls.Page>.  Esto se muestra en el código siguiente.  
  
 [!code-xml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Si controla <xref:System.Windows.Application.Startup> para que abra solamente un objeto <xref:System.Windows.Window> o navegue a un objeto <xref:System.Windows.Controls.Page>, podrá establecer el atributo `StartupUri` en el marcado.  
  
 En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Application.StartupUri%2A> desde una aplicación independiente para abrir un objeto <xref:System.Windows.Window>.  
  
 [!code-xml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 En el ejemplo siguiente se muestra cómo utilizar la propiedad <xref:System.Windows.Application.StartupUri%2A> de una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] para navegar a un objeto <xref:System.Windows.Controls.Page>.  
  
 [!code-xml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Este marcado tiene el mismo efecto que el código anterior para abrir una ventana.  
  
> [!NOTE]
>  Para obtener más información sobre la navegación, vea [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Debe controlar el evento <xref:System.Windows.Application.Startup> para que se abra un objeto <xref:System.Windows.Window> si necesita crear instancias del mismo mediante un constructor no predeterminado, o bien, si necesita establecer sus propiedades o suscribirse a sus eventos antes de que se muestre, o bien, si necesita procesar los argumentos de línea de comandos proporcionados al iniciarse la aplicación.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### Procesar argumentos de la línea de comandos  
 En [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)], las aplicaciones independientes pueden iniciarse desde el símbolo del sistema o desde el escritorio.  En ambos casos, es posible pasar argumentos de la línea de comandos a la aplicación. En el ejemplo siguiente se muestra una aplicación que se inicia con un solo argumento de la línea de comandos, "\/StartMinimized":  
  
 `wpfapplication.exe /StartMinimized`  
  
 Durante la inicialización de la aplicación, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] recupera los argumentos de la línea de comandos del sistema operativo y los pasa al controlador de eventos <xref:System.Windows.Application.Startup> a través de la propiedad <xref:System.Windows.StartupEventArgs.Args%2A> del parámetro <xref:System.Windows.StartupEventArgs>.  Puede recuperar y almacenar los argumentos de la línea de comandos utilizando código como el siguiente.  
  
 [!code-xml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 El código controla el evento <xref:System.Windows.Application.Startup> para comprobar si se proporcionó el argumento de la línea de comandos **\/StartMinimized**; en caso afirmativo, abre la ventana principal con el valor de <xref:System.Windows.WindowState> <xref:System.Windows.WindowState>.  Observe que, dado que la propiedad <xref:System.Windows.Window.WindowState%2A> debe establecerse mediante programación, el objeto <xref:System.Windows.Window> principal se debe abrir explícitamente en el código.  
  
 Las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no pueden recuperar ni procesar los argumentos de la línea de comandos porque se inician usando la implementación de [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] \(vea [Implementar una aplicación de WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)\).  Sin embargo, pueden recuperar y procesar los parámetros de las cadenas de consulta de las direcciones URL que se usan para iniciarlas.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### Activación y desactivación de aplicaciones  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] permite a los usuarios cambiar de una aplicación a otra. El método más común es utilizar la combinación de teclas ALT\+TAB.  Solamente se puede cambiar a una aplicación si tiene un objeto <xref:System.Windows.Window> visible que el usuario pueda seleccionar.  El objeto <xref:System.Windows.Window> seleccionado actualmente es la *ventana activa* \(también conocida como *ventana de primer plano*\) y es el objeto <xref:System.Windows.Window> que recibe los datos proporcionados por el usuario. La aplicación con la ventana activa es la *aplicación activa* \(o *aplicación de primer plano*\). Una aplicación se convierte en la aplicación activa en las siguientes circunstancias:  
  
-   Se inicia y muestra un objeto <xref:System.Windows.Window>.  
  
-   Un usuario cambia desde otra aplicación seleccionando un objeto <xref:System.Windows.Window> de la aplicación.  
  
 Para detectar cuándo una aplicación se convierte en la aplicación activa, controle el evento <xref:System.Windows.Application.Activated?displayProperty=fullName>.  
  
 De manera similar, una aplicación puede volverse inactiva en las circunstancias siguientes:  
  
-   Un usuario cambia a otra aplicación desde la actual.  
  
-   Cuando se cierra la aplicación.  
  
 Para detectar cuándo una aplicación se vuelve inactiva, controle el evento <xref:System.Windows.Application.Deactivated?displayProperty=fullName>.  
  
 En el código siguiente se muestra cómo controlar los eventos <xref:System.Windows.Application.Activated> y <xref:System.Windows.Application.Deactivated> para determinar si una aplicación está activa.  
  
 [!code-xml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Un objeto <xref:System.Windows.Window> también se puede activar y desactivar.  Para obtener más información, vea <xref:System.Windows.Window.Activated?displayProperty=fullName> y <xref:System.Windows.Window.Deactivated?displayProperty=fullName>.  
  
> [!NOTE]
>  En el caso de las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], no se provoca el evento <xref:System.Windows.Application.Activated?displayProperty=fullName> ni el evento <xref:System.Windows.Application.Deactivated?displayProperty=fullName>.  
  
<a name="Application_Shutdown"></a>   
### Cierre de la aplicación  
 La duración de una aplicación finaliza cuando se cierra, lo cual puede ocurrir por las razones siguientes:  
  
-   El usuario cierra todos los objetos <xref:System.Windows.Window>.  
  
-   El usuario cierra el objeto <xref:System.Windows.Window> principal.  
  
-   El usuario finaliza la sesión de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] cerrando sesión o apagando.  
  
-   Se ha cumplido una condición específica de la aplicación.  
  
 Para facilitar la administración del cierre de la aplicación, <xref:System.Windows.Application> proporciona el método <xref:System.Windows.Application.Shutdown%2A>, la propiedad <xref:System.Windows.Application.ShutdownMode%2A> y los eventos <xref:System.Windows.Application.SessionEnding> y <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Solamente se puede llamar a <xref:System.Windows.Application.Shutdown%2A> desde aplicaciones que tengan <xref:System.Security.Permissions.UIPermission>.  Las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] independientes siempre tienen este permiso.  Sin embargo, las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] que se ejecutan en el recinto de seguridad de confianza parcial de la zona de Internet no lo tienen.  
  
#### Modo de apagado  
 La mayoría de las aplicaciones se apagan cuando se cierran todas las ventanas o cuando se cierra la ventana principal.  En ocasiones, sin embargo, puede haber otras condiciones específicas de la aplicación que determinen cuándo se cierra la aplicación.  Puede especificar las condiciones en las que se cerrará la aplicación estableciendo la propiedad <xref:System.Windows.Application.ShutdownMode%2A> en uno de los valores siguientes de la enumeración <xref:System.Windows.ShutdownMode>:  
  
-   <xref:System.Windows.ShutdownMode>  
  
-   <xref:System.Windows.ShutdownMode>  
  
-   <xref:System.Windows.ShutdownMode>  
  
 El valor predeterminado de <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode>, lo que significa que una aplicación se cierra automáticamente cuando el usuario cierra la última ventana de la aplicación.  Sin embargo, si la aplicación debe cerrarse cuando se cierre la ventana principal, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] lo hará automáticamente si establece <xref:System.Windows.Application.ShutdownMode%2A> en <xref:System.Windows.ShutdownMode>.  El ejemplo siguiente muestra esta opción.  
  
 [!code-xml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 En el caso de condiciones de cierre específicas de la aplicación, establezca <xref:System.Windows.Application.ShutdownMode%2A> en <xref:System.Windows.ShutdownMode>.  En este caso, es su responsabilidad cerrar la aplicación llamando al método <xref:System.Windows.Application.Shutdown%2A>; de lo contrario, la aplicación seguirá ejecutándose aunque se cierren todas las ventanas.  Observe que se llama implícitamente a <xref:System.Windows.Application.Shutdown%2A> cuando el valor de <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode> u <xref:System.Windows.ShutdownMode>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> se puede establecer desde una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], pero se omite; una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] siempre se cierra cuando se navega fuera de ella en un explorador o cuando se cierra el explorador que hospeda la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
#### Fin de la sesión  
 Las condiciones de apagado que describe la propiedad <xref:System.Windows.Application.ShutdownMode%2A> son específicas de la aplicación.  En algunos casos, sin embargo, es posible que una aplicación se cierre como resultado de una condición externa.  La condición externa más común se produce cuando el usuario finaliza la sesión de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] mediante las acciones siguientes:  
  
-   Cerrar sesión  
  
-   Apagar  
  
-   Reiniciar  
  
-   Hibernar  
  
 Para detectar cuándo finaliza una sesión de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)], puede controlar el evento <xref:System.Windows.Application.SessionEnding>, tal como se muestra en el ejemplo siguiente.  
  
 [!code-xml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 En este ejemplo, el código inspecciona la propiedad <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> para determinar cómo finaliza la sesión de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  Utiliza este valor para mostrar un mensaje de confirmación al usuario.  Si el usuario no desea que la sesión finalice, el código establece <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> en `true` para evitar que finalice la sesión de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
> [!NOTE]
>  No se provoca el evento <xref:System.Windows.Application.SessionEnding> para las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
#### Exit  
 Cuando una aplicación se apaga, es posible que necesite realizar algunos últimos procesos, como conservar el estado de la aplicación.  Para estas situaciones, puede controlar el evento <xref:System.Windows.Application.Exit>.  
  
 [!code-xml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 Para obtener el ejemplo completo, consulte [Conservar y restaurar propiedades en el ámbito de aplicación a través de sesiones de aplicación](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).  
  
 El evento <xref:System.Windows.Application.Exit> puede ser controlado tanto por las aplicaciones independientes como por las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  En el caso de las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], se provoca el evento <xref:System.Windows.Application.Exit> en las circunstancias siguientes:  
  
-   Cuando se navega fuera de una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   En [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], cuando se cierra la ficha en la que se hospeda la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Cuando se cierra el explorador.  
  
#### Código de salida  
 La mayoría de las aplicaciones las inicia el sistema operativo en respuesta a una solicitud del usuario.  Sin embargo, una aplicación puede ser iniciada por otra aplicación para realizar alguna tarea concreta.  Cuando la aplicación iniciada se cierra, es posible que la aplicación que la inició desee conocer la condición en la que se cerró la aplicación iniciada.  En estas situaciones, [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] permite que las aplicaciones devuelvan un código de salida al cerrarse.  De forma predeterminada, las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] devuelven 0 como valor de código de salida.  
  
> [!NOTE]
>  Cuando se depura desde [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], el código de salida de la aplicación se muestra en la **Ventana de salida** cuando se cierra la aplicación, en un mensaje similar al siguiente:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Para abrir la **Ventana de salida**, haga clic en **Resultados** en el menú **Ver**.  
  
 Para cambiar el código de salida, puede llamar a la sobrecarga <xref:System.Windows.Application.Shutdown%28System.Int32%29>, que acepta un argumento de tipo entero como código de salida:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Para detectar el valor del código de salida y cambiarlo, controle el evento <xref:System.Windows.Application.Exit>.  Al controlador de eventos <xref:System.Windows.Application.Exit> se le pasa un objeto <xref:System.Windows.ExitEventArgs> que proporciona acceso al código de salida con la propiedad <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A>.  Para obtener más información, vea <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  El código de salida puede establecerse tanto en las aplicaciones independientes como en las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Sin embargo, el valor del código de salida se omite para las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Unhandled_Exceptions"></a>   
### Excepciones no controladas  
 A veces, puede que una aplicación se cierre en condiciones irregulares, como cuando se produce una excepción imprevista.  En este caso, es posible que la aplicación no tenga el código necesario para detectar y procesar la excepción.  Este tipo de excepción es una excepción no controlada; se muestra una notificación similar a la que aparece en la figura siguiente antes de que se cierre la aplicación.  
  
 ![Notificación de excepción no controlada](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 Desde la perspectiva del usuario, es mejor que una aplicación evite este comportamiento predeterminado realizando todas o alguna de las siguientes acciones:  
  
-   Mostrar información fácil de usar.  
  
-   Intentar mantener la aplicación en funcionamiento.  
  
-   Registrar en el registro de eventos de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] información detallada sobre la excepción que sea fácil de usar para el desarrollador.  
  
 La implementación de esta compatibilidad depende de la capacidad para detectar las excepciones no controladas; el evento <xref:System.Windows.Application.DispatcherUnhandledException> se provoca con esta finalidad.  
  
 [!code-xml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 Al controlador de eventos <xref:System.Windows.Application.DispatcherUnhandledException> se le pasa un parámetro <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> que contiene información contextual referente a la excepción no controlada, incluida la propia excepción \(<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=fullName>\).  Puede utilizar esta información para determinar cómo debe controlar la excepción.  
  
 Cuando controle <xref:System.Windows.Application.DispatcherUnhandledException>, establezca la propiedad <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=fullName> en `true`; de lo contrario, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] seguirá considerando la excepción como no controlada y volverá al comportamiento predeterminado que se ha descrito anteriormente.  Si se produce una excepción no controlada y no se controla el evento <xref:System.Windows.Application.DispatcherUnhandledException>, o bien, se controla el evento y se establece <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> en `false`, la aplicación se cerrará inmediatamente.  Además, no se provocará ningún otro evento de <xref:System.Windows.Application>.  Por consiguiente, deberá controlar <xref:System.Windows.Application.DispatcherUnhandledException> si la aplicación tiene código que deba ejecutarse antes de que se cierre la aplicación.  
  
 Aunque es posible que una aplicación se cierre como resultado de una excepción no controlada, las aplicaciones suelen cerrarse en respuesta a una solicitud del usuario, tal como se explica en la sección siguiente.  
  
<a name="Application_Lifetime_Events"></a>   
### Eventos de duración de la aplicación  
 Las aplicaciones independientes y las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no tienen exactamente la misma duración. En la ilustración siguiente se muestran los eventos clave en la duración de una aplicación independiente y la secuencia en la que se generan.  
  
 ![Aplicación independiente: Eventos de objetos de la aplicación](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview\_ApplicationObjectEvents")  
  
 Igualmente, en la figura siguiente se muestran los eventos clave a lo largo de la duración de una aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] y la secuencia en la que se provocan.  
  
 ![XBAP: Eventos de objetos de la aplicación](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview\_ApplicationObjectEvents\_xbap")  
  
## Vea también  
 <xref:System.Windows.Application>   
 [Información general sobre ventanas de WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)   
 [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md)   
 [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)   
 [Empaquetar URI en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Application Model: How\-to Topics](http://msdn.microsoft.com/es-es/76771b09-3688-4d1c-8818-9b3f4cf39a30)   
 [Desarrollo de aplicaciones](../../../../docs/framework/wpf/app-development/index.md)