---
title: Aplicaciones gRPC autohospedadas - gRPC para desarrolladores de WCF
description: Implementación de aplicaciones gRPC ASP.NET Core como servicios autohospedados.
ms.date: 09/02/2019
ms.openlocfilehash: 69f70e4077247fd07eba7abeee82f257dd1f4f90
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110911"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="bd762-103">Aplicaciones gRPC autohospedadas</span><span class="sxs-lookup"><span data-stu-id="bd762-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="bd762-104">Aunque ASP.NET aplicaciones DeCore 3.0 se pueden hospedar en IIS en Windows Server, actualmente no es posible hospedar una aplicación gRPC en IIS porque no se admite parte de la funcionalidad HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="bd762-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="bd762-105">Esta funcionalidad es un objetivo para una futura actualización de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bd762-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="bd762-106">Puede ejecutar la aplicación como un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="bd762-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="bd762-107">O bien, puede ejecutarlo como un servicio Linux controlado por [systemd](https://en.wikipedia.org/wiki/Systemd), debido a las nuevas características de las extensiones de hospedaje de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="bd762-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="bd762-108">Ejecute la aplicación como un servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="bd762-108">Run your app as a Windows service</span></span>

<span data-ttu-id="bd762-109">Para configurar la aplicación ASP.NET Core para que se ejecute como un servicio de Windows, instale el paquete [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) desde NuGet.</span><span class="sxs-lookup"><span data-stu-id="bd762-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="bd762-110">A continuación, `UseWindowsService` agregue `CreateHostBuilder` una `Program.cs`llamada al método en .</span><span class="sxs-lookup"><span data-stu-id="bd762-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="bd762-111">Si la aplicación no se ejecuta como `UseWindowsService` un servicio de Windows, el método no hace nada.</span><span class="sxs-lookup"><span data-stu-id="bd762-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="bd762-112">Ahora publique la aplicación mediante uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="bd762-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="bd762-113">Desde Visual Studio haciendo clic con el botón derecho en el proyecto y seleccionando **Publicar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="bd762-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="bd762-114">Desde la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd762-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="bd762-115">Al publicar una aplicación de .NET Core, puede elegir crear una implementación *dependiente del marco* de trabajo o una implementación *independiente.*</span><span class="sxs-lookup"><span data-stu-id="bd762-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="bd762-116">Las implementaciones dependientes de Framework requieren que el tiempo de ejecución compartido de .NET Core se instale en el host donde se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="bd762-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="bd762-117">Las implementaciones independientes se publican con una copia completa del tiempo de ejecución y el marco de trabajo de .NET Core y se pueden ejecutar en cualquier host.</span><span class="sxs-lookup"><span data-stu-id="bd762-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="bd762-118">Para obtener más información, incluidas las ventajas y desventajas de cada enfoque, consulte la documentación de implementación de la [aplicación .NET Core.](../../core/deploying/index.md)</span><span class="sxs-lookup"><span data-stu-id="bd762-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="bd762-119">Para publicar una compilación independiente de la aplicación que no requiera que el tiempo de ejecución de .NET Core 3.0 se instale en el host, especifique el tiempo de ejecución que se incluirá con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd762-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="bd762-120">Utilice `-r` la `--runtime`marca (o).</span><span class="sxs-lookup"><span data-stu-id="bd762-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="bd762-121">Para publicar una compilación dependiente `-r` del marco de trabajo, omita la marca.</span><span class="sxs-lookup"><span data-stu-id="bd762-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="bd762-122">Copie el contenido `publish` completo del directorio en una carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="bd762-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="bd762-123">A continuación, utilice la [herramienta sc](/windows/desktop/services/controlling-a-service-using-sc) para crear un servicio de Windows para el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="bd762-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="bd762-124">Inicie sesión en el registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="bd762-124">Log to the Windows event log</span></span>

<span data-ttu-id="bd762-125">El `UseWindowsService` método agrega automáticamente un proveedor de [registro](/aspnet/core/fundamentals/logging/) que escribe mensajes de registro en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="bd762-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="bd762-126">Puede configurar el registro para `EventLog` este proveedor `Logging` agregando una entrada a la sección de u otro origen de `appsettings.json` configuración.</span><span class="sxs-lookup"><span data-stu-id="bd762-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="bd762-127">Puede invalidar el nombre de origen utilizado `SourceName` en el registro de eventos estableciendo una propiedad en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="bd762-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="bd762-128">Si no especifica un nombre, se utilizará el nombre de aplicación predeterminado (normalmente el nombre del ensamblado ejecutable).</span><span class="sxs-lookup"><span data-stu-id="bd762-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="bd762-129">Más información sobre el registro está al final de este capítulo.</span><span class="sxs-lookup"><span data-stu-id="bd762-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="bd762-130">Ejecute la aplicación como un servicio Linux con systemd</span><span class="sxs-lookup"><span data-stu-id="bd762-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="bd762-131">Para configurar la aplicación ASP.NET Core para que se ejecute como un servicio Linux (o *daemon* en el lenguaje Linux), instale el paquete [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) desde NuGet.</span><span class="sxs-lookup"><span data-stu-id="bd762-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="bd762-132">A continuación, `UseSystemd` agregue `CreateHostBuilder` una `Program.cs`llamada al método en .</span><span class="sxs-lookup"><span data-stu-id="bd762-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="bd762-133">Si la aplicación no se ejecuta como `UseSystemd` un servicio Linux, el método no hace nada.</span><span class="sxs-lookup"><span data-stu-id="bd762-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="bd762-134">Ahora publique su aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd762-134">Now publish your application.</span></span> <span data-ttu-id="bd762-135">La aplicación puede ser dependiente del marco de trabajo o independiente `linux-x64`para el tiempo de ejecución de Linux relevante (por ejemplo, ).</span><span class="sxs-lookup"><span data-stu-id="bd762-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="bd762-136">Puede publicar mediante uno de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="bd762-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="bd762-137">Desde Visual Studio haciendo clic con el botón derecho en el proyecto y seleccionando **Publicar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="bd762-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="bd762-138">Desde la CLI de .NET Core, mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bd762-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="bd762-139">Copie el contenido `publish` completo del directorio en una carpeta de instalación en el host Linux.</span><span class="sxs-lookup"><span data-stu-id="bd762-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="bd762-140">El registro del servicio requiere que se agregue un archivo `/etc/systemd/system` especial, denominado archivo de *unidad,* al directorio.</span><span class="sxs-lookup"><span data-stu-id="bd762-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="bd762-141">Necesitará permiso de root para crear un archivo en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="bd762-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="bd762-142">Asigne al archivo el nombre `systemd` con el `.service` identificador que desea usar y la extensión.</span><span class="sxs-lookup"><span data-stu-id="bd762-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="bd762-143">Por ejemplo, use `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="bd762-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="bd762-144">El archivo de servicio utiliza el formato INI, tal y como se muestra en de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd762-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="bd762-145">La `Type=notify` propiedad `systemd` indica que la aplicación le notificará al iniciar y apagar.</span><span class="sxs-lookup"><span data-stu-id="bd762-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="bd762-146">La `WantedBy=multi-user.target` configuración hará que el servicio se inicie cuando el sistema Linux alcance el "nivel de ejecución 2", lo que significa que un shell multiusuario no gráfico está activo.</span><span class="sxs-lookup"><span data-stu-id="bd762-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical, multi-user shell is active.</span></span>

<span data-ttu-id="bd762-147">Antes `systemd` de reconocer el servicio, necesita volver a cargar su configuración.</span><span class="sxs-lookup"><span data-stu-id="bd762-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="bd762-148">Puede `systemd` controlar mediante `systemctl` el comando.</span><span class="sxs-lookup"><span data-stu-id="bd762-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="bd762-149">Después de volver `status` a cargar, utilice el subcomando para confirmar que la aplicación se ha registrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd762-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="bd762-150">Si ha configurado el servicio correctamente, obtendrá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="bd762-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="bd762-151">Utilice `start` el comando para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bd762-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="bd762-152">La `.service` extensión es opcional cuando `systemctl start`se utiliza .</span><span class="sxs-lookup"><span data-stu-id="bd762-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="bd762-153">Para `systemd` indicar que se inicie el servicio `enable` automáticamente al iniciar el sistema, utilice el comando.</span><span class="sxs-lookup"><span data-stu-id="bd762-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="bd762-154">Registro en diario</span><span class="sxs-lookup"><span data-stu-id="bd762-154">Log to journald</span></span>

<span data-ttu-id="bd762-155">El equivalente de Linux del `journald`registro de eventos de Windows `systemd`es , un servicio de sistema de registro estructurado que forma parte de .</span><span class="sxs-lookup"><span data-stu-id="bd762-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="bd762-156">Los mensajes de registro escritos en la `journald`salida estándar por un demonio Linux se escriben automáticamente en .</span><span class="sxs-lookup"><span data-stu-id="bd762-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="bd762-157">Para configurar los niveles `Console` de registro, utilice la sección de la configuración de registro.</span><span class="sxs-lookup"><span data-stu-id="bd762-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="bd762-158">El `UseSystemd` método del generador de hosts configura automáticamente el formato de salida de la consola para que se adapte al diario.</span><span class="sxs-lookup"><span data-stu-id="bd762-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="bd762-159">Debido `journald` a que es el estándar para los registros de Linux, una variedad de herramientas se integran con él.</span><span class="sxs-lookup"><span data-stu-id="bd762-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="bd762-160">Puede enrutar fácilmente `journald` los registros desde un sistema de registro externo.</span><span class="sxs-lookup"><span data-stu-id="bd762-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="bd762-161">Al trabajar localmente en el `journalctl` host, puede utilizar el comando para ver los registros de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bd762-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="bd762-162">Si tiene un entorno GUI disponible en el host, algunos visores de registrográficos están disponibles para Linux, como *QJournalctl* y *gnome-logs*.</span><span class="sxs-lookup"><span data-stu-id="bd762-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="bd762-163">Para obtener más información `systemd` sobre cómo consultar `journalctl`el diario desde la línea de comandos mediante , consulte [las páginas de comando man](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="bd762-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="bd762-164">Certificados HTTPS para aplicaciones autohospedadas</span><span class="sxs-lookup"><span data-stu-id="bd762-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="bd762-165">Cuando ejecute una aplicación gRPC en producción, debe usar un certificado TLS de una entidad de certificación (CA) de confianza.</span><span class="sxs-lookup"><span data-stu-id="bd762-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="bd762-166">Esta CA puede ser una CA pública o una ca interna para su organización.</span><span class="sxs-lookup"><span data-stu-id="bd762-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="bd762-167">En hosts de Windows, puede cargar el certificado <xref:System.Security.Cryptography.X509Certificates.X509Store> desde un [almacén](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) de certificados seguro mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="bd762-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="bd762-168">También puede utilizar `X509Store` la clase con el almacén de claves OpenSSL en algunos hosts Linux.</span><span class="sxs-lookup"><span data-stu-id="bd762-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="bd762-169">También puede crear certificados mediante uno de los [constructores X509Certificate2,](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)desde:</span><span class="sxs-lookup"><span data-stu-id="bd762-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="bd762-170">Un archivo, como `.pfx` un archivo protegido por una contraseña segura</span><span class="sxs-lookup"><span data-stu-id="bd762-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="bd762-171">Datos binarios recuperados de un servicio de almacenamiento seguro como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="bd762-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="bd762-172">Puede configurar Kestrel para que use un certificado de dos maneras: desde la configuración o en el código.</span><span class="sxs-lookup"><span data-stu-id="bd762-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="bd762-173">Establecer certificados HTTPS mediante la configuración</span><span class="sxs-lookup"><span data-stu-id="bd762-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="bd762-174">El enfoque de configuración requiere establecer `.pfx` la ruta de acceso al archivo de certificado y la contraseña en la sección de configuración de Kestrel.</span><span class="sxs-lookup"><span data-stu-id="bd762-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="bd762-175">En `appsettings.json`, que se vería así:</span><span class="sxs-lookup"><span data-stu-id="bd762-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="bd762-176">Proporcione la contraseña mediante un origen de configuración seguro como Azure Key Vault o Hashicorp Vault.</span><span class="sxs-lookup"><span data-stu-id="bd762-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd762-177">No almacene contraseñas sin cifrar en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="bd762-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="bd762-178">Establecer certificados HTTPS en código</span><span class="sxs-lookup"><span data-stu-id="bd762-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="bd762-179">Para configurar HTTPS en Kestrel `ConfigureKestrel` en `IWebHostBuilder` el `Program` código, utilice el método on en la clase.</span><span class="sxs-lookup"><span data-stu-id="bd762-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="bd762-180">Una vez más, asegúrese `.pfx` de almacenar la contraseña del archivo y recuperarla de un origen de configuración seguro.</span><span class="sxs-lookup"><span data-stu-id="bd762-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bd762-181">[Anterior](grpc-in-production.md)
>[Siguiente](docker.md)</span><span class="sxs-lookup"><span data-stu-id="bd762-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
