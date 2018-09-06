---
title: Información general sobre la administración de aplicaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: ba8d07a26b7e6abc511e5b24db26162b46a2b0a1
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042262"
---
# <a name="application-management-overview"></a>Información general sobre la administración de aplicaciones
Todas las aplicaciones suelen compartir un conjunto común de funciones que se aplica a la implementación y la administración de la aplicación. Este tema proporciona información general de la funcionalidad de la <xref:System.Windows.Application> clase para crear y administrar aplicaciones.  
   
  
## <a name="the-application-class"></a>La clase Application  
 En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], se encapsula la funcionalidad común de ámbito de la aplicación en el <xref:System.Windows.Application> clase. La <xref:System.Windows.Application> clase incluye la funcionalidad siguiente:  
  
-   Realizar el seguimiento e interactuar con la duración de la aplicación.  
  
-   Recuperar y procesar los parámetros de la línea de comandos.  
  
-   Detectar y responder a las excepciones no controladas.  
  
-   Compartir propiedades y recursos en el ámbito de aplicación.  
  
-   Administrar ventanas en las aplicaciones independientes.  
  
-   Seguimiento y administración de la navegación.  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Cómo realizar las tareas comunes con la clase Application  
 Si no está interesado en todos los detalles de la <xref:System.Windows.Application> (clase), en la tabla siguiente se enumera algunas de las tareas comunes para <xref:System.Windows.Application> y cómo realizarlas. Viendo las API y los temas relacionados, puede buscar más información y código de ejemplo.  
  
|Tarea|Método|  
|----------|--------------|  
|Obtener un objeto que representa la aplicación actual|Utilice la propiedad <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|  
|Agregar una pantalla de inicio a una aplicación|Consulte [agregar una pantalla de presentación a una aplicación WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Iniciar una aplicación|Utilice el método <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|  
|Detener una aplicación|Use la <xref:System.Windows.Application.Shutdown%2A> método de la <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> objeto.|  
|Obtener los argumentos de la línea de comandos|Controlar la <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento y utilice la <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> propiedad. Para obtener un ejemplo, vea el <xref:System.Windows.Application.Startup?displayProperty=nameWithType> eventos.|  
|Obtener y establecer el código de salida de la aplicación|Establecer el <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> propiedad en el <xref:System.Windows.Application.Exit?displayProperty=nameWithType> controlador de eventos o llamada la <xref:System.Windows.Application.Shutdown%2A> método y pasar un entero.|  
|Detectar y responder a las excepciones no controladas|Controlar la <xref:System.Windows.Application.DispatcherUnhandledException> eventos.|  
|Obtener y establecer recursos en el ámbito de aplicación|Utilice la propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|  
|Usar un diccionario de recursos en el ámbito de aplicación|Consulte [usar un diccionario de recursos en el ámbito de aplicación](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md).|  
|Obtener y establecer propiedades en el ámbito de aplicación|Utilice la propiedad <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|  
|Obtener y guardar el estado de una aplicación|Consulte [conservar y restaurar propiedades en el ámbito de la aplicación a través de sesiones de la aplicación](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).|  
|Administrar archivos de datos que no son de código, incluidos los archivos de recursos, los archivos de contenido y los archivos de sitio de origen.|Consulte [WPF Application Resource, contenido y los archivos de datos](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).|  
|Administrar ventanas en las aplicaciones independientes|Vea [WPF Windows Overview](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md) (Introducción a Windows Presentation Foundation).|  
|Realizar un seguimiento y administrar la navegación|Consulte [información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>La definición de aplicación  
 Para utilizar la funcionalidad de la <xref:System.Windows.Application> (clase), debe implementar una definición de aplicación. Un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] definición de aplicación es una clase que derive de <xref:System.Windows.Application> y está configurado con un especial [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] configuración.  
  
### <a name="implementing-an-application-definition"></a>Implementar una definición de aplicación  
 Una típica [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] definición de la aplicación se implementa usando tanto marcado como código subyacente. Esto le permite usar marcado para establecer mediante declaración propiedades, recursos y eventos de registro de la aplicación, mientras que el control de eventos y la implementación del comportamiento específico de la aplicación se realizan en el código subyacente.  
  
 En el ejemplo siguiente se muestra cómo implementar una definición de aplicación usando tanto marcado como código subyacente:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Para que un archivo de marcado y un archivo de código subyacente funcionen conjuntamente, debe ocurrir lo siguiente:  
  
-   En el marcado, el `Application` elemento debe incluir el `x:Class` atributo. Cuando se compila la aplicación, la existencia de `x:Class` en el marcado hace que el archivo [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] para crear un `partial` clase que derive de <xref:System.Windows.Application> y tiene el nombre especificado por el `x:Class` atributo. Esto requiere la adición de un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] declaración de espacio de nombres para el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esquema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).  
  
