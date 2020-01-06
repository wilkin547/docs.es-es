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
# <a name="self-hosted-grpc-applications"></a>Aplicaciones autohospedadas de gRPC

Aunque las aplicaciones ASP.NET Core 3,0 se pueden hospedar en IIS en Windows Server, actualmente no es posible hospedar una aplicación de gRPC en IIS porque algunas de las funcionalidades de HTTP/2 todavía no se admiten. Esta funcionalidad se espera en una actualización futura de Windows Server.

Puede ejecutar la aplicación como un servicio de Windows o como un servicio de Linux controlado por [systemd](https://en.wikipedia.org/wiki/Systemd), gracias a algunas características nuevas de las extensiones de hospedaje de .net Core 3,0.

## <a name="run-your-app-as-a-windows-service"></a>Ejecutar la aplicación como un servicio de Windows

Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Windows, instale el paquete [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) de NuGet. A continuación, agregue una llamada a `UseWindowsService` al método `CreateHostBuilder` en `Program.cs`.

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
> Si la aplicación no se está ejecutando como un servicio de Windows, el método `UseWindowsService` no hace nada.

Publique la aplicación, ya sea desde Visual Studio; para ello, haga clic con el botón derecho en el proyecto y elija *publicar* en el menú contextual o en el CLI de .net Core.

Al publicar una aplicación de .NET Core, puede crear una implementación *dependiente del marco* o una implementación *autocontenida* . Las implementaciones dependientes del marco requieren que el entorno de tiempo de ejecución compartido de .NET Core esté instalado en el host donde se ejecutan. Las implementaciones independientes se publican con una copia completa del entorno de ejecución y el marco de trabajo de .NET Core y se pueden ejecutar en cualquier host. Para obtener más información, incluidas las ventajas y desventajas de cada método, consulte la documentación de [implementación de aplicaciones .net Core](../../core/deploying/index.md) .

Para publicar una compilación independiente de la aplicación que no requiere la instalación del tiempo de ejecución de .NET Core 3,0 en el host, especifique el tiempo de ejecución que se va a incluir con la aplicación mediante la marca `-r` (o `--runtime`).

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

Para publicar una compilación dependiente del marco, omita la marca `-r`.

```console
dotnet publish -c Release -o ./publish
```

Copie el contenido completo del directorio `publish` en una carpeta de instalación y use la [utilidad SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) para crear un servicio de Windows para el ejecutable.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a>Registrar en el registro de eventos de Windows

El método `UseWindowsService` agrega automáticamente un proveedor de [registro](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) que escribe mensajes de registro en el registro de eventos de Windows. Puede configurar el registro para este proveedor agregando una entrada `EventLog` a la sección `Logging` de `appsettings.json` u otro origen de configuración. El nombre de origen utilizado en el registro de eventos se puede invalidar estableciendo una propiedad `SourceName` en esta configuración. Si no especifica un nombre, se usará el nombre predeterminado de la aplicación (normalmente el nombre del ensamblado ejecutable).

Al final de este capítulo encontrará más información sobre el registro.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Ejecución de la aplicación como un servicio de Linux con systemd

Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Linux (o *demonio* en la jerga de Linux), instale el paquete [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) desde NuGet. A continuación, agregue una llamada a `UseSystemd` al método `CreateHostBuilder` en `Program.cs`.

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
> Si la aplicación no se está ejecutando como un servicio de Linux, el método `UseSystemd` no hace nada.

Publique la aplicación (ya sea dependiente del marco o independiente para el tiempo de ejecución de Linux relevante, por ejemplo, `linux-x64`), desde Visual Studio; para ello, haga clic con el botón derecho en el proyecto y elija *publicar* en el menú contextual, o bien desde el CLI de .net Core con el siguiente comando.

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

Copie el contenido completo del directorio `publish` en una carpeta de instalación del host de Linux. El registro del servicio requiere un archivo especial, denominado "archivo de unidad", que se va a agregar al directorio de `/etc/systemd/system`. Necesitará el permiso raíz para crear un archivo en esta carpeta. Asigne al archivo el nombre que desee `systemd` usar y la extensión `.service`. Por ejemplo: `/etc/systemd/system/myapp.service`.

El archivo de servicio usa el formato INI, tal como se muestra en este ejemplo.

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

La propiedad `Type=notify` indica `systemd` que la aplicación le notificará en el inicio y el apagado. El valor `WantedBy=multi-user.target` hará que el servicio se inicie cuando el sistema Linux llegue a "nivel 2", lo que significa que un shell multiusuario no gráfico está activo.

Antes de que `systemd` reconozca el servicio, debe volver a cargar su configuración. Puede controlar `systemd` mediante el comando `systemctl`. Después de volver a cargar, use el subcomando `status` para confirmar que la aplicación se ha registrado correctamente.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Si ha configurado el servicio correctamente, se mostrará el siguiente resultado:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Use el comando `start` para iniciar el servicio.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> La extensión `.service` es opcional cuando se usa `systemctl start`.

Para indicar a `systemd` que inicie el servicio automáticamente al iniciar el sistema, use el comando `enable`.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Registrar en el diario

El equivalente de Linux del registro de eventos de Windows es `journald`, un servicio de sistema de registro estructurado que forma parte de `systemd`. Los mensajes de registro que se escriben en la salida estándar mediante un demonio de Linux se escriben automáticamente en `journald`, por lo que para configurar los niveles de registro, use la sección `Console` de la configuración de registro. El método del generador de host de `UseSystemd` configura automáticamente el formato de salida de la consola para que se adapte al diario.

Dado que `journald` es el estándar para los registros de Linux, hay una variedad de herramientas que se integran con él, y puede enrutar fácilmente los registros de `journald` a un sistema de registro externo. Al trabajar localmente en el host, puede usar el comando `journalctl` para ver los registros desde la línea de comandos.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Si tiene un entorno de GUI disponible en el host, algunos visores de registros gráficos están disponibles para Linux, como *QJournalctl* y *GNOME-logs*.

Para obtener más información sobre cómo consultar el diario systemd desde la línea de comandos con `journalctl`, vea [las páginas del comando man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificados HTTPS para aplicaciones autohospedadas

Al ejecutar una aplicación de gRPC en producción, debe usar un certificado TLS de una entidad de certificación (CA) de confianza. Esta entidad de certificación puede ser una entidad de certificación pública o una interna para su organización.

En los hosts de Windows, el certificado se puede cargar desde un [almacén de certificados](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) seguro mediante la clase <xref:System.Security.Cryptography.X509Certificates.X509Store>. La clase `X509Store` también se puede usar con el almacén de claves de OpenSSL en algunos hosts de Linux.

Los certificados también se pueden crear con uno de los [constructores X509Certificate2](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), ya sea desde un archivo (por ejemplo, un archivo `.pfx` protegido mediante una contraseña segura) o desde datos binarios recuperados de un servicio de almacenamiento seguro como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).

Kestrel se puede configurar para usar un certificado de dos maneras: desde la configuración o en el código.

### <a name="set-https-certificates-using-configuration"></a>Establecer certificados HTTPS mediante la configuración

El enfoque de configuración requiere establecer la ruta de acceso al archivo `.pfx` del certificado y la contraseña en la sección de configuración Kestrel. En `appsettings.json` tendrá este aspecto.

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

La contraseña debe proporcionarse mediante un origen de configuración seguro como Azure KeyVault o Hashicorp Vault.

NO debe almacenar contraseñas no cifradas en los archivos de configuración.

### <a name="set-https-certificates-in-code"></a>Establecimiento de certificados HTTPS en el código

Para configurar HTTPS en Kestrel en el código, use el método `ConfigureKestrel` en `IWebHostBuilder` en la clase `Program`.

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

Una vez más, la contraseña para el archivo `.pfx` se debe almacenar y recuperar de un origen de configuración seguro.

>[!div class="step-by-step"]
>[Anterior](grpc-in-production.md)
>[Siguiente](docker.md)
