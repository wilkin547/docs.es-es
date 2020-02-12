---
title: Información general sobre la administración de aplicaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: dbc5bd9f699415fb47f21c6a45b1c58cfcff0f33
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124525"
---
# <a name="application-management-overview"></a>Información general sobre la administración de aplicaciones

Todas las aplicaciones suelen compartir un conjunto común de funciones que se aplica a la implementación y la administración de la aplicación. En este tema se proporciona información general sobre la funcionalidad de la clase <xref:System.Windows.Application> para la creación y administración de aplicaciones.

## <a name="the-application-class"></a>La clase Application

En WPF, la funcionalidad común de ámbito de aplicación se encapsula en la clase <xref:System.Windows.Application>. La clase <xref:System.Windows.Application> incluye la siguiente funcionalidad:

- Realizar el seguimiento e interactuar con la duración de la aplicación.

- Recuperar y procesar los parámetros de la línea de comandos.

- Detectar y responder a las excepciones no controladas.

- Compartir propiedades y recursos en el ámbito de aplicación.

- Administrar ventanas en las aplicaciones independientes.

- Seguimiento y administración de la navegación.

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Cómo realizar las tareas comunes con la clase Application

Si no le interesan todos los detalles de la clase <xref:System.Windows.Application>, en la tabla siguiente se enumeran algunas de las tareas comunes de <xref:System.Windows.Application> y cómo realizarlas. Viendo las API y los temas relacionados, puede buscar más información y código de ejemplo.

|Tarea|Enfoque|
|----------|--------------|
|Obtener un objeto que representa la aplicación actual|Utilice la propiedad <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|
|Agregar una pantalla de inicio a una aplicación|Vea [Agregar una pantalla de presentación a una aplicación WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).|
|Iniciar una aplicación|Utilice el método <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|
|Detener una aplicación|Use el método <xref:System.Windows.Application.Shutdown%2A> del objeto <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|
|Obtener los argumentos de la línea de comandos|Controle el evento de <xref:System.Windows.Application.Startup?displayProperty=nameWithType> y use la propiedad <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType>. Para obtener un ejemplo, vea el evento <xref:System.Windows.Application.Startup?displayProperty=nameWithType>.|
|Obtener y establecer el código de salida de la aplicación|Establezca la propiedad <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> en el controlador de eventos <xref:System.Windows.Application.Exit?displayProperty=nameWithType> o llame al método <xref:System.Windows.Application.Shutdown%2A> y pase un entero.|
|Detectar y responder a las excepciones no controladas|Controle el evento <xref:System.Windows.Application.DispatcherUnhandledException>.|
|Obtener y establecer recursos en el ámbito de aplicación|Utilice la propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|
|Usar un diccionario de recursos en el ámbito de aplicación|Vea [usar un diccionario de recursos del ámbito de aplicación](how-to-use-an-application-scope-resource-dictionary.md).|
|Obtener y establecer propiedades en el ámbito de aplicación|Utilice la propiedad <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|
|Obtener y guardar el estado de una aplicación|Vea [conservar y restaurar propiedades de ámbito de aplicación a través de sesiones de aplicación](persist-and-restore-application-scope-properties.md).|
|Administrar archivos de datos que no son de código, incluidos los archivos de recursos, los archivos de contenido y los archivos de sitio de origen.|Vea [archivos de recursos, contenido y datos de aplicaciones de WPF](wpf-application-resource-content-and-data-files.md).|
|Administrar ventanas en las aplicaciones independientes|Vea [WPF Windows Overview](wpf-windows-overview.md) (Introducción a Windows Presentation Foundation).|
|Realizar un seguimiento y administrar la navegación|Vea [información general sobre navegación](navigation-overview.md).|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a>La definición de aplicación

Para poder emplear la funcionalidad de la clase <xref:System.Windows.Application>, debe implementar una definición de aplicación. Una definición de aplicación de WPF es una clase que se deriva de <xref:System.Windows.Application> y se configura con una configuración especial de MSBuild.

### <a name="implementing-an-application-definition"></a>Implementar una definición de aplicación

Una definición de aplicación de WPF típica se implementa mediante el marcado y el código subyacente. Esto le permite usar marcado para establecer mediante declaración propiedades, recursos y eventos de registro de la aplicación, mientras que el control de eventos y la implementación del comportamiento específico de la aplicación se realizan en el código subyacente.

