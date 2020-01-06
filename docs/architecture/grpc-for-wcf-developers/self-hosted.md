---
title: 'Aplicaciones autohospedadas de gRPC: gRPC para desarrolladores de WCF'
description: Implementación de aplicaciones de ASP.NET Core gRPC como servicios autohospedados.
ms.date: 09/02/2019
ms.openlocfilehash: 00b4ad50eae629b5b36a890d1eecf7119386c74c
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545068"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="f8ade-103">Aplicaciones autohospedadas de gRPC</span><span class="sxs-lookup"><span data-stu-id="f8ade-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="f8ade-104">Aunque las aplicaciones ASP.NET Core 3,0 se pueden hospedar en IIS en Windows Server, actualmente no es posible hospedar una aplicación de gRPC en IIS porque algunas de las funcionalidades de HTTP/2 todavía no se admiten.</span><span class="sxs-lookup"><span data-stu-id="f8ade-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't yet supported.</span></span> <span data-ttu-id="f8ade-105">Esta funcionalidad se espera en una actualización futura de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f8ade-105">This functionality is expected in a future update to Windows Server.</span></span>

<span data-ttu-id="f8ade-106">Puede ejecutar la aplicación como un servicio de Windows o como un servicio de Linux controlado por [systemd](https://en.wikipedia.org/wiki/Systemd), gracias a algunas características nuevas de las extensiones de hospedaje de .net Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="f8ade-106">You can run your application as a Windows Service, or as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), thanks to some new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="f8ade-107">Ejecutar la aplicación como un servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="f8ade-107">Run your app as a Windows service</span></span>

<span data-ttu-id="f8ade-108">Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Windows, instale el paquete [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) de NuGet.</span><span class="sxs-lookup"><span data-stu-id="f8ade-108">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="f8ade-109">A continuación, agregue una llamada a `UseWindowsService` al método `CreateHostBuilder` en `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-109">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="f8ade-110">Si la aplicación no se está ejecutando como un servicio de Windows, el método `UseWindowsService` no hace nada.</span><span class="sxs-lookup"><span data-stu-id="f8ade-110">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="f8ade-111">Publique la aplicación, ya sea desde Visual Studio; para ello, haga clic con el botón derecho en el proyecto y elija *publicar* en el menú contextual o en el CLI de .net Core.</span><span class="sxs-lookup"><span data-stu-id="f8ade-111">Now publish your application, either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI.</span></span>

<span data-ttu-id="f8ade-112">Al publicar una aplicación de .NET Core, puede crear una implementación *dependiente del marco* o una implementación *autocontenida* .</span><span class="sxs-lookup"><span data-stu-id="f8ade-112">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="f8ade-113">Las implementaciones dependientes del marco requieren que el entorno de tiempo de ejecución compartido de .NET Core esté instalado en el host donde se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="f8ade-113">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="f8ade-114">Las implementaciones independientes se publican con una copia completa del entorno de ejecución y el marco de trabajo de .NET Core y se pueden ejecutar en cualquier host.</span><span class="sxs-lookup"><span data-stu-id="f8ade-114">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="f8ade-115">Para obtener más información, incluidas las ventajas y desventajas de cada método, consulte la documentación de [implementación de aplicaciones .net Core](../../core/deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="f8ade-115">For more information, including the advantages and disadvantages of each approach, refer to the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="f8ade-116">Para publicar una compilación independiente de la aplicación que no requiere la instalación del tiempo de ejecución de .NET Core 3,0 en el host, especifique el tiempo de ejecución que se va a incluir con la aplicación mediante la marca `-r` (o `--runtime`).</span><span class="sxs-lookup"><span data-stu-id="f8ade-116">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application using the `-r` (or `--runtime`) flag.</span></span>

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="f8ade-117">Para publicar una compilación dependiente del marco, omita la marca `-r`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-117">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```console
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="f8ade-118">Copie el contenido completo del directorio `publish` en una carpeta de instalación y use la [utilidad SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) para crear un servicio de Windows para el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="f8ade-118">Copy the complete contents of the `publish` directory to an installation folder, and use the [sc utility](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a><span data-ttu-id="f8ade-119">Registrar en el registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="f8ade-119">Log to Windows Event Log</span></span>

<span data-ttu-id="f8ade-120">El método `UseWindowsService` agrega automáticamente un proveedor de [registro](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) que escribe mensajes de registro en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="f8ade-120">The `UseWindowsService` method automatically adds a [Logging](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) provider that writes log messages to the Windows Event Log.</span></span> <span data-ttu-id="f8ade-121">Puede configurar el registro para este proveedor agregando una entrada `EventLog` a la sección `Logging` de `appsettings.json` u otro origen de configuración.</span><span class="sxs-lookup"><span data-stu-id="f8ade-121">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or other configuration source.</span></span> <span data-ttu-id="f8ade-122">El nombre de origen utilizado en el registro de eventos se puede invalidar estableciendo una propiedad `SourceName` en esta configuración. Si no especifica un nombre, se usará el nombre predeterminado de la aplicación (normalmente el nombre del ensamblado ejecutable).</span><span class="sxs-lookup"><span data-stu-id="f8ade-122">The source name used in Event Log can be overridden by setting a `SourceName` property in these settings; if you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="f8ade-123">Al final de este capítulo encontrará más información sobre el registro.</span><span class="sxs-lookup"><span data-stu-id="f8ade-123">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="f8ade-124">Ejecución de la aplicación como un servicio de Linux con systemd</span><span class="sxs-lookup"><span data-stu-id="f8ade-124">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="f8ade-125">Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Linux (o *demonio* en la jerga de Linux), instale el paquete [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) desde NuGet.</span><span class="sxs-lookup"><span data-stu-id="f8ade-125">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="f8ade-126">A continuación, agregue una llamada a `UseSystemd` al método `CreateHostBuilder` en `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-126">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="f8ade-127">Si la aplicación no se está ejecutando como un servicio de Linux, el método `UseSystemd` no hace nada.</span><span class="sxs-lookup"><span data-stu-id="f8ade-127">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="f8ade-128">Publique la aplicación (ya sea dependiente del marco o independiente para el tiempo de ejecución de Linux relevante, por ejemplo, `linux-x64`), desde Visual Studio; para ello, haga clic con el botón derecho en el proyecto y elija *publicar* en el menú contextual, o bien desde el CLI de .net Core con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="f8ade-128">Now publish your application (either framework-dependent, or self-contained for the relevant Linux runtime, for example, `linux-x64`), either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI using the following command.</span></span>

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

<span data-ttu-id="f8ade-129">Copie el contenido completo del directorio `publish` en una carpeta de instalación del host de Linux.</span><span class="sxs-lookup"><span data-stu-id="f8ade-129">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="f8ade-130">El registro del servicio requiere un archivo especial, denominado "archivo de unidad", que se va a agregar al directorio de `/etc/systemd/system`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-130">Registering the service requires a special file, called a "unit file", to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="f8ade-131">Necesitará el permiso raíz para crear un archivo en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="f8ade-131">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="f8ade-132">Asigne al archivo el nombre que desee `systemd` usar y la extensión `.service`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-132">Name the file with the identifier you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="f8ade-133">Por ejemplo: `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-133">For example, `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="f8ade-134">El archivo de servicio usa el formato INI, tal como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f8ade-134">The service file uses INI format, as shown in this example.</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="f8ade-135">La propiedad `Type=notify` indica `systemd` que la aplicación le notificará en el inicio y el apagado.</span><span class="sxs-lookup"><span data-stu-id="f8ade-135">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="f8ade-136">El valor `WantedBy=multi-user.target` hará que el servicio se inicie cuando el sistema Linux llegue a "nivel 2", lo que significa que un shell multiusuario no gráfico está activo.</span><span class="sxs-lookup"><span data-stu-id="f8ade-136">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2", meaning a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="f8ade-137">Antes de que `systemd` reconozca el servicio, debe volver a cargar su configuración.</span><span class="sxs-lookup"><span data-stu-id="f8ade-137">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="f8ade-138">Puede controlar `systemd` mediante el comando `systemctl`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-138">You control `systemd` using the `systemctl` command.</span></span> <span data-ttu-id="f8ade-139">Después de volver a cargar, use el subcomando `status` para confirmar que la aplicación se ha registrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f8ade-139">After reloading, use the `status` subcommand to confirm the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="f8ade-140">Si ha configurado el servicio correctamente, se mostrará el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f8ade-140">If you've configured the service correctly, the following output will be shown:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="f8ade-141">Use el comando `start` para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f8ade-141">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="f8ade-142">La extensión `.service` es opcional cuando se usa `systemctl start`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-142">The `.service` extension is optional when using `systemctl start`.</span></span>

<span data-ttu-id="f8ade-143">Para indicar a `systemd` que inicie el servicio automáticamente al iniciar el sistema, use el comando `enable`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-143">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="f8ade-144">Registrar en el diario</span><span class="sxs-lookup"><span data-stu-id="f8ade-144">Log to journald</span></span>

<span data-ttu-id="f8ade-145">El equivalente de Linux del registro de eventos de Windows es `journald`, un servicio de sistema de registro estructurado que forma parte de `systemd`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-145">The Linux equivalent of the Windows Event Log is `journald`, a structured logging system service that is part of `systemd`.</span></span> <span data-ttu-id="f8ade-146">Los mensajes de registro que se escriben en la salida estándar mediante un demonio de Linux se escriben automáticamente en `journald`, por lo que para configurar los niveles de registro, use la sección `Console` de la configuración de registro.</span><span class="sxs-lookup"><span data-stu-id="f8ade-146">Log messages written to the standard output by a Linux daemon are automatically written to `journald`, so to configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="f8ade-147">El método del generador de host de `UseSystemd` configura automáticamente el formato de salida de la consola para que se adapte al diario.</span><span class="sxs-lookup"><span data-stu-id="f8ade-147">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="f8ade-148">Dado que `journald` es el estándar para los registros de Linux, hay una variedad de herramientas que se integran con él, y puede enrutar fácilmente los registros de `journald` a un sistema de registro externo.</span><span class="sxs-lookup"><span data-stu-id="f8ade-148">Because `journald` is the standard for Linux logs, there are a variety of tools that integrate with it, and you can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="f8ade-149">Al trabajar localmente en el host, puede usar el comando `journalctl` para ver los registros desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f8ade-149">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="f8ade-150">Si tiene un entorno de GUI disponible en el host, algunos visores de registros gráficos están disponibles para Linux, como *QJournalctl* y *GNOME-logs*.</span><span class="sxs-lookup"><span data-stu-id="f8ade-150">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="f8ade-151">Para obtener más información sobre cómo consultar el diario systemd desde la línea de comandos con `journalctl`, vea [las páginas del comando man](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="f8ade-151">To learn more about querying the systemd journal from the command line with `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="f8ade-152">Certificados HTTPS para aplicaciones autohospedadas</span><span class="sxs-lookup"><span data-stu-id="f8ade-152">HTTPS Certificates for self-hosted applications</span></span>

<span data-ttu-id="f8ade-153">Al ejecutar una aplicación de gRPC en producción, debe usar un certificado TLS de una entidad de certificación (CA) de confianza.</span><span class="sxs-lookup"><span data-stu-id="f8ade-153">When running a gRPC application in production, you should use a TLS certificate from a trusted Certificate Authority (CA).</span></span> <span data-ttu-id="f8ade-154">Esta entidad de certificación puede ser una entidad de certificación pública o una interna para su organización.</span><span class="sxs-lookup"><span data-stu-id="f8ade-154">This CA could be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="f8ade-155">En los hosts de Windows, el certificado se puede cargar desde un [almacén de certificados](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) seguro mediante la clase <xref:System.Security.Cryptography.X509Certificates.X509Store>.</span><span class="sxs-lookup"><span data-stu-id="f8ade-155">On Windows hosts, the certificate may be loaded from a secure [Certificate Store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="f8ade-156">La clase `X509Store` también se puede usar con el almacén de claves de OpenSSL en algunos hosts de Linux.</span><span class="sxs-lookup"><span data-stu-id="f8ade-156">The `X509Store` class can also be used with the OpenSSL key-store on some Linux hosts.</span></span>

<span data-ttu-id="f8ade-157">Los certificados también se pueden crear con uno de los [constructores X509Certificate2](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), ya sea desde un archivo (por ejemplo, un archivo `.pfx` protegido mediante una contraseña segura) o desde datos binarios recuperados de un servicio de almacenamiento seguro como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="f8ade-157">Certificates may also be created using one of the [X509Certificate2 constructors](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), either from a file (for example a `.pfx` file protected by a strong password), or from binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="f8ade-158">Kestrel se puede configurar para usar un certificado de dos maneras: desde la configuración o en el código.</span><span class="sxs-lookup"><span data-stu-id="f8ade-158">Kestrel can be configured to use a certificate in two ways: from configuration, or in code.</span></span>

### <a name="set-https-certificates-using-configuration"></a><span data-ttu-id="f8ade-159">Establecer certificados HTTPS mediante la configuración</span><span class="sxs-lookup"><span data-stu-id="f8ade-159">Set HTTPS certificates using configuration</span></span>

<span data-ttu-id="f8ade-160">El enfoque de configuración requiere establecer la ruta de acceso al archivo `.pfx` del certificado y la contraseña en la sección de configuración Kestrel.</span><span class="sxs-lookup"><span data-stu-id="f8ade-160">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="f8ade-161">En `appsettings.json` tendrá este aspecto.</span><span class="sxs-lookup"><span data-stu-id="f8ade-161">In `appsettings.json` that would look like this.</span></span>

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

<span data-ttu-id="f8ade-162">La contraseña debe proporcionarse mediante un origen de configuración seguro como Azure KeyVault o Hashicorp Vault.</span><span class="sxs-lookup"><span data-stu-id="f8ade-162">The password should be provided using a secure configuration source such as Azure KeyVault or Hashicorp Vault.</span></span>

<span data-ttu-id="f8ade-163">NO debe almacenar contraseñas no cifradas en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="f8ade-163">You SHOULD NOT store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="f8ade-164">Establecimiento de certificados HTTPS en el código</span><span class="sxs-lookup"><span data-stu-id="f8ade-164">Set HTTPS certificates in code</span></span>

<span data-ttu-id="f8ade-165">Para configurar HTTPS en Kestrel en el código, use el método `ConfigureKestrel` en `IWebHostBuilder` en la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="f8ade-165">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="f8ade-166">Una vez más, la contraseña para el archivo `.pfx` se debe almacenar y recuperar de un origen de configuración seguro.</span><span class="sxs-lookup"><span data-stu-id="f8ade-166">Again, the password for the `.pfx` file should be stored in and retrieved from a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f8ade-167">[Anterior](grpc-in-production.md)
>[Siguiente](docker.md)</span><span class="sxs-lookup"><span data-stu-id="f8ade-167">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
