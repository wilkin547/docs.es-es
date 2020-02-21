---
title: 'Aplicaciones autohospedadas de gRPC: gRPC para desarrolladores de WCF'
description: Implementación de aplicaciones de ASP.NET Core gRPC como servicios autohospedados.
ms.date: 09/02/2019
ms.openlocfilehash: 2244f161ad4b5d60138ae0f7b4d6a9c8c8829aa8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503400"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="653f0-103">Aplicaciones autohospedadas de gRPC</span><span class="sxs-lookup"><span data-stu-id="653f0-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="653f0-104">Aunque las aplicaciones ASP.NET Core 3,0 se pueden hospedar en IIS en Windows Server, actualmente no es posible hospedar una aplicación gRPC en IIS porque no se admiten algunas de las funcionalidades de HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="653f0-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="653f0-105">Esta funcionalidad es un objetivo para una futura actualización de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="653f0-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="653f0-106">Puede ejecutar la aplicación como un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="653f0-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="653f0-107">O bien, puede ejecutarlo como un servicio de Linux controlado por el [sistema](https://en.wikipedia.org/wiki/Systemd), debido a las nuevas características de las extensiones de hospedaje de .net Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="653f0-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="653f0-108">Ejecutar la aplicación como un servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="653f0-108">Run your app as a Windows service</span></span>

<span data-ttu-id="653f0-109">Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Windows, instale el paquete [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) de NuGet.</span><span class="sxs-lookup"><span data-stu-id="653f0-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="653f0-110">A continuación, agregue una llamada a `UseWindowsService` al método `CreateHostBuilder` en `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="653f0-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="653f0-111">Si la aplicación no se está ejecutando como un servicio de Windows, el método `UseWindowsService` no hace nada.</span><span class="sxs-lookup"><span data-stu-id="653f0-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="653f0-112">Ahora, publique la aplicación mediante uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="653f0-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="653f0-113">En Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **publicar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="653f0-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="653f0-114">Desde el CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="653f0-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="653f0-115">Al publicar una aplicación de .NET Core, puede crear una implementación *dependiente del marco* o una implementación *autocontenida* .</span><span class="sxs-lookup"><span data-stu-id="653f0-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="653f0-116">Las implementaciones dependientes del marco requieren que el entorno de tiempo de ejecución compartido de .NET Core esté instalado en el host donde se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="653f0-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="653f0-117">Las implementaciones independientes se publican con una copia completa del entorno de ejecución y el marco de trabajo de .NET Core y se pueden ejecutar en cualquier host.</span><span class="sxs-lookup"><span data-stu-id="653f0-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="653f0-118">Para obtener más información, incluidas las ventajas y desventajas de cada método, consulte la documentación de [implementación de aplicaciones .net Core](../../core/deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="653f0-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="653f0-119">Para publicar una compilación independiente de la aplicación que no requiere la instalación del tiempo de ejecución de .NET Core 3,0 en el host, especifique el tiempo de ejecución que se va a incluir con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="653f0-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="653f0-120">Use la marca `-r` (o `--runtime`).</span><span class="sxs-lookup"><span data-stu-id="653f0-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="653f0-121">Para publicar una compilación dependiente del marco, omita la marca `-r`.</span><span class="sxs-lookup"><span data-stu-id="653f0-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="653f0-122">Copie el contenido completo del directorio `publish` en una carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="653f0-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="653f0-123">A continuación, use la [herramienta SC](/windows/desktop/services/controlling-a-service-using-sc) para crear un servicio de Windows para el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="653f0-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="653f0-124">Registro en el registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="653f0-124">Log to the Windows event log</span></span>

<span data-ttu-id="653f0-125">El método `UseWindowsService` agrega automáticamente un proveedor de [registro](/aspnet/core/fundamentals/logging/) que escribe mensajes de registro en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="653f0-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="653f0-126">Puede configurar el registro para este proveedor agregando una entrada `EventLog` a la sección `Logging` de `appsettings.json` u otro origen de configuración.</span><span class="sxs-lookup"><span data-stu-id="653f0-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span> 

