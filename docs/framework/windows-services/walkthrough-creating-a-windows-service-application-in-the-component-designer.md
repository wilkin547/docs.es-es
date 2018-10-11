---
title: Creación de una aplicación de un servicio de Windows en Visual Studio
ms.date: 09/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: 27acdac5d34b96dd04fec1bb763edec9077ff928
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "46493612"
---
# <a name="walkthrough-create-a-windows-service-app"></a>Tutorial: Creación de una aplicación de un servicio de Windows

En este artículo se explica cómo crear una sencilla aplicación de servicio de Windows en Visual Studio que escribe mensajes en un registro de eventos.

## <a name="create-a-service"></a>Creación de un servicio

Para empezar, cree el proyecto y defina los valores necesarios para que el servicio funcione correctamente.

1. En Visual Studio, en la barra de menús, elija **Archivo** > **Nuevo** > **Proyecto**, o presione **Ctrl** + **Mayús**+**N**, para abrir el cuadro de diálogo **Nuevo proyecto**.

2. Vaya a la plantilla de proyecto **Servicio de Windows** y selecciónela. Expanda **Instalado** > [**Visual C#** o **Visual Basic**] > **Escritorio de Windows**, o escriba **Servicio de Windows** en el cuadro de búsqueda en la esquina superior derecha.

   ![Plantilla Servicio de Windows en el cuadro de diálogo Nuevo proyecto en Visual Studio](media/new-project-dialog.png)

   > [!NOTE]
   > Si no ve la plantilla **Servicio de Windows**, puede que tenga que instalar la carga de trabajo **Desarrollo de escritorio de .NET**. En el cuadro de diálogo **Nuevo proyecto**, haga clic en el vínculo que dice **Abrir el instalador de Visual Studio** en la parte inferior izquierda. En el **Instalador de Visual Studio**, seleccione la carga de trabajo **Desarrollo de escritorio de .NET** y luego seleccione **Modificar**.

3. Asigne el nombre **MyNewService** al proyecto y después seleccione **Aceptar**.

   La plantilla de proyecto incluye una clase de componente denominada `Service1`, que hereda de <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. Incluye gran parte del código de servicio básico, como el código para iniciar el servicio.

## <a name="rename-the-service"></a>Cambiar el nombre del servicio

Cambie el nombre del servicio **Service1** por **MyNewService**.

1. En la vista **Diseño** de Service1.cs o de Service1.vb, haga clic en el vínculo para **cambiar a la vista de código**. Haga clic con el botón derecho en **Service1** y seleccione **Cambiar nombre** en el menú contextual. Escriba **MyNewService** y luego presione la tecla **ENTRAR** o haga clic en **Aplicar**.

2. En la ventana **Propiedades** de **Service1.cs [Diseño]** o **Service1.vb [Diseño]**, cambie el valor **ServiceName** por **MyNewService**.

3. En el **Explorador de soluciones**, cambie el nombre **Service1.cs** por **MyNewService.cs** o **Service1.vb** por **MyNewService.vb**.

## <a name="add-features-to-the-service"></a>Adición de características al servicio

En esta sección, agregará un registro de eventos personalizado al servicio de Windows. Los registros de eventos no están asociados de ningún modo a los servicios de Windows. El componente <xref:System.Diagnostics.EventLog> se utiliza como ejemplo del tipo de componente que se puede agregar a un servicio de Windows.

### <a name="add-custom-event-log-functionality"></a>Adición de la funcionalidad de registro de eventos personalizado

1. En el **Explorador de soluciones**, abra el menú contextual de **MyNewService.cs** o **MyNewService.vb**y, a continuación, elija **Diseñador de vistas**.

2. En la sección **Componentes** del **Cuadro de herramientas**, arrastre un componente <xref:System.Diagnostics.EventLog> hasta el diseñador.

3. En el **Explorador de soluciones**, abra el menú contextual de **MyNewService.cs** o **MyNewService.vb**y, a continuación, elija **Ver código**.

4. Edite el constructor para definir un registro de eventos personalizado:

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new System.Diagnostics.EventLog();
        if (!System.Diagnostics.EventLog.SourceExists("MySource"))
        {
            System.Diagnostics.EventLog.CreateEventSource(
                "MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

### <a name="define-what-occurs-when-the-service-starts"></a>Definición de qué ocurre al iniciar el servicio

En el Editor de código, busque el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> que se reemplazó automáticamente al crear el proyecto. Agregue una línea de código que escriba una entrada en el registro de eventos cuando el servicio se inicia:

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

Una aplicación de servicio está diseñada para ejecutarse a largo plazo, por lo que suele sondear o supervisar algún elemento del sistema. La supervisión se puede establecer en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> . Sin embargo, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> no lleva a cabo la supervisión. El método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> debe volver al sistema operativo después de que haya comenzado el funcionamiento del servicio. No debe bloquearse ni ejecutar un bucle infinito. Para establecer un mecanismo de sondeo sencillo, puede usar el componente <xref:System.Timers.Timer?displayProperty=nameWithType> de la siguiente manera: en el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, establezca los parámetros en el componente y, a continuación, establezca la propiedad <xref:System.Timers.Timer.Enabled%2A> en `true`. El temporizador activa eventos periódicamente en el código y, en esos instantes, el servicio podría realizar su control. Para ello puede usar el código siguiente:

```csharp
// Set up a timer that triggers every minute.
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 60000; // 60 seconds
timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);
timer.Start();
```

```vb
' Set up a timer that triggers every minute.
Dim timer As System.Timers.Timer = New System.Timers.Timer()
timer.Interval = 60000 ' 60 seconds
AddHandler timer.Elapsed, AddressOf Me.OnTimer
timer.Start()
```

Agregue una variable de miembro a la clase. Contiene el identificador del siguiente evento para escribir en el registro de eventos.

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

Agregue un método nuevo para controlar el evento de temporizador:

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

Es posible que desee realizar tareas mediante el uso de subprocesos de trabajo en segundo plano en lugar de ejecutar todo el trabajo en el subproceso principal. Para obtener más información, vea <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.

### <a name="define-what-occurs-when-the-service-is-stopped"></a>Definición de qué ocurre al detener el servicio

Agregue una línea de código al método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> que agregue una entrada al registro de eventos cuando el servicio se detenga:

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>Definición de otras acciones para el servicio

Puede invalidar los métodos <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> y <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> para definir un procesamiento adicional para el componente. En el siguiente código se muestra cómo reemplazar el método <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> :

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

Deben realizarse algunas acciones personalizadas cuando la clase <xref:System.Configuration.Install.Installer> instala un servicio de Windows. Visual Studio puede crear estos instaladores específicamente para un servicio de Windows y agregarlos al proyecto.

## <a name="set-service-status"></a>Definición del estado de servicio

Los servicios informan de su estado al Administrador de control de servicios, para que los usuarios puedan saber si un servicio funciona correctamente. De manera predeterminada, los servicios que se heredan de <xref:System.ServiceProcess.ServiceBase> informan de un conjunto limitado de parámetros de estado, incluidos Detenido, En pausa y En ejecución. Si un servicio tarda un poco en iniciarse, puede ser útil informar de un estado Inicio pendiente. También puede implementar la configuración de estado Inicio pendiente y Detención pendiente si agrega código que llama a la [función SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)de Windows.

Para implementar el estado pendiente del servicio:

1. Agregue una instrucción `using` o una declaración `Imports` al espacio de nombres <xref:System.Runtime.InteropServices?displayProperty=nameWithType> en el archivo MyNewService.cs o MyNewService.vb:

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. Agregue el código siguiente a MyNewService.cs para declarar los valores de `ServiceState` y agregue una estructura para el estado, que usará en una llamada de invocación de plataforma:

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

3. Ahora, en la clase `MyNewService`, declare la [función SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mediante la [invocación de plataforma](../interop/consuming-unmanaged-dll-functions.md):

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. Para implementar el estado Inicio pendiente, agregue el código siguiente al principio del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> :

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

5. Agregue código para establecer el estado en En ejecución al final del método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> .

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

6. (Opcional) Repita este procedimiento para el método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> .

> [!NOTE]
> El cuadro de diálogo [Administrador de control de servicios](/windows/desktop/Services/service-control-manager) usa los miembros `dwWaitHint` y `dwCheckpoint` de la [estructura SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) para determinar durante cuánto tiempo hay que esperar a que un servicio de Windows se inicie o apague. Si los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> se ejecutan durante mucho tiempo, el servicio puede solicitar más tiempo por medio de una nueva llamada a [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) con un valor de `dwCheckPoint` incrementado.

## <a name="add-installers-to-the-service"></a>Adición de instaladores al servicio

Para poder ejecutar un servicio de Windows, antes debe instalarlo, lo que lo registra con el Administrador de control de servicios. Puede agregar instaladores al proyecto que controlen los detalles del registro.

1. En el **Explorador de soluciones**, abra el menú contextual de **MyNewService.cs** o **MyNewService.vb**y, a continuación, elija **Diseñador de vistas**.

2. Haga clic en el fondo del diseñador para seleccionar el propio servicio, en vez de cualquier elemento de su contenido.

3. Abra el menú contextual de la ventana del diseñador (si usa un dispositivo señalador, haga clic con el botón secundario dentro de la ventana) y, a continuación, elija **Agregar instalador**.

   De forma predeterminada, se agrega al proyecto una clase de componente que contiene dos instaladores. El componente se denomina **ProjectInstaller**, y los instaladores que contiene son el instalador para el servicio y el instalador para el proceso asociado al servicio.

4. En la vista **Diseño** de **ProjectInstaller**, elija **serviceInstaller1** para un proyecto de Visual C# o **ServiceInstaller1** para un proyecto de Visual Basic.

5. En la ventana **Propiedades** , asegúrese de que la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> esté establecida en **MyNewService**.

6. Establezca texto en la propiedad **Descripción** , como "Servicio de ejemplo". Este texto aparece en la ventana Servicios y ayuda al usuario a identificar el servicio y comprender para qué se usa.

7. Establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> en el texto que desea que aparezca en la ventana Servicios en la columna **Nombre** . Por ejemplo, puede escribir "Nombre para mostrar de MyNewService". Este nombre puede ser diferente de la propiedad <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> , que es el nombre usado por el sistema (por ejemplo, al usar el comando `net start` para iniciar el servicio).

8. Establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en <xref:System.ServiceProcess.ServiceStartMode.Automatic>.

     ![Propiedades de instalador para un servicio de Windows](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")

9. En el diseñador, elija **serviceProcessInstaller1** para un proyecto de Visual C# o **ServiceProcessInstaller1** para un proyecto de Visual Basic. Establezca la propiedad <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> en <xref:System.ServiceProcess.ServiceAccount.LocalSystem>. Esto hace que el servicio se instale y se ejecute con la cuenta de sistema local.

    > [!IMPORTANT]
    > La cuenta <xref:System.ServiceProcess.ServiceAccount.LocalSystem> tiene amplios permisos, incluida la capacidad para escribir en el registro de eventos. Utilice esta cuenta con precaución porque podría aumentar el riesgo de ataques por parte de software malintencionado. Para otras tareas, considere la posibilidad de usar la cuenta <xref:System.ServiceProcess.ServiceAccount.LocalService>, que actúa como un usuario sin privilegios en el equipo local y presenta credenciales anónimas a cualquier servidor remoto. En este ejemplo se produce un error si intenta usar la cuenta <xref:System.ServiceProcess.ServiceAccount.LocalService>, ya que necesita permiso de escritura en el registro de eventos.

Para obtener más información sobre los instaladores, vea [Adición de instaladores a una aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).

## <a name="optional-set-startup-parameters"></a>(Opcional) Establecer parámetros de inicio

Un servicio de Windows, al igual que cualquier otro archivo ejecutable, puede aceptar argumentos de línea de comandos o parámetros de inicio. Cuando se agrega código para procesar los parámetros de inicio, los usuarios pueden iniciar el servicio con sus propios parámetros de inicio personalizados mediante la ventana Servicios del Panel de control de Windows. Sin embargo, estos parámetros de inicio no se conservan la próxima vez que se inicia el servicio. Para establecer los parámetros de inicio de manera permanente, puede establecerlos en el Registro, como se muestra en este procedimiento.

> [!NOTE]
> Antes de decidirse a agregar parámetros de inicio, piense en si es la mejor manera de pasar información al servicio. Aunque los parámetros de inicio son fáciles de usar y analizar, y los usuarios los pueden reemplazar fácilmente, pueden ser más difíciles de descubrir y usar para los usuarios sin documentación. Por lo general, si el servicio requiere más de unos pocos parámetros de inicio, debe considerar el uso del Registro o un archivo de configuración en su lugar. Todos los servicios de Windows tienen una entrada en el Registro en **HKLM\System\CurrentControlSet\services**. En la clave del servicio, se puede usar la subclave **Parameters** para almacenar la información a la que puede tener acceso su servicio. Puede usar archivos de configuración de aplicación para un servicio de Windows del mismo modo que lo hace para otros tipos de programas. Para obtener código de ejemplo, vea <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.

Para agregar parámetros de inicio:

1. En el método `Main` de Program.cs o MyNewService.Designer.vb, agregue un parámetro de entrada para pasarlo al constructor del servicio:

   ```csharp
   static void Main(string[] args)
   {
       ServiceBase[] ServicesToRun;
       ServicesToRun = new ServiceBase[]
       {
           new MyNewService(args)
       };
       ServiceBase.Run(ServicesToRun);
   }
   ```

   ```vb
   Shared Sub Main(ByVal cmdArgs() As String)
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. Cambie el constructor `MyNewService` de la siguiente forma:

   ```csharp
   public MyNewService(string[] args)
   {
       InitializeComponent();

        string eventSourceName = "MySource";
        string logName = "MyNewLog";

        if (args.Length > 0)
        {
            eventSourceName = args[0];
        }

        if (args.Length > 1)
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

   Este código modifica la clave del Registro **ImagePath**, que suele contener la ruta de acceso completa al archivo ejecutable para el servicio de Windows. Para ello, agrega los valores de parámetros predeterminados. Las comillas alrededor de la ruta de acceso (y alrededor de cada parámetro individual) son obligatorias para que el servicio se inicie correctamente. Para cambiar los parámetros de inicio para este servicio de Windows, los usuarios pueden cambiar los parámetros proporcionados en la clave del Registro **ImagePath**, aunque la mejor manera es cambiarlos mediante programación y exponer la funcionalidad a los usuarios de una manera fácil de usar (por ejemplo, en una utilidad de administración o configuración).

## <a name="build-the-service"></a>Compilación del servicio

1. En el **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **Propiedades**.

   Aparecerán las páginas de propiedades del proyecto.

2. En la pestaña **Aplicación**, en la lista **Objeto de inicio**, elija **MyNewService.Program**.

3. En el **Explorador de soluciones**, abra el menú contextual del proyecto y, a continuación, elija **Compilar** para compilar el proyecto, o bien presione **Ctrl**+**Mayús**+**B**.

## <a name="install-the-service"></a>Instalación del servicio

Ahora que ha compilado el servicio de Windows, puede instalarlo. Para instalar un servicio de Windows, debe tener credenciales de administrador en el equipo en el que lo va a instalar.

1. Abra un **Símbolo del sistema para desarrolladores para Visual Studio** con credenciales administrativas. Si usa un mouse, haga clic con el botón derecho en **Símbolo del sistema para desarrolladores para VS 2017** en el menú Inicio de Windows y, a continuación, elija **Más** > **Ejecutar como administrador**.

2. En la ventana del **Símbolo del sistema para desarrolladores**, desplácese hasta la carpeta que contiene el resultado del proyecto (de forma predeterminada, es el subdirectorio *\bin\Debug* del proyecto).

3. Escriba el comando siguiente:

    ```shell
    installutil.exe MyNewService.exe
    ```

    Si el servicio se instala correctamente, **installutil.exe** indica que la instalación ha sido correcta. Si el sistema no encuentra **InstallUtil.exe**, asegúrese de que existe en el equipo. Esta herramienta se instala con .NET Framework en la carpeta *%windir%\Microsoft.NET\Framework[64]\\[versión de framework]*. Por ejemplo, la ruta de acceso predeterminada para la versión de 32 bits es *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.

    Si el proceso **installutil.exe** informa de un error, compruebe el registro de instalación para averiguar por qué. De manera predeterminada, el registro está en la misma carpeta que el ejecutable del servicio. La instalación puede generar errores si la clase <xref:System.ComponentModel.RunInstallerAttribute> no está presente en la clase `ProjectInstaller`, si el atributo no está establecido en **true** o si la clase `ProjectInstaller` no está marcada como **pública**.

Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="start-and-run-the-service"></a>Inicio y ejecución del servicio

1. En Windows, abra la aplicación de escritorio **Servicios**. Presione **Windows**+**R** para abrir el cuadro **Ejecutar** y después escriba **services.msc** y presione la tecla **ENTRAR** o haga clic en **Aceptar**.

     El servicio debería aparecer en **Servicios**, mostrado en orden alfabético por el nombre para mostrar que se haya establecido.

     ![MyNewService en la ventana Servicios.](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. En **Servicios**, abra el menú contextual del servicio y, a continuación, elija **Iniciar**.

3. Para detener el servicio, abra el menú contextual del servicio y luego elija **Detener**.

4. (Opcional) Desde la línea de comandos, puede usar los comandos `net start ServiceName` y `net stop ServiceName` para iniciar y detener el servicio.

### <a name="verify-the-event-log-output-of-your-service"></a>Verificación de la salida del registro de eventos del servicio

1. Abra el **Visor de eventos**; para ello, empiece a escribir **Visor de eventos** en el cuadro de búsqueda de la barra de tareas de Windows y luego seleccione **Visor de eventos** en los resultados de la búsqueda.

   > [!TIP]
   > En Visual Studio, puede acceder a los registros de eventos; para ello, abra el **Explorador de servidores** (en el teclado: **Ctrl**+**Alt**+**S**) y expanda el nodo **Registros de eventos** para el equipo local.

2. En **Visor de eventos**, expanda **Registros de aplicaciones y servicios**.

3. Localice la lista correspondiente a **MyNewLog**, o **MyLogFile1** si siguió el procedimiento opcional para agregar argumentos de línea de comandos, y expándala. Debería ver las entradas de las dos acciones (iniciar y detener) que el servicio realizó.

     ![Uso del Visor de eventos para consultar las entradas del registro de eventos](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a>Desinstalación del servicio

1. Abra un **Símbolo del sistema para desarrolladores para Visual Studio** con credenciales administrativas.

2. En la ventana del símbolo del sistema, desplácese hasta la carpeta que contiene la salida del proyecto.

3. Escriba el comando siguiente:

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   Si el servicio se desinstala correctamente, **installutil.exe** indica que el servicio se ha desinstalado correctamente. Para obtener más información, consulta [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).

## <a name="next-steps"></a>Pasos siguientes

Ahora que ya ha creado el servicio, puede crear un programa de instalación independiente que otros usuarios pueden usar para instalar el servicio de Windows. ClickOnce no es compatible con los servicios de Windows, pero puede usar el [conjunto de herramientas de WiX](http://wixtoolset.org/) para crear un instalador para un servicio de Windows. Para otras ideas, vea [Crear un paquete de instalador](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).

Podría probar también el uso de un componente <xref:System.ServiceProcess.ServiceController>, que permite enviar comandos al servicio instalado.

Puede usar un instalador para crear un registro de eventos al instalar la aplicación, en lugar de crearlo cuando se ejecuta la aplicación. Además, el instalador eliminará el registro de eventos cuando se desinstale la aplicación. Para obtener más información, vea la página de referencia de <xref:System.Diagnostics.EventLogInstaller> .

## <a name="see-also"></a>Vea también

- [Aplicaciones de servicios de Windows](../../../docs/framework/windows-services/index.md)
- [Introducción a las aplicaciones de servicios de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Depuración de aplicaciones de servicios de Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [Servicios (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
