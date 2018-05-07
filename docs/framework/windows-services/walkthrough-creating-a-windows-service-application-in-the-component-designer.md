---
title: 'Tutorial: Crear una aplicación de servicios de Windows en el Diseñador de componentes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Service applications, walkthroughs
- Windows Service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: c33b8badcacd4e228d70f8e770d4bf27144c29eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-a-windows-service-application-in-the-component-designer"></a>Tutorial: Crear una aplicación de servicios de Windows en el Diseñador de componentes
En este artículo se demuestra cómo crear una sencilla aplicación de servicio de Windows en Visual Studio que escribe mensajes en un registro de eventos. A continuación se incluyen los pasos básicos que se realizan para crear y usar el servicio:  
  
1.  [Crear un servicio](#BK_CreateProject) mediante la plantilla del proyecto **Servicio de Windows** y configurarlo. Esta plantilla crea una clase que hereda de <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> y escribe gran parte del código básico del servicio, como el código que lo inicia.  
  
2.  [Agregar características al servicio](#BK_WriteCode) para los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> , y reemplazar los otros métodos que quiera redefinir.  
  
3.  [Configurar el estado del servicio](#BK_SetStatus). De manera predeterminada, los servicios creados con <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> implementan solo un subconjunto de las marcas de estado disponibles. Si el servicio tarda mucho tiempo en iniciarse, pausarse o detenerse, puede implementar valores de estado como Inicio pendiente o Finalización pendiente para indicar que está trabajando en una operación.  
  
4.  [Agregar instaladores al servicio](#BK_AddInstallers) para la aplicación de servicio.  
  
5.  (Opcional) [Establecer parámetros de inicio](#BK_StartupParameters), especificar los argumentos de inicio predeterminados y permitir a los usuarios reemplazar la configuración predeterminada al iniciar el servicio manualmente.  
  
6.  [Compilar el servicio](#BK_Build).  
  
7.  [Instalar el servicio](#BK_Install) en el equipo local.  
  
8.  Obtener acceso al Administrador de control de servicios de Windows e [Iniciar y ejecutar el servicio](#BK_StartService).  
  
9. [Desinstalar un servicio de Windows](#BK_Uninstall).  
  
> [!WARNING]
>  La plantilla de proyecto Servicios de Windows que se requiere para este tutorial no está disponible en la edición Express de Visual Studio.  
  
 [!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]  
  
<a name="BK_CreateProject"></a>   
## <a name="creating-a-service"></a>Crear un servicio  
 Para empezar, debe crear el proyecto y definir los valores necesarios para que el servicio funcione correctamente.  
  
#### <a name="to-create-and-configure-your-service"></a>Para crear y configurar el servicio  
  
1.  En Visual Studio, en la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto** .  
  
2.  Seleccione **Servicio de Windows**en la lista de plantillas de proyecto de Visual Basic o Visual C# y asigne al proyecto el nombre **MyNewService**. Elija **Aceptar**.  
  
     La plantilla de proyecto agrega automáticamente una clase de componente, denominada `Service1`, que hereda de <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.  
  
3.  En el menú **Editar** , elija **Buscar y reemplazar**, **Buscar en archivos** (teclado: Ctrl+Mayús+F). Cambie todas las apariciones de `Service1` a `MyNewService`. Encontrará casos en Service1.cs, Program.cs y Service1.Designer.cs (o sus equivalentes .vb).  
  
4.  En la ventana **Propiedades** para **Service1.cs [Diseño]** o **Service1.vb [Diseño]**, establezca <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> y la propiedad **(Name)** para `Service1` en **MyNewService**, si todavía no están establecidos.  
  
5.  En el Explorador de soluciones, cambie el nombre de **Service1.cs** a **MyNewService.cs**o de **Service1.vb** a **MyNewService.vb**.  
  
<a name="BK_WriteCode"></a>   
## <a name="adding-features-to-the-service"></a>Agregar características al servicio  
 En esta sección, agregará un registro de eventos personalizado al servicio de Windows. Los registros de eventos no están asociados de ningún modo a los servicios de Windows. Aquí, el componente <xref:System.Diagnostics.EventLog> se utiliza como ejemplo del tipo de componente que se puede agregar a un servicio de Windows.  
  
#### <a name="to-add-custom-event-log-functionality-to-your-service"></a>Para agregar la funcionalidad de registro de eventos personalizado al servicio  
  
1.  En el **Explorador de soluciones**, abra el menú contextual de **MyNewService.cs** o **MyNewService.vb**y, a continuación, elija **Diseñador de vistas**.  
  
2.  En la sección **Componentes** del **Cuadro de herramientas**, arrastre un componente <xref:System.Diagnostics.EventLog> hasta el diseñador.  
  
3.  En el **Explorador de soluciones**, abra el menú contextual de **MyNewService.cs** o **MyNewService.vb**y, a continuación, elija **Ver código**.  
  
4.  Agregue una declaración para el objeto **eventLog** en la clase `MyNewService` , después de la línea que declara la variable `components` :  
  
     [!code-csharp[VbRadconService#16](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#16)]
     [!code-vb[VbRadconService#16](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#16)]  
  
5.  Agregue o edite el constructor para definir un registro de eventos personalizado:  
  
     [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
     [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]  
  
#### <a name="to-define-what-occurs-when-the-service-starts"></a>Para definir qué ocurre al iniciar el servicio  
  
-   En el Editor de código, busque el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> que se reemplazó automáticamente al crear el proyecto y reemplace el código con lo siguiente. Agrega una entrada al registro de eventos cuando el servicio comienza a ejecutarse:  
  
     [!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
     [!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]  
  
     Una aplicación de servicio está diseñada para ejecutarse a largo plazo, por lo que suele sondear o supervisar algún elemento del sistema. La supervisión se puede establecer en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> . Sin embargo, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> no lleva a cabo la supervisión. El método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> debe volver al sistema operativo después de que haya comenzado el funcionamiento del servicio. No debe bloquearse ni ejecutar un bucle infinito. Para establecer un mecanismo de sondeo sencillo, puede usar el componente <xref:System.Timers.Timer?displayProperty=nameWithType> de la siguiente manera: en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, establezca los parámetros en el componente y, a continuación, establezca la propiedad <xref:System.Timers.Timer.Enabled%2A> en `true`. El temporizador activa eventos periódicamente en el código y, en esos instantes, el servicio podría realizar su control. Para ello puede usar el código siguiente:  
  
    ```csharp  
    // Set up a timer to trigger every minute.  
    System.Timers.Timer timer = new System.Timers.Timer();  
    timer.Interval = 60000; // 60 seconds  
    timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);  
    timer.Start();  
    ```  
  
    ```vb  
    ' Set up a timer to trigger every minute.  
    Dim timer As System.Timers.Timer = New System.Timers.Timer()  
    timer.Interval = 60000 ' 60 seconds  
    AddHandler timer.Elapsed, AddressOf Me.OnTimer  
    timer.Start()  
    ```  
     Agregue una variable miembro a la clase. Contendrá el identificador del evento siguiente para escribir en el registro de eventos.

    ```csharp
    private int eventId = 1;
    ```

    ```vb
    Private eventId As Integer = 1
    ```

     Agregue código para controlar el evento de temporizador:  
  
    ```csharp  
    public void OnTimer(object sender, System.Timers.ElapsedEventArgs args)  
    {  
        // TODO: Insert monitoring activities here.  
        eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);  
    }  
    ```  
  
    ```vb  
    Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)  
        ' TODO: Insert monitoring activities here.  
        eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)  
        eventId = eventId + 1  
    End Sub  
    ```  
  
     Es posible que desee realizar tareas mediante el uso de subprocesos de trabajo en segundo plano en lugar de ejecutar todo el trabajo en el subproceso principal. Para obtener un ejemplo de esto, vea la página de referencia de <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.  
  
#### <a name="to-define-what-occurs-when-the-service-is-stopped"></a>Para definir qué debe ocurrir al detener el servicio  
  
-   Reemplace el código del método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> por el código siguiente: Agrega una entrada al registro de eventos cuando el servicio se detiene:  
  
     [!code-csharp[VbRadconService#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
     [!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]  
  
 En la siguiente sección, puede reemplazar los métodos <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, y <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> para definir procesamiento adicional para el componente.  
  
#### <a name="to-define-other-actions-for-the-service"></a>Para definir otras acciones para el servicio  
  
-   Localice el método que desee controlar y reemplácelo para definir lo que desea que suceda.  
  
     En el siguiente código se muestra cómo reemplazar el método <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :  
  
     [!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
     [!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]  
  
 Deben realizarse algunas acciones personalizadas cuando la clase <xref:System.Configuration.Install.Installer> instala un servicio de Windows. Visual Studio puede crear estos instaladores específicamente para un servicio de Windows y agregarlos al proyecto.  
  
<a name="BK_SetStatus"></a>   
## <a name="setting-service-status"></a>Configurar el estado del servicio  
 Los servicios informan de su estado al Administrador de control de servicios, para que los usuarios puedan saber si un servicio funciona correctamente. De manera predeterminada, los servicios que se heredan de <xref:System.ServiceProcess.ServiceBase> informan de un conjunto limitado de parámetros de estado, incluidos Detenido, En pausa y En ejecución. Si un servicio tarda un poco en iniciarse, puede ser útil informar de un estado Inicio pendiente. También puede implementar la configuración de estado Inicio pendiente y Detención pendiente si agrega código que llama a la [función SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx)de Windows.  
  
#### <a name="to-implement-service-pending-status"></a>Para implementar el estado pendiente del servicio  
  
1.  Agregue una instrucción `using` o una declaración `Imports` al espacio de nombres <xref:System.Runtime.InteropServices?displayProperty=nameWithType> en el archivo MyNewService.cs o MyNewService.vb:  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    ```  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    ```  
  
2.  Agregue el código siguiente a MyNewService.cs para declarar los valores de `ServiceState` y agregue una estructura para el estado, que usará en una llamada de invocación de plataforma:  
  
    ```csharp  
    public enum ServiceState  
      {  
          SERVICE_STOPPED = 0x00000001,  
          SERVICE_START_PENDING = 0x00000002,  
          SERVICE_STOP_PENDING = 0x00000003,  
          SERVICE_RUNNING = 0x00000004,  
          SERVICE_CONTINUE_PENDING = 0x00000005,  
          SERVICE_PAUSE_PENDING = 0x00000006,  
          SERVICE_PAUSED = 0x00000007,  
      }  
  
      [StructLayout(LayoutKind.Sequential)]  
      public struct ServiceStatus  
      {  
          public int dwServiceType;  
          public ServiceState dwCurrentState;  
          public int dwControlsAccepted;  
          public int dwWin32ExitCode;  
          public int dwServiceSpecificExitCode;  
          public int dwCheckPoint;  
          public int dwWaitHint;  
      };  
    ```  
  
    ```vb  
    Public Enum ServiceState  
        SERVICE_STOPPED = 1  
        SERVICE_START_PENDING = 2  
        SERVICE_STOP_PENDING = 3  
        SERVICE_RUNNING = 4  
        SERVICE_CONTINUE_PENDING = 5  
        SERVICE_PAUSE_PENDING = 6  
        SERVICE_PAUSED = 7  
    End Enum  
  
    <StructLayout(LayoutKind.Sequential)>  
    Public Structure ServiceStatus  
        Public dwServiceType As Long  
        Public dwCurrentState As ServiceState  
        Public dwControlsAccepted As Long  
        Public dwWin32ExitCode As Long  
        Public dwServiceSpecificExitCode As Long  
        Public dwCheckPoint As Long  
        Public dwWaitHint As Long  
    End Structure  
    ```  
  
3.  Ahora, en la clase `MyNewService` , declare la [función SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) con la plataforma de invocación:  
  
    ```csharp  
    [DllImport("advapi32.dll", SetLastError=true)]  
            private static extern bool SetServiceStatus(IntPtr handle, ref ServiceStatus serviceStatus);  
    ```  
  
    ```vb  
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean  
    ```  
  
4.  Para implementar el estado Inicio pendiente, agregue el código siguiente al principio del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :  
  
    ```csharp  
    // Update the service state to Start Pending.  
    ServiceStatus serviceStatus = new ServiceStatus();  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;  
    serviceStatus.dwWaitHint = 100000;  
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);  
    ```  
  
    ```vb  
    ' Update the service state to Start Pending.  
    Dim serviceStatus As ServiceStatus = New ServiceStatus()  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING  
    serviceStatus.dwWaitHint = 100000  
    SetServiceStatus(Me.ServiceHandle, serviceStatus)  
    ```  
  
5.  Agregue código para establecer el estado en En ejecución al final del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .  
  
    ```csharp
    // Update the service state to Running.  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;  
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);  
    ```  
  
    ```vb  
    ' Update the service state to Running.  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING  
    SetServiceStatus(Me.ServiceHandle, serviceStatus)  
    ```  
  
6.  (Opcional) Repita este procedimiento para el método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> .  
  
> [!CAUTION]
>  Aparece el cuadro de diálogo [Administrador de control de servicios](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) usa los miembros `dwWaitHint` y `dwCheckpoint` de la [estructura SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) para determinar durante cuánto tiempo hay que esperar a que un servicio de Windows se inicie o apague. Si los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> se ejecutan durante mucho tiempo, el servicio puede solicitar más tiempo por medio de una llamada a [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) de nuevo con un valor de `dwCheckPoint` incrementado.  
  
<a name="BK_AddInstallers"></a>   
## <a name="adding-installers-to-the-service"></a>Agregar instaladores al servicio  
 Para poder ejecutar un servicio de Windows, antes debe instalarlo, lo que lo registra con el Administrador de control de servicios. Puede agregar instaladores al proyecto que controlen los detalles del registro.  
  
#### <a name="to-create-the-installers-for-your-service"></a>Para crear los instaladores necesarios para el servicio  
  
1.  En el **Explorador de soluciones**, abra el menú contextual de **MyNewService.cs** o **MyNewService.vb**y, a continuación, elija **Diseñador de vistas**.  
  
2.  Haga clic en el fondo del diseñador para seleccionar el propio servicio, en vez de cualquier elemento de su contenido.  
  
3.  Abra el menú contextual de la ventana del diseñador (si usa un dispositivo señalador, haga clic con el botón secundario dentro de la ventana) y, a continuación, elija **Agregar instalador**.  
  
     De forma predeterminada, se agrega al proyecto una clase de componente que contiene dos instaladores. El componente se denomina **ProjectInstaller**, y los instaladores que contiene son el instalador para el servicio y el instalador para el proceso asociado al servicio.  
  
4.  En la vista **Diseño** de **ProjectInstaller**, elija **serviceInstaller1** para un proyecto de Visual C# o **ServiceInstaller1** para un proyecto de Visual Basic.  
  
5.  En la ventana **Propiedades** , asegúrese de que la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> esté establecida en **MyNewService**.  
  
6.  Establezca texto en la propiedad **Descripción** , como "Servicio de ejemplo". Este texto aparece en la ventana Servicios y ayuda al usuario a identificar el servicio y comprender para qué se usa.  
  
7.  Establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> en el texto que desea que aparezca en la ventana Servicios en la columna **Nombre** . Por ejemplo, puede escribir "Nombre para mostrar de MyNewService". Este nombre puede ser diferente de la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , que es el nombre usado por el sistema (por ejemplo, al usar el comando `net start` para iniciar el servicio).  
  
8.  Establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en <xref:System.ServiceProcess.ServiceStartMode.Automatic>.  
  
     ![Propiedades de instalador de un servicio de Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")  
  
9. En el diseñador, elija **serviceProcessInstaller1** para un proyecto de Visual C# o **ServiceProcessInstaller1** para un proyecto de Visual Basic. Establezca la propiedad <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> en <xref:System.ServiceProcess.ServiceAccount.LocalSystem>. Esto hará que se instale el servicio y se ejecute con una cuenta de servicio local.  
  
    > [!IMPORTANT]
    >  La cuenta <xref:System.ServiceProcess.ServiceAccount.LocalSystem> tiene amplios permisos, incluida la capacidad para escribir en el registro de eventos. Utilice esta cuenta con precaución porque podría aumentar el riesgo de ataques por parte de software malintencionado. Para otras tareas, considere la posibilidad de usar la cuenta <xref:System.ServiceProcess.ServiceAccount.LocalService>, que actúa como un usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto. En este ejemplo se produce un error si intenta usar la cuenta <xref:System.ServiceProcess.ServiceAccount.LocalService>, ya que necesita permiso de escritura en el registro de eventos.  
  
     Para obtener más información acerca de los instaladores, vea [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
<a name="BK_StartupParameters"></a>   
## <a name="set-startup-parameters"></a>Establecer parámetros de inicio  
 Un servicio de Windows, al igual que cualquier otro archivo ejecutable, puede aceptar argumentos de línea de comandos o parámetros de inicio. Cuando se agrega código para procesar los parámetros de inicio, los usuarios pueden iniciar el servicio con sus propios parámetros de inicio personalizados mediante la ventana Servicios del Panel de control de Windows. Sin embargo, estos parámetros de inicio no se conservan la próxima vez que se inicia el servicio. Para establecer los parámetros de inicio de manera permanente, puede establecerlos en el Registro, como se muestra en este procedimiento.  
  
> [!NOTE]
>  Antes de decidirse a agregar parámetros de inicio, piense en si es la mejor manera de pasar información al servicio. Aunque los parámetros de inicio son fáciles de usar y analizar, y los usuarios los pueden reemplazar fácilmente, pueden ser más difíciles de descubrir y usar para los usuarios sin documentación. Por lo general, si el servicio requiere más de unos pocos parámetros de inicio, debe considerar el uso del Registro o un archivo de configuración en su lugar. Todos los servicios de Windows tienen una entrada en el Registro en HKLM\System\CurrentControlSet\services. En la clave del servicio, se puede usar la subclave **Parameters** para almacenar la información a la que puede tener acceso su servicio. Puede usar archivos de configuración de aplicación para un servicio de Windows del mismo modo que lo hace para otros tipos de programas. Para obtener código de ejemplo, vea <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.  
  
#### <a name="adding-startup-parameters"></a>Agregar parámetros de inicio  
  
1.  En el método `Main` de Program.cs o MyNewService.Designer.vb, agregue un argumento para la línea de comandos:  
  
```csharp  
static void Main(string[] args)
{
    ServiceBase[] ServicesToRun = new ServiceBase[] { new MyNewService(args) };
    ServiceBase.Run(ServicesToRun);
}
```  
  
```vb
Shared Sub Main(ByVal cmdArgs() As String)
    Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
    System.ServiceProcess.ServiceBase.Run(ServicesToRun)
End Sub
```  
  
2.  Cambie el constructor `MyNewService` de la siguiente forma:  
  
```csharp  
public MyNewService(string[] args)
{
    InitializeComponent();
    string eventSourceName = "MySource";
    string logName = "MyNewLog";
    if (args.Count() > 0) 
    {
        eventSourceName = args[0];
    }
    if (args.Count() > 1)
    {
        logName = args[1];
    }
    eventLog1 = new System.Diagnostics.EventLog();
    if (!System.Diagnostics.EventLog.SourceExists(eventSourceName))
    {
        System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName);
    }
    eventLog1.Source = eventSourceName;
    eventLog1.Log = logName;        
}
```  
  
```vb  
Public Sub New(ByVal cmdArgs() As String)
    InitializeComponent()
    Dim eventSourceName As String = "MySource"
    Dim logName As String = "MyNewLog"
    If (cmdArgs.Count() > 0) Then
        eventSourceName = cmdArgs(0)
    End If
    If (cmdArgs.Count() > 1) Then
        logName = cmdArgs(1)
    End If
    eventLog1 = New System.Diagnostics.EventLog()
    If (Not System.Diagnostics.EventLog.SourceExists(eventSourceName)) Then
        System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName)
    End If
    eventLog1.Source = eventSourceName
    eventLog1.Log = logName
End Sub  
```  
  
Este código establece el nombre de registro y el origen de eventos según los parámetros de inicio proporcionados, o bien, usa los valores predeterminados si no se proporcionan argumentos.  
  
3. Para especificar los argumentos de línea de comandos, agregue el código siguiente a la clase `ProjectInstaller` en ProjectInstaller.cs o ProjectInstaller.vb:  
  
```csharp  
protected override void OnBeforeInstall(IDictionary savedState)
{
    string parameter = "MySource1\" \"MyLogFile1";
    Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
    base.OnBeforeInstall(savedState);
}
```

```vb  
Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
    Dim parameter As String = "MySource1"" ""MyLogFile1"
    Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
    MyBase.OnBeforeInstall(savedState)
End Sub  
```  
  
Este código modifica la clave del Registro **ImagePath** , que suele contener la ruta de acceso completa al archivo ejecutable para el servicio de Windows. Para ello, agrega los valores de parámetros predeterminados. Las comillas alrededor de la ruta de acceso (y alrededor de cada parámetro individual) son obligatorias para que el servicio se inicie correctamente. Para cambiar los parámetros de inicio para este servicio de Windows, los usuarios pueden cambiar los parámetros proporcionados en la clave del Registro **ImagePath** , aunque la mejor manera es cambiarlos mediante programación y exponer la funcionalidad a los usuarios de una manera fácil de usar (por ejemplo, en una utilidad de administración o configuración).  
  
<a name="BK_Build"></a>   
## <a name="building-the-service"></a>Compilar el servicio  
  
#### <a name="to-build-your-service-project"></a>Para compilar el proyecto de servicio  
  
1.  En el **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **Propiedades**. Aparecerán las páginas de propiedades del proyecto.  
  
2.  En la pestaña Aplicación, en la lista **Objeto de inicio** , elija **MyNewService.Program**.  
  
3.  En el **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **Compilar** para compilar el proyecto (teclado: Ctrl+Mayús+B).  
  
<a name="BK_Install"></a>   
## <a name="installing-the-service"></a>Instalar el servicio  
 Ahora que ha compilado el servicio de Windows, puede instalarlo. Para instalar un servicio de Windows, debe tener credenciales administrativas en el equipo en el que lo va a instalar.  
  
#### <a name="to-install-a-windows-service"></a>Para instalar un servicio de Windows  
  
1.  En Windows 7 y Windows Server, abra el **Símbolo del sistema para desarrolladores** en **Visual Studio Tools** en el menú **Inicio** . En Windows 8 o Windows 8.1, elija el icono de **Visual Studio Tools** en la pantalla **Inicio** y ejecute el Símbolo del sistema para desarrolladores con credenciales administrativas. (Si usa un mouse, haga clic con el botón derecho en **Símbolo del sistema para desarrolladores**y, a continuación, elija **Ejecutar como administrador**).  
  
2.  En la ventana de símbolo del sistema, desplácese hasta la carpeta que contiene la salida del proyecto. Por ejemplo, en la carpeta Mis documentos, desplácese hasta Visual Studio 2013\Projects\MyNewService\bin\Debug.  
  
3.  Escriba el comando siguiente:  
  
    ```  
    installutil.exe MyNewService.exe  
    ```  
  
     Si el servicio se instala correctamente, installutil.exe indicará que la instalación ha sido correcta. Si el sistema no encuentra InstallUtil.exe, asegúrese de que existe en el equipo. Esta herramienta se instala con .NET Framework en la carpeta `%WINDIR%\Microsoft.NET\Framework[64]\`*versión_Framework*. Por ejemplo, la ruta de acceso predeterminada para la versión de 32 bits de .NET Framework 4, 4.5, 4.5.1 y 4.5.2 es `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.  
  
     Si el proceso installutil.exe informa de un error, compruebe el registro de instalación para averiguar por qué. De manera predeterminada, el registro está en la misma carpeta que el ejecutable del servicio. La instalación puede fallar si el <xref:System.ComponentModel.RunInstallerAttribute> clase no está presente en el `ProjectInstaller` clase, o si el atributo no está establecido en `true`, o bien el `ProjectInstaller` clase no es `public`.  
  
     Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
<a name="BK_StartService"></a>   
## <a name="starting-and-running-the-service"></a>Iniciar y ejecutar el servicio  
  
#### <a name="to-start-and-stop-your-service"></a>Para iniciar y detener el servicio  
  
1.  En Windows, abra la pantalla **Inicio** o el menú **Inicio** y escriba `services.msc`.  
  
     Podrá ver el servicio **MyNewService** en la lista de la ventana **Servicios** .  
  
     ![MyNewService en la ventana Servicios. ] (../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")  
  
2.  En la ventana **Servicios** , abra el menú contextual del servicio y, a continuación, elija **Iniciar**.  
  
3.  Abra el menú contextual del servicio y, a continuación, elija **Detener**.  
  
4.  (Opcional) Desde la línea de comandos, puede usar los comandos `net start``ServiceName` y `net stop``ServiceName` para iniciar y detener el servicio.  
  
#### <a name="to-verify-the-event-log-output-of-your-service"></a>Para comprobar el registro de eventos del servicio  
  
1.  En Visual Studio, abra el **Explorador de servidores** (teclado: Ctrl+Alt+S) y obtenga acceso al nodo **Registros de eventos** del equipo local.  
  
2.  Localice la lista correspondiente a **MyNewLog** (o **MyLogFile1**, si se usa el procedimiento opcional para agregar argumentos de línea de comandos) y expándala. Debería ver las entradas de las dos acciones (iniciar y detener) que ha realizado el servicio.  
  
     ![Use el Visor de eventos para ver las entradas del registro de eventos. ] (../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")  
  
<a name="BK_Uninstall"></a>   
## <a name="uninstalling-a-windows-service"></a>Desinstalar un servicio de Windows  
  
#### <a name="to-uninstall-your-service"></a>Para desinstalar el servicio  
  
1.  Abra un Símbolo del sistema para desarrolladores con credenciales administrativas.  
  
2.  En la ventana de símbolo del sistema, desplácese hasta la carpeta que contiene la salida del proyecto. Por ejemplo, en la carpeta Mis documentos, desplácese hasta Visual Studio 2013\Projects\MyNewService\bin\Debug.  
  
3.  Escriba el comando siguiente:  
  
    ```  
    installutil.exe /u MyNewService.exe  
    ```  
  
     Si el servicio se desinstala correctamente, installutil.exe indicará que el servicio se ha desinstalado correctamente. Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Puede crear un programa de instalación independiente que otros usuarios pueden usar para instalar el servicio de Windows, pero esto requiere pasos adicionales. ClickOnce no admite servicios de Windows, por lo que no puede utilizar el Asistente para publicación. Puede utilizar una versión completa de InstallShield, que Microsoft no proporciona. Para obtener más información acerca de InstallShield, vea [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition). También puede usar [Conjunto de herramientas de Windows Installer XML](http://go.microsoft.com/fwlink/?LinkId=249067) para crear un instalador para un servicio de Windows.  
  
 Podría probar también el uso de un componente <xref:System.ServiceProcess.ServiceController> para enviar comandos al servicio instalado.  
  
 Puede usar un instalador para crear un registro de eventos al instalar la aplicación, en lugar de crearlo cuando se ejecuta la aplicación. Además, el instalador eliminará el registro de eventos cuando se desinstale la aplicación. Para obtener más información, vea la página de referencia de <xref:System.Diagnostics.EventLogInstaller> .  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones de servicios de Windows](../../../docs/framework/windows-services/index.md)  
 [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Depuración de aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Servicios (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