<span data-ttu-id="653f0-127">Puede invalidar el nombre de origen utilizado en el registro de eventos estableciendo una propiedad `SourceName` en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="653f0-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="653f0-128">Si no especifica un nombre, se usará el nombre predeterminado de la aplicación (normalmente el nombre del ensamblado ejecutable).</span><span class="sxs-lookup"><span data-stu-id="653f0-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="653f0-129">Al final de este capítulo encontrará más información sobre el registro.</span><span class="sxs-lookup"><span data-stu-id="653f0-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="653f0-130">Ejecución de la aplicación como un servicio de Linux con systemd</span><span class="sxs-lookup"><span data-stu-id="653f0-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="653f0-131">Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Linux (o *demonio* en la jerga de Linux), instale el paquete [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) desde NuGet.</span><span class="sxs-lookup"><span data-stu-id="653f0-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="653f0-132">A continuación, agregue una llamada a `UseSystemd` al método `CreateHostBuilder` en `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="653f0-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="653f0-133">Si la aplicación no se está ejecutando como un servicio de Linux, el método `UseSystemd` no hace nada.</span><span class="sxs-lookup"><span data-stu-id="653f0-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="653f0-134">Publique la aplicación ahora.</span><span class="sxs-lookup"><span data-stu-id="653f0-134">Now publish your application.</span></span> <span data-ttu-id="653f0-135">La aplicación puede ser dependiente del marco de trabajo o independiente para el tiempo de ejecución de Linux pertinente (por ejemplo, `linux-x64`).</span><span class="sxs-lookup"><span data-stu-id="653f0-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="653f0-136">Puede publicar mediante uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="653f0-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="653f0-137">En Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **publicar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="653f0-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span> 
* <span data-ttu-id="653f0-138">En el CLI de .NET Core, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="653f0-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
<span data-ttu-id="653f0-139">Copie el contenido completo del directorio `publish` en una carpeta de instalación del host de Linux.</span><span class="sxs-lookup"><span data-stu-id="653f0-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="653f0-140">El registro del servicio requiere que se agregue un archivo especial, denominado *archivo de unidad*, al directorio `/etc/systemd/system`.</span><span class="sxs-lookup"><span data-stu-id="653f0-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="653f0-141">Necesitará el permiso raíz para crear un archivo en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="653f0-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="653f0-142">Asigne al archivo el nombre que desee `systemd` usar y la extensión `.service`.</span><span class="sxs-lookup"><span data-stu-id="653f0-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="653f0-143">Por ejemplo, use `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="653f0-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="653f0-144">El archivo de servicio usa el formato INI, tal como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="653f0-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="653f0-145">La propiedad `Type=notify` indica `systemd` que la aplicación le notificará en el inicio y el apagado.</span><span class="sxs-lookup"><span data-stu-id="653f0-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="653f0-146">La configuración `WantedBy=multi-user.target` hará que el servicio se inicie cuando el sistema Linux llegue a "nivel 2", lo que significa que un shell multiusuario no gráfico está activo.</span><span class="sxs-lookup"><span data-stu-id="653f0-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="653f0-147">Antes de que `systemd` reconozca el servicio, debe volver a cargar su configuración.</span><span class="sxs-lookup"><span data-stu-id="653f0-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="653f0-148">Puede controlar `systemd` mediante el comando `systemctl`.</span><span class="sxs-lookup"><span data-stu-id="653f0-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="653f0-149">Después de volver a cargar, use el subcomando `status` para confirmar que la aplicación se ha registrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="653f0-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="653f0-150">Si ha configurado el servicio correctamente, obtendrá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="653f0-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="653f0-151">Use el comando `start` para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="653f0-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="653f0-152">La extensión `.service` es opcional cuando se usa `systemctl start`.</span><span class="sxs-lookup"><span data-stu-id="653f0-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="653f0-153">Para indicar a `systemd` que inicie el servicio automáticamente al iniciar el sistema, use el comando `enable`.</span><span class="sxs-lookup"><span data-stu-id="653f0-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="653f0-154">Registrar en el diario</span><span class="sxs-lookup"><span data-stu-id="653f0-154">Log to journald</span></span>

<span data-ttu-id="653f0-155">El equivalente de Linux del registro de eventos de Windows es `journald`, un servicio de sistema de registro estructurado que forma parte de `systemd`.</span><span class="sxs-lookup"><span data-stu-id="653f0-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="653f0-156">Los mensajes de registro que se escriben en la salida estándar mediante un demonio de Linux se escriben automáticamente en `journald`.</span><span class="sxs-lookup"><span data-stu-id="653f0-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="653f0-157">Para configurar los niveles de registro, use la sección `Console` de la configuración de registro.</span><span class="sxs-lookup"><span data-stu-id="653f0-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="653f0-158">El método del generador de host de `UseSystemd` configura automáticamente el formato de salida de la consola para que se adapte al diario.</span><span class="sxs-lookup"><span data-stu-id="653f0-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="653f0-159">Dado que `journald` es el estándar para los registros de Linux, hay una variedad de herramientas que se integran con él.</span><span class="sxs-lookup"><span data-stu-id="653f0-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="653f0-160">Puede enrutar fácilmente los registros desde `journald` a un sistema de registro externo.</span><span class="sxs-lookup"><span data-stu-id="653f0-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="653f0-161">Al trabajar localmente en el host, puede usar el comando `journalctl` para ver los registros desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="653f0-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="653f0-162">Si tiene un entorno de GUI disponible en el host, algunos visores de registros gráficos están disponibles para Linux, como *QJournalctl* y *GNOME-logs*.</span><span class="sxs-lookup"><span data-stu-id="653f0-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="653f0-163">Para obtener más información acerca de cómo consultar el diario de `systemd` desde la línea de comandos mediante `journalctl`, vea [las páginas del comando man](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="653f0-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="653f0-164">Certificados HTTPS para aplicaciones autohospedadas</span><span class="sxs-lookup"><span data-stu-id="653f0-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="653f0-165">Al ejecutar una aplicación de gRPC en producción, debe usar un certificado TLS de una entidad de certificación (CA) de confianza.</span><span class="sxs-lookup"><span data-stu-id="653f0-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="653f0-166">Esta CA puede ser una CA pública o una interna para su organización.</span><span class="sxs-lookup"><span data-stu-id="653f0-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="653f0-167">En los hosts de Windows, puede cargar el certificado desde un [almacén de certificados](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) seguro mediante la clase <xref:System.Security.Cryptography.X509Certificates.X509Store>.</span><span class="sxs-lookup"><span data-stu-id="653f0-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="653f0-168">También puede usar la clase `X509Store` con el almacén de claves de OpenSSL en algunos hosts de Linux.</span><span class="sxs-lookup"><span data-stu-id="653f0-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="653f0-169">También puede crear certificados con uno de los [constructores X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), desde:</span><span class="sxs-lookup"><span data-stu-id="653f0-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="653f0-170">Un archivo, como un archivo `.pfx` protegido mediante una contraseña segura</span><span class="sxs-lookup"><span data-stu-id="653f0-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="653f0-171">Datos binarios recuperados de un servicio de almacenamiento seguro como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="653f0-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="653f0-172">Puede configurar Kestrel para usar un certificado de dos maneras: desde la configuración o en el código.</span><span class="sxs-lookup"><span data-stu-id="653f0-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="653f0-173">Establecer certificados HTTPS mediante la configuración</span><span class="sxs-lookup"><span data-stu-id="653f0-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="653f0-174">El enfoque de configuración requiere establecer la ruta de acceso al archivo `.pfx` del certificado y la contraseña en la sección de configuración Kestrel.</span><span class="sxs-lookup"><span data-stu-id="653f0-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="653f0-175">En `appsettings.json`, tendría el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="653f0-175">In `appsettings.json`, that would look like this:</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="653f0-176">Proporcione la contraseña mediante un origen de configuración seguro, como Azure Key Vault o el almacén Hashicorp.</span><span class="sxs-lookup"><span data-stu-id="653f0-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="653f0-177">No almacene contraseñas sin cifrar en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="653f0-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="653f0-178">Establecimiento de certificados HTTPS en el código</span><span class="sxs-lookup"><span data-stu-id="653f0-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="653f0-179">Para configurar HTTPS en Kestrel en el código, use el método `ConfigureKestrel` en `IWebHostBuilder` en la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="653f0-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="653f0-180">De nuevo, asegúrese de almacenar la contraseña del archivo de `.pfx` en y recuperarlo de un origen de configuración seguro.</span><span class="sxs-lookup"><span data-stu-id="653f0-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="653f0-181">[Anterior](grpc-in-production.md)
>[Siguiente](docker.md)</span><span class="sxs-lookup"><span data-stu-id="653f0-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