En el ejemplo siguiente se muestra cómo implementar una definición de aplicación usando tanto marcado como código subyacente:

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

Para que un archivo de marcado y un archivo de código subyacente funcionen conjuntamente, debe ocurrir lo siguiente:

- En el marcado, el elemento `Application` debe incluir el atributo `x:Class`. Cuando se compila la aplicación, la existencia de `x:Class` en el archivo de marcado hace que MSBuild cree una `partial` clase que deriva de <xref:System.Windows.Application> y tiene el nombre especificado por el atributo `x:Class`. Esto requiere la adición de una declaración de espacio de nombres XML para el esquema XAML (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).

- En el código subyacente, la clase debe ser una `partial` clase con el mismo nombre especificado por el atributo `x:Class` en el marcado y debe derivar de <xref:System.Windows.Application>. Esto permite asociar el archivo de código subyacente a la clase `partial` que se genera para el archivo de marcado cuando se compila la aplicación (consulte [compilar una aplicación WPF](building-a-wpf-application-wpf.md)).

> [!NOTE]
> Al crear un nuevo proyecto de aplicación WPF o un proyecto de aplicación de explorador de WPF con Visual Studio, se incluye una definición de aplicación de forma predeterminada y se define mediante el marcado y el código subyacente.

Este código es el mínimo necesario para implementar una definición de aplicación. Sin embargo, es necesario realizar una configuración adicional de MSBuild en la definición de la aplicación antes de compilar y ejecutar la aplicación.

### <a name="configuring-the-application-definition-for-msbuild"></a>Configurar la definición de aplicación para MSBuild

Las aplicaciones independientes y las aplicaciones de explorador XAML (XBAP) requieren la implementación de un cierto nivel de infraestructura antes de poder ejecutarse. La parte más importante de esta infraestructura es el punto de entrada. Cuando un usuario inicia una aplicación, el sistema operativo llama al punto de entrada, que es una función conocida para iniciar las aplicaciones.

Tradicionalmente, los desarrolladores necesitaban escribir todo o parte de este código, según la tecnología. Sin embargo, WPF genera este código cuando el archivo de marcado de la definición de la aplicación se configura como un elemento de `ApplicationDefinition` de MSBuild, como se muestra en el siguiente archivo de proyecto de MSBuild:

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

Dado que el archivo de código subyacente contiene código, se marca como un elemento de `Compile` de MSBuild, como es normal.

La aplicación de estas configuraciones de MSBuild al marcado y a los archivos de código subyacente de una definición de aplicación hace que MSBuild genere código como el siguiente:

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

El código resultante aumenta la definición de la aplicación con código de infraestructura adicional, que incluye el método de punto de entrada `Main`. El atributo <xref:System.STAThreadAttribute> se aplica al método `Main` para indicar que el subproceso principal de la interfaz de usuario de la aplicación WPF es un subproceso STA, que es necesario para las aplicaciones de WPF. Cuando se llama a, `Main` crea una nueva instancia de `App` antes de llamar al método `InitializeComponent` para registrar los eventos y establecer las propiedades que se implementan en el marcado. Dado que `InitializeComponent` se genera automáticamente, no es necesario llamar explícitamente a `InitializeComponent` desde una definición de aplicación como lo hace para implementaciones de <xref:System.Windows.Controls.Page> y <xref:System.Windows.Window>. Por último, se llama al método <xref:System.Windows.Application.Run%2A> para iniciar la aplicación.

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a>Obtener la aplicación actual