-   En el código subyacente, la clase debe ser un `partial` clase con el mismo nombre que se especifica mediante el `x:Class` de atributo en el marcado y debe derivar de <xref:System.Windows.Application>. Esto permite que el archivo de código subyacente se asocie a la `partial` clase que se genera para el archivo de marcado cuando se compila la aplicación (consulte [compilar una aplicación WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  Cuando se crea un nuevo proyecto de aplicación WPF o el proyecto de aplicación de explorador WPF mediante [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], una definición de aplicación se incluye de forma predeterminada y se define usando tanto marcado como código subyacente.  
  
 Este código es el mínimo necesario para implementar una definición de aplicación. Sin embargo, otros [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] configuración debe realizarse en la definición de aplicación antes de compilar y ejecutar la aplicación.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Configurar la definición de aplicación para MSBuild  
 Las aplicaciones independientes y [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] requieren la implementación de un cierto nivel de infraestructura para poderse ejecutar. La parte más importante de esta infraestructura es el punto de entrada. Cuando un usuario inicia una aplicación, el sistema operativo llama al punto de entrada, que es una función conocida para iniciar las aplicaciones.  
  
 Tradicionalmente, los desarrolladores necesitaban escribir todo o parte de este código, según la tecnología. Sin embargo, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] este código se genera automáticamente cuando el archivo de marcado de la definición de aplicación se configura como un [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` de elemento, como se muestra en la siguiente [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] archivo de proyecto:  
  
```xml  
<Project   
  DefaultTargets="Build"  
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 Dado que el archivo de código subyacente contiene código, se marca como un [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` de elemento, lo cual es normal.  
  
 La aplicación de estas [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] hace que las configuraciones a los archivos de marcado y código subyacente de una definición de aplicación [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] para generar código similar al siguiente:  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 El código resultante amplía la definición de aplicación con código de infraestructura adicional, que incluye el método de punto de entrada `Main`. El <xref:System.STAThreadAttribute> atributo se aplica a la `Main` método para indicar que el principal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del subproceso para el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación es un subproceso STA, que es necesario para [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones. Cuando se llama, `Main` crea una nueva instancia de `App` antes de llamar a la `InitializeComponent` método para registrar los eventos y establecer las propiedades que se implementan en el marcado. Dado que `InitializeComponent` se genera automáticamente, no es necesario llamar explícitamente a `InitializeComponent` desde una definición de aplicación como haría para hacer <xref:System.Windows.Controls.Page> y <xref:System.Windows.Window> implementaciones. Por último, el <xref:System.Windows.Application.Run%2A> método se llama para iniciar la aplicación.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Obtener la aplicación actual  
 Dado que la funcionalidad de la <xref:System.Windows.Application> clase se comparten entre una aplicación, puede haber solo una instancia de la <xref:System.Windows.Application> clase por <xref:System.AppDomain>. Para exigir esto, el <xref:System.Windows.Application> clase se implementa como una clase singleton (vea [Implementing Singleton in C#](https://go.microsoft.com/fwlink/?LinkId=100567)), que crea una única instancia de sí mismo y proporciona acceso comparten a ella con el `static` <xref:System.Windows.Application.Current%2A> propiedad.  
  
 El código siguiente muestra cómo adquirir una referencia a la <xref:System.Windows.Application> objeto actual <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> Devuelve una referencia a una instancia de la <xref:System.Windows.Application> clase. Si desea obtener una referencia a su <xref:System.Windows.Application> derivados de la clase primero debe convertir el valor de la <xref:System.Windows.Application.Current%2A> propiedad, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Puede inspeccionar el valor de <xref:System.Windows.Application.Current%2A> en cualquier momento de la duración de un <xref:System.Windows.Application> objeto. En cambio, se recomienda tener cuidado. Después de la <xref:System.Windows.Application> se crea una instancia de clase, hay un período durante el cual el estado de la <xref:System.Windows.Application> objeto es incoherente. Durante este período, <xref:System.Windows.Application> está realizando las diversas tareas de inicialización que requieren el código para ejecutar, incluido el establecimiento de la infraestructura de aplicación, establecer las propiedades y registrar los eventos. Si intenta usar el <xref:System.Windows.Application> objeto durante este período, el código puede tener resultados inesperados, particularmente si depende de los distintos <xref:System.Windows.Application> propiedades que se va a establecer.  
  
 Cuando <xref:System.Windows.Application> completa su trabajo de inicialización, se inicia realmente su duración.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Duración de la aplicación  
 La duración de un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación está marcada por varios eventos generados por <xref:System.Windows.Application> para que sepa cuándo se ha iniciado la aplicación, se ha activado y desactivado y se ha cerrado.  
  
  
<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Pantalla de presentación  
 A partir de la [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], puede especificar una imagen que se usará en una ventana de inicio o *pantalla de presentación*. La <xref:System.Windows.SplashScreen> clase facilita la tarea mostrar una ventana de inicio mientras se carga la aplicación. El <xref:System.Windows.SplashScreen> se crea y se muestra antes de ventana <xref:System.Windows.Application.Run%2A> se llama. Para obtener más información, consulte [Application Startup Time](../../../../docs/framework/wpf/advanced/application-startup-time.md) y [agregar una pantalla de presentación a una aplicación WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Iniciar una aplicación  
 Después de <xref:System.Windows.Application.Run%2A> se denomina y se inicializa la aplicación, está lista para ejecutar la aplicación. En este momento se especifica cuando la <xref:System.Windows.Application.Startup> provoca el evento:  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 En este momento de la duración de la aplicación, lo más común es mostrar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Showing_a_User_Interface"></a>   
### <a name="showing-a-user-interface"></a>Mostrar una interfaz de usuario  
 Abre la mayoría de las aplicaciones Windows independiente una <xref:System.Windows.Window> cuando empieza a ejecutar. El <xref:System.Windows.Application.Startup> controlador de eventos es una ubicación desde la que puede hacer esto, como se muestra en el código siguiente.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  La primera <xref:System.Windows.Window> para ejecutarse en una independiente aplicación se convierte en la ventana principal de la aplicación de forma predeterminada. Esto <xref:System.Windows.Window> objeto hace referencia el <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> propiedad. El valor de la <xref:System.Windows.Application.MainWindow%2A> propiedad se puede cambiar mediante programación si una ventana diferente que el primero crea una instancia de <xref:System.Windows.Window> debe ser la ventana principal.  
  
 Cuando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] inicia primero, lo más probable es que se le remitirá a un <xref:System.Windows.Controls.Page>. Esto se muestra en el código siguiente.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Si controla <xref:System.Windows.Application.Startup> sólo abran un <xref:System.Windows.Window> o navegue hasta un <xref:System.Windows.Controls.Page>, puede establecer el `StartupUri` atributo en el marcado en su lugar.  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Application.StartupUri%2A> desde una aplicación independiente para abrir un <xref:System.Windows.Window>.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 El ejemplo siguiente muestra cómo usar <xref:System.Windows.Application.StartupUri%2A> desde un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] para navegar a un <xref:System.Windows.Controls.Page>.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Este marcado tiene el mismo efecto que el código anterior para abrir una ventana.  
  
> [!NOTE]
>  Para obtener más información sobre la navegación, consulte [información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Tiene que controlar la <xref:System.Windows.Application.Startup> eventos para abrir un <xref:System.Windows.Window> si necesita crear una instancia mediante un constructor no predeterminado, o deberá establecer sus propiedades o suscribirse a sus eventos antes de mostrarlo o necesita procesar los argumentos de línea de comandos que se han proporcionado cuando se inicia la aplicación.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Procesar argumentos de la línea de comandos  
 En Windows, las aplicaciones independientes pueden iniciarse desde un símbolo del sistema o el escritorio. En ambos casos, es posible pasar argumentos de la línea de comandos a la aplicación. En el ejemplo siguiente se muestra una aplicación que se inicia con un solo argumento de la línea de comandos, "/StartMinimized":  
  
 `wpfapplication.exe /StartMinimized`  
  
 Durante la inicialización de la aplicación, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] recupera los argumentos de línea de comandos desde el sistema operativo y los pasa a la <xref:System.Windows.Application.Startup> controlador de eventos a través de la <xref:System.Windows.StartupEventArgs.Args%2A> propiedad de la <xref:System.Windows.StartupEventArgs> parámetro. Puede recuperar y almacenar los argumentos de la línea de comandos usando código como el siguiente.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 El código controla <xref:System.Windows.Application.Startup> para comprobar si el **/StartMinimized** se ha proporcionado un argumento de línea de comandos; si es así, se abre la ventana principal con un <xref:System.Windows.WindowState> de <xref:System.Windows.WindowState.Minimized>. Tenga en cuenta que dado que la <xref:System.Windows.Window.WindowState%2A> propiedad debe establecerse mediante programación, el método main <xref:System.Windows.Window> debe abrirse explícitamente en el código.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no se puede recuperar y procesar los argumentos de línea de comandos porque se inician mediante [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] implementación (consulte [implementar una aplicación WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)). En cambio, pueden recuperar y procesar los parámetros de las cadenas de consulta de las direcciones URL que se usan para iniciarlas.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Activación y desactivación de aplicaciones  
 Windows permite a los usuarios cambiar entre las aplicaciones. El método más común es usar la combinación de teclas ALT+TAB. Una aplicación solo se puede cambiar a si tiene un visible <xref:System.Windows.Window> que un usuario puede seleccionar. Actualmente seleccionado <xref:System.Windows.Window> es el *ventana activa* (también conocido como el *ventana de primer plano*) y es el <xref:System.Windows.Window> que recibe la entrada del usuario. La aplicación con la ventana activa es la *aplicación activa* (o *aplicación en primer plano*). Una aplicación se convierte en la aplicación activa en las siguientes circunstancias:  
  
-   Se inicia y muestra un <xref:System.Windows.Window>.  
  
-   Un usuario cambia desde otra aplicación seleccionando un <xref:System.Windows.Window> en la aplicación.  
  
 Puede detectar cuando se activa una aplicación controlando el <xref:System.Windows.Application.Activated?displayProperty=nameWithType> eventos.  
  
 De manera similar, una aplicación puede volverse inactiva en las circunstancias siguientes:  
  
-   Un usuario cambia a otra aplicación desde la actual.  
  
-   Cuando se cierra la aplicación.  
  
 Puede detectar cuando una aplicación pasa a estar inactiva controlando el <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> eventos.  
  
 El código siguiente muestra cómo controlar el <xref:System.Windows.Application.Activated> y <xref:System.Windows.Application.Deactivated> eventos para determinar si una aplicación está activa.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Un <xref:System.Windows.Window> también se puede activar y desactivar. Para obtener más información, vea <xref:System.Windows.Window.Activated?displayProperty=nameWithType> y <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Ni <xref:System.Windows.Application.Activated?displayProperty=nameWithType> ni <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> se desencadena para [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Cierre de la aplicación  
 La duración de una aplicación finaliza cuando se cierra, lo cual puede ocurrir por las razones siguientes:  
  
-   Un usuario cierra cada <xref:System.Windows.Window>.  
  
-   Un usuario cierra el principal <xref:System.Windows.Window>.  
  
-   Un usuario finaliza la sesión de Windows cerrando sesión o cerrando.  
  
-   Se ha cumplido una condición específica de la aplicación.  
  
 Para ayudarle a administrar el cierre de la aplicación, <xref:System.Windows.Application> proporciona el <xref:System.Windows.Application.Shutdown%2A> método, el <xref:System.Windows.Application.ShutdownMode%2A> propiedad y el <xref:System.Windows.Application.SessionEnding> y <xref:System.Windows.Application.Exit> eventos.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A> solo se puede llamar desde las aplicaciones que tienen <xref:System.Security.Permissions.UIPermission>. Independiente [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones siempre tienen este permiso. Sin embargo, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] que se ejecuta en el recinto de seguridad de confianza parcial de la zona de Internet no lo hacen.  
  
#### <a name="shutdown-mode"></a>Modo de apagado  
 La mayoría de las aplicaciones se apagan cuando se cierran todas las ventanas o cuando se cierra la ventana principal. En ocasiones, en cambio, puede haber otras condiciones específicas de la aplicación que determinen cuándo se cierra la aplicación. Puede especificar las condiciones en las que se cerrará la aplicación estableciendo <xref:System.Windows.Application.ShutdownMode%2A> con uno de los siguientes <xref:System.Windows.ShutdownMode> valores de enumeración:  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 El valor predeterminado de <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode.OnLastWindowClose>, lo que significa que una aplicación se cierra automáticamente cuando el usuario cierra la última ventana de la aplicación. Sin embargo, si se debe cerrar la aplicación cuando se cierra la ventana principal, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] lo hará automáticamente si establece <xref:System.Windows.Application.ShutdownMode%2A> a <xref:System.Windows.ShutdownMode.OnMainWindowClose>. Esta implementación se muestra en el ejemplo siguiente.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Cuando tiene condiciones de cierre específicas de la aplicación, establezca <xref:System.Windows.Application.ShutdownMode%2A> a <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. En este caso, es su responsabilidad cerrar la aplicación llamando explícitamente la <xref:System.Windows.Application.Shutdown%2A> método; en caso contrario, la aplicación seguirá ejecutándose aunque se cierran todas las ventanas. Tenga en cuenta que <xref:System.Windows.Application.Shutdown%2A> se llama implícitamente cuando el <xref:System.Windows.Application.ShutdownMode%2A> sea <xref:System.Windows.ShutdownMode.OnLastWindowClose> o <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> se puede establecer desde un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], pero se omite; una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] siempre está apagada cuando se navega fuera de ella en un explorador o cuando el explorador que hospeda el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] está cerrado. Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
#### <a name="session-ending"></a>Fin de la sesión  
 Las condiciones de apagado que describen el <xref:System.Windows.Application.ShutdownMode%2A> propiedad son específicos de una aplicación. En algunos casos, en cambio, es posible que una aplicación se cierre como resultado de una condición externa. La condición externa más común se produce cuando un usuario finaliza la sesión de Windows mediante las siguientes acciones:  
  
-   Cerrar sesión  
  
-   Apagar  
  
-   Reiniciar  
  
-   Hibernar  
  
 Para detectar cuándo finaliza una sesión de Windows, puede controlar la <xref:System.Windows.Application.SessionEnding> eventos, como se muestra en el ejemplo siguiente.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 En este ejemplo, el código inspecciona el <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> propiedad para determinar la forma en que finaliza la sesión de Windows. Usa este valor para mostrar un mensaje de confirmación al usuario. Si el usuario no desea que la sesión finalice, el código establece <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> a `true` para evitar que la sesión de Windows final.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding> no se desencadena para [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
#### <a name="exit"></a>Salir  
 Cuando una aplicación se apaga, es posible que necesite realizar algunos últimos procesos, como conservar el estado de la aplicación. Para estas situaciones, puede controlar la <xref:System.Windows.Application.Exit> eventos.  
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 Para obtener un ejemplo completo, vea [conservar y restaurar las propiedades de ámbito de la aplicación a través de sesiones de aplicación](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit> se pueden controlar aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Para [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], <xref:System.Windows.Application.Exit> se produce cuando se encuentra en las siguientes circunstancias:  
  
-   Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se navega fuera de ella.  
  
-   En [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], cuando la pestaña que hospeda el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] está cerrado.  
  
-   Cuando se cierra el explorador.  
  
#### <a name="exit-code"></a>Código de salida  
 La mayoría de las aplicaciones las inicia el sistema operativo en respuesta a una solicitud del usuario. En cambio, una aplicación puede ser iniciada por otra aplicación para realizar alguna tarea concreta. Cuando la aplicación iniciada se cierra, es posible que la aplicación que la ha iniciado quiera conocer la condición en la que se cerró la aplicación iniciada. En estas situaciones, Windows permite que las aplicaciones devolver un código de salida de la aplicación en el apagado. De forma predeterminada, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones devuelven un valor de código de salida de 0.  
  
> [!NOTE]
>  Cuando se depura desde [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], el código de salida de la aplicación se muestra en el **salida** ventana cuando se cierra la aplicación, en un mensaje similar a lo siguiente:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Abre el **salida** ventana haciendo **salida** en el **vista** menú.  
  
 Para cambiar el código de salida, puede llamar a la <xref:System.Windows.Application.Shutdown%28System.Int32%29> sobrecarga, que acepta un argumento entero sea el código de salida:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Puede detectar el valor del código de salida y cambiarlo, controlando la <xref:System.Windows.Application.Exit> eventos. El <xref:System.Windows.Application.Exit> controlador de eventos se pasa un <xref:System.Windows.ExitEventArgs> que proporciona acceso al código de salida con el <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> propiedad. Para obtener más información, consulta <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Puede establecer el código de salida en aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Sin embargo, se omite el valor del código de salida para [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Excepciones no controladas  
 A veces, puede que una aplicación se cierre en condiciones irregulares, como cuando se produce una excepción imprevista. En este caso, es posible que la aplicación no tenga el código necesario para detectar y procesar la excepción. Este tipo de excepción es una excepción no controlada; se muestra una notificación similar a la que aparece en la figura siguiente antes de que se cierre la aplicación.  
  
 ![Notificación de excepción no controlada](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 Desde la perspectiva del usuario, es mejor que una aplicación evite este comportamiento predeterminado realizando todas o alguna de las siguientes acciones:  
  
-   Mostrar información fácil de usar.  
  
-   Intentar mantener la aplicación en funcionamiento.  
  
-   Grabación había detallada, sencillo para los desarrolladores, información de excepción en el registro de eventos de Windows.  
  
 Implementación de esta compatibilidad depende de poder detectar las excepciones no controladas, que es lo que el <xref:System.Windows.Application.DispatcherUnhandledException> evento se desencadena para.  
  
 [!code-xaml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 El <xref:System.Windows.Application.DispatcherUnhandledException> controlador de eventos se pasa un <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parámetro que contiene información contextual referente a la excepción no controlada, incluida la propia excepción (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). Puede usar esta información para determinar cómo debe controlar la excepción.  
  
 Cuando controle <xref:System.Windows.Application.DispatcherUnhandledException>, debe establecer el <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> propiedad `true`; en caso contrario, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aún considera que la excepción no controlada y se revierte al comportamiento predeterminado se ha descrito anteriormente. Si se produce una excepción no controlada y la <xref:System.Windows.Application.DispatcherUnhandledException> no se controla el evento o se controla el evento y <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> está establecido en `false`, la aplicación se cierra inmediatamente. Además, ninguna otra <xref:System.Windows.Application> se generan eventos. Por lo tanto, tiene que controlar <xref:System.Windows.Application.DispatcherUnhandledException> si la aplicación tiene código que deba ejecutarse antes de que se cierra la aplicación.  
  
 Aunque es posible que una aplicación se cierre como resultado de una excepción no controlada, las aplicaciones suelen cerrarse en respuesta a una solicitud del usuario, tal como se explica en la sección siguiente.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Eventos de duración de la aplicación  
 Las aplicaciones independientes y [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] no tiene exactamente la misma duración. En la ilustración siguiente se muestran los eventos clave en la duración de una aplicación independiente y la secuencia en la que se generan.  
  
 ![Aplicación independiente &#45; Eventos de objeto de la aplicación](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Del mismo modo, la ilustración siguiente muestra los eventos clave en la duración de un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]y se muestra la secuencia en la que se generan.  
  
 ![XBAP &#45; Eventos de objeto de la aplicación](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Application>  
 [Información general sobre ventanas de WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)  
 [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)  
 [Identificadores URI de paquete en WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Modelo de aplicación: Temas de procedimientos](https://msdn.microsoft.com/library/76771b09-3688-4d1c-8818-9b3f4cf39a30)  
 [Desarrollo de aplicaciones](../../../../docs/framework/wpf/app-development/index.md)