Dado que la funcionalidad de la clase <xref:System.Windows.Application> se comparte en una aplicación, solo puede haber una instancia de la clase <xref:System.Windows.Application> por <xref:System.AppDomain>. Para aplicar esto, la clase <xref:System.Windows.Application> se implementa como una clase singleton (vea [implementar Singleton en C# ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650316(v=pandp.10))), que crea una única instancia de sí misma y proporciona acceso compartido a ella con la propiedad <xref:System.Windows.Application.Current%2A> `static`.

En el código siguiente se muestra cómo adquirir una referencia al objeto <xref:System.Windows.Application> para la <xref:System.AppDomain>actual.

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<xref:System.Windows.Application.Current%2A> devuelve una referencia a una instancia de la clase <xref:System.Windows.Application>. Si desea una referencia a la clase derivada <xref:System.Windows.Application> debe convertir el valor de la propiedad <xref:System.Windows.Application.Current%2A>, como se muestra en el ejemplo siguiente.

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

Puede inspeccionar el valor de <xref:System.Windows.Application.Current%2A> en cualquier momento de la duración de un objeto <xref:System.Windows.Application>. En cambio, se recomienda tener cuidado. Después de crear una instancia de la clase <xref:System.Windows.Application>, hay un período durante el cual el estado del objeto <xref:System.Windows.Application> es incoherente. Durante este período, <xref:System.Windows.Application> está realizando las diversas tareas de inicialización que requiere el código para ejecutarse, incluido el establecimiento de la infraestructura de la aplicación, el establecimiento de las propiedades y el registro de eventos. Si intenta usar el objeto de <xref:System.Windows.Application> durante este período, el código puede tener resultados inesperados, especialmente si depende de las distintas propiedades de <xref:System.Windows.Application> que se establecen.

Cuando <xref:System.Windows.Application> completa su trabajo de inicialización, su duración comienza realmente.

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a>Duración de la aplicación

La duración de una aplicación WPF está marcada por varios eventos que se producen en <xref:System.Windows.Application> para que sepa cuándo se ha iniciado la aplicación, se ha activado y desactivado y se ha cerrado.

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a>Pantalla de presentación

A partir del .NET Framework 3,5 SP1, puede especificar una imagen para usarla en una ventana de inicio o en una *pantalla de presentación*. La clase <xref:System.Windows.SplashScreen> facilita la visualización de una ventana de inicio mientras se carga la aplicación. La ventana de <xref:System.Windows.SplashScreen> se crea y se muestra antes de que se llame a <xref:System.Windows.Application.Run%2A>. Para obtener más información, consulte [hora de inicio](../advanced/application-startup-time.md) de la aplicación y [Agregar una pantalla de presentación a una aplicación WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a>Iniciar una aplicación

Una vez que se llama a <xref:System.Windows.Application.Run%2A> y se inicializa la aplicación, la aplicación está lista para ejecutarse. Este momento se indica cuando se genera el evento <xref:System.Windows.Application.Startup>:

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

En este punto de la duración de una aplicación, lo más habitual es mostrar una interfaz de usuario.

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a>Mostrar una interfaz de usuario

La mayoría de las aplicaciones Windows independientes abren un <xref:System.Windows.Window> cuando empiezan a ejecutarse. El controlador de eventos <xref:System.Windows.Application.Startup> es una ubicación desde la que puede hacer esto, tal y como se muestra en el código siguiente.

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> La primera <xref:System.Windows.Window> de la que se van a crear instancias en una aplicación independiente se convierte en la ventana principal de la aplicación de forma predeterminada. La propiedad <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> hace referencia a este objeto <xref:System.Windows.Window>. El valor de la propiedad <xref:System.Windows.Application.MainWindow%2A> se puede cambiar mediante programación si una ventana diferente de la primera instancia de <xref:System.Windows.Window> debe ser la ventana principal.

Cuando se inicia una aplicación XBAP por primera vez, lo más probable es que vaya a una <xref:System.Windows.Controls.Page>. Esto se muestra en el siguiente código.

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

Si controla <xref:System.Windows.Application.Startup> para abrir solo un <xref:System.Windows.Window> o navegar a un <xref:System.Windows.Controls.Page>, puede establecer el atributo `StartupUri` en el marcado en su lugar.

En el ejemplo siguiente se muestra cómo usar la <xref:System.Windows.Application.StartupUri%2A> desde una aplicación independiente para abrir un <xref:System.Windows.Window>.

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Application.StartupUri%2A> desde una aplicación XBAP para navegar a una <xref:System.Windows.Controls.Page>.

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

Este marcado tiene el mismo efecto que el código anterior para abrir una ventana.

> [!NOTE]
> Para obtener más información sobre la navegación, consulte [información general sobre navegación](navigation-overview.md).

Necesita controlar el evento <xref:System.Windows.Application.Startup> para abrir un <xref:System.Windows.Window> si necesita crear una instancia de él mediante un constructor sin parámetros, o bien debe establecer sus propiedades o suscribirse a sus eventos antes de mostrarlos, o bien debe procesar los argumentos de línea de comandos que se proporcionaron cuando se inició la aplicación.

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a>Procesar argumentos de la línea de comandos

En Windows, las aplicaciones independientes se pueden iniciar desde un símbolo del sistema o desde el escritorio. En ambos casos, es posible pasar argumentos de la línea de comandos a la aplicación. En el ejemplo siguiente se muestra una aplicación que se inicia con un solo argumento de la línea de comandos, "/StartMinimized":

`wpfapplication.exe /StartMinimized`

Durante la inicialización de la aplicación, WPF recupera los argumentos de la línea de comandos del sistema operativo y los pasa al controlador de eventos <xref:System.Windows.Application.Startup> a través de la propiedad <xref:System.Windows.StartupEventArgs.Args%2A> del parámetro <xref:System.Windows.StartupEventArgs>. Puede recuperar y almacenar los argumentos de la línea de comandos usando código como el siguiente.

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

El código controla <xref:System.Windows.Application.Startup> para comprobar si se proporcionó el argumento de línea de comandos **/StartMinimized** ; Si es así, abre la ventana principal con un <xref:System.Windows.WindowState> de <xref:System.Windows.WindowState.Minimized>. Tenga en cuenta que, dado que la propiedad <xref:System.Windows.Window.WindowState%2A> debe establecerse mediante programación, el <xref:System.Windows.Window> principal se debe abrir explícitamente en el código.

Las XBAP no pueden recuperar y procesar argumentos de la línea de comandos porque se inician mediante la implementación de ClickOnce (vea [implementación de una aplicación de WPF](deploying-a-wpf-application-wpf.md)). En cambio, pueden recuperar y procesar los parámetros de las cadenas de consulta de las direcciones URL que se usan para iniciarlas.

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a>Activación y desactivación de aplicaciones

Windows permite a los usuarios cambiar entre aplicaciones. El método más común es usar la combinación de teclas ALT+TAB. Una aplicación solo se puede cambiar a si tiene un <xref:System.Windows.Window> visible que un usuario puede seleccionar. La <xref:System.Windows.Window> seleccionada actualmente es la *ventana activa* (también conocida como *ventana de primer plano*) y es el <xref:System.Windows.Window> que recibe los datos proporcionados por el usuario. La aplicación con la ventana activa es la *aplicación activa* (o *aplicación de primer plano*). Una aplicación se convierte en la aplicación activa en las siguientes circunstancias:

- Se inicia y muestra un <xref:System.Windows.Window>.

- Un usuario cambia de otra aplicación seleccionando un <xref:System.Windows.Window> en la aplicación.

Puede detectar cuándo se activa una aplicación controlando el evento <xref:System.Windows.Application.Activated?displayProperty=nameWithType>.

De manera similar, una aplicación puede volverse inactiva en las circunstancias siguientes:

- Un usuario cambia a otra aplicación desde la actual.

- Cuando se cierra la aplicación.

Puede detectar cuándo una aplicación pasa a estar inactiva mediante el control del evento de <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>.

En el código siguiente se muestra cómo controlar los eventos <xref:System.Windows.Application.Activated> y <xref:System.Windows.Application.Deactivated> para determinar si una aplicación está activa.

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

También se puede activar y desactivar un <xref:System.Windows.Window>. Para obtener más información, vea <xref:System.Windows.Window.Activated?displayProperty=nameWithType> y <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.

> [!NOTE]
> No se genera ni <xref:System.Windows.Application.Activated?displayProperty=nameWithType> ni <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> para XBAP.

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a>Cierre de la aplicación

La duración de una aplicación finaliza cuando se cierra, lo cual puede ocurrir por las razones siguientes:

- Un usuario cierra cada <xref:System.Windows.Window>.

- Un usuario cierra la <xref:System.Windows.Window>principal.

- Un usuario finaliza la sesión de Windows cerrando la sesión o apagando.

- Se ha cumplido una condición específica de la aplicación.

Para ayudarle a administrar el cierre de la aplicación, <xref:System.Windows.Application> proporciona el método <xref:System.Windows.Application.Shutdown%2A>, la propiedad <xref:System.Windows.Application.ShutdownMode%2A> y los eventos <xref:System.Windows.Application.SessionEnding> y <xref:System.Windows.Application.Exit>.

> [!NOTE]
> <xref:System.Windows.Application.Shutdown%2A> solo se puede llamar desde aplicaciones que tengan <xref:System.Security.Permissions.UIPermission>. Las aplicaciones de WPF independientes siempre tienen este permiso. Sin embargo, las XBAP que se ejecutan en el espacio aislado de seguridad de confianza parcial de la zona de Internet no lo hacen.

#### <a name="shutdown-mode"></a>Modo de apagado

La mayoría de las aplicaciones se apagan cuando se cierran todas las ventanas o cuando se cierra la ventana principal. En ocasiones, en cambio, puede haber otras condiciones específicas de la aplicación que determinen cuándo se cierra la aplicación. Puede especificar las condiciones en las que se cerrará la aplicación estableciendo <xref:System.Windows.Application.ShutdownMode%2A> con uno de los siguientes valores de enumeración <xref:System.Windows.ShutdownMode>:

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

El valor predeterminado de <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode.OnLastWindowClose>, lo que significa que una aplicación se cierra automáticamente cuando el usuario cierra la última ventana de la aplicación. Sin embargo, si la aplicación debe cerrarse cuando se cierra la ventana principal, WPF lo hace automáticamente si establece <xref:System.Windows.Application.ShutdownMode%2A> en <xref:System.Windows.ShutdownMode.OnMainWindowClose>. Esto se muestra en el ejemplo siguiente.

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

Si tiene condiciones de cierre específicas de la aplicación, establezca <xref:System.Windows.Application.ShutdownMode%2A> en <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. En este caso, es su responsabilidad cerrar una aplicación llamando explícitamente al método <xref:System.Windows.Application.Shutdown%2A>; de lo contrario, la aplicación seguirá ejecutándose aunque todas las ventanas estén cerradas. Tenga en cuenta que se llama implícitamente a <xref:System.Windows.Application.Shutdown%2A> cuando el <xref:System.Windows.Application.ShutdownMode%2A> es <xref:System.Windows.ShutdownMode.OnLastWindowClose> o <xref:System.Windows.ShutdownMode.OnMainWindowClose>.

> [!NOTE]
> <xref:System.Windows.Application.ShutdownMode%2A> puede establecerse desde una aplicación XBAP, pero se omite; una aplicación XBAP siempre se cierra cuando se navega fuera de en un explorador o cuando se cierra el explorador que hospeda la aplicación XBAP. Para obtener más información, consulte [Información general sobre navegación](navigation-overview.md).

#### <a name="session-ending"></a>Fin de la sesión

Las condiciones de cierre que se describen en la propiedad <xref:System.Windows.Application.ShutdownMode%2A> son específicas de una aplicación. En algunos casos, en cambio, es posible que una aplicación se cierre como resultado de una condición externa. La condición externa más común se produce cuando un usuario finaliza la sesión de Windows mediante las siguientes acciones:

- Cerrando sesión

- Apagar

- Reiniciar

- Hibernar

Para detectar cuándo finaliza una sesión de Windows, puede controlar el evento <xref:System.Windows.Application.SessionEnding>, como se muestra en el ejemplo siguiente.

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

En este ejemplo, el código inspecciona la propiedad <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> para determinar cómo finaliza la sesión de Windows. Usa este valor para mostrar un mensaje de confirmación al usuario. Si el usuario no desea que finalice la sesión, el código establece <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> en `true` para evitar que finalice la sesión de Windows.

> [!NOTE]
> no se produce <xref:System.Windows.Application.SessionEnding> para XBAP.

#### <a name="exit"></a>Salir

Cuando una aplicación se apaga, es posible que necesite realizar algunos últimos procesos, como conservar el estado de la aplicación. En estas situaciones, puede controlar el evento <xref:System.Windows.Application.Exit>, como hace el controlador de eventos `App_Exit` en el ejemplo siguiente. Se define como un controlador de eventos en el archivo *app. Xaml* . Su implementación se resalta en los archivos *app.Xaml.CS* y *Application. Xaml. VB* .

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

Para ver el ejemplo completo, vea [conservar y restaurar propiedades de ámbito de aplicación a través de sesiones de aplicación](persist-and-restore-application-scope-properties.md).

las aplicaciones independientes y XBAP pueden controlar <xref:System.Windows.Application.Exit>. En el caso de las XBAP, se genera <xref:System.Windows.Application.Exit> cuando en las siguientes circunstancias:

- Una aplicación XBAP se desplaza fuera de.

- En Internet Explorer, cuando se cierra la pestaña que hospeda la aplicación XBAP.

- Cuando se cierra el explorador.

#### <a name="exit-code"></a>Código de salida

La mayoría de las aplicaciones las inicia el sistema operativo en respuesta a una solicitud del usuario. En cambio, una aplicación puede ser iniciada por otra aplicación para realizar alguna tarea concreta. Cuando la aplicación iniciada se cierra, es posible que la aplicación que la ha iniciado quiera conocer la condición en la que se cerró la aplicación iniciada. En estas situaciones, Windows permite a las aplicaciones devolver un código de salida de la aplicación al cerrarse. De forma predeterminada, las aplicaciones de WPF devuelven un valor de código de salida de 0.

> [!NOTE]
> Al depurar desde Visual Studio, el código de salida de la aplicación se muestra en la ventana de **salida** cuando se cierra la aplicación, en un mensaje similar al siguiente:
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> Para abrir la ventana **resultados** , haga clic en **salida** en el menú **Ver** .

Para cambiar el código de salida, puede llamar a la sobrecarga <xref:System.Windows.Application.Shutdown%28System.Int32%29>, que acepta un argumento de tipo entero como código de salida:

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

Puede detectar el valor del código de salida y cambiarlo, controlando el evento <xref:System.Windows.Application.Exit>. Se pasa al controlador de eventos <xref:System.Windows.Application.Exit> un <xref:System.Windows.ExitEventArgs> que proporciona acceso al código de salida con la propiedad <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A>. Para más información, consulte <xref:System.Windows.Application.Exit>.

> [!NOTE]
> Puede establecer el código de salida tanto en aplicaciones independientes como en XBAP. Sin embargo, el valor de código de salida se omite para las XBAP.

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a>Excepciones no controladas

A veces, puede que una aplicación se cierre en condiciones irregulares, como cuando se produce una excepción imprevista. En este caso, es posible que la aplicación no tenga el código necesario para detectar y procesar la excepción. Este tipo de excepción es una excepción no controlada; se muestra una notificación similar a la que aparece en la figura siguiente antes de que se cierre la aplicación.

![Captura de pantalla que muestra una notificación de excepción no controlada.](./media/application-management-overview/unhandled-exception-notification.png)

Desde la perspectiva del usuario, es mejor que una aplicación evite este comportamiento predeterminado realizando todas o alguna de las siguientes acciones:

- Mostrar información fácil de usar.

- Intentar mantener la aplicación en funcionamiento.

- Registra la información detallada de las excepciones para el desarrollador en el registro de eventos de Windows.

La implementación de esta compatibilidad depende de la capacidad de detectar las excepciones no controladas, que es para la que se genera el evento <xref:System.Windows.Application.DispatcherUnhandledException>.

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

Se pasa al controlador de eventos <xref:System.Windows.Application.DispatcherUnhandledException> un parámetro <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> que contiene información contextual relativa a la excepción no controlada, incluida la propia excepción (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). Puede usar esta información para determinar cómo debe controlar la excepción.

Al controlar <xref:System.Windows.Application.DispatcherUnhandledException>, debe establecer la propiedad <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> en `true`; de lo contrario, WPF sigue considerando la excepción como no controlada y revierte al comportamiento predeterminado descrito anteriormente. Si se produce una excepción no controlada y no se controla el evento <xref:System.Windows.Application.DispatcherUnhandledException> o si el evento está controlado y <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> está establecido en `false`, la aplicación se cierra inmediatamente. Además, no se generan otros eventos de <xref:System.Windows.Application>. Por lo tanto, debe controlar <xref:System.Windows.Application.DispatcherUnhandledException> si la aplicación tiene código que debe ejecutarse antes de que se cierre la aplicación.

Aunque es posible que una aplicación se cierre como resultado de una excepción no controlada, las aplicaciones suelen cerrarse en respuesta a una solicitud del usuario, tal como se explica en la sección siguiente.

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a>Eventos de duración de la aplicación

Las aplicaciones independientes y XBAP no tienen exactamente la misma duración. En la ilustración siguiente se muestran los eventos clave en la duración de una aplicación independiente y la secuencia en la que se generan.

![Eventos de &#45; objeto de aplicación de aplicación independiente](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")

Del mismo modo, en la siguiente ilustración se muestran los eventos clave de la duración de una aplicación XBAP y se muestra la secuencia en la que se generan.

![Eventos &#45; de objeto de aplicación de XBAP](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Application>
- [Información general sobre ventanas de WPF](wpf-windows-overview.md)
- [Información general sobre navegación](navigation-overview.md)
- [Archivos de recursos, contenido y datos de aplicaciones de WPF](wpf-application-resource-content-and-data-files.md)
- [Identificadores URI de paquete en WPF](pack-uris-in-wpf.md)
- [Modelo de aplicación: temas de procedimientos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Desarrollo de aplicaciones](index.md)
