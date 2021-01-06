---
title: 'Aplicaciones autohospedadas de gRPC: gRPC para desarrolladores de WCF'
description: Implementación de aplicaciones de ASP.NET Core gRPC como servicios autohospedados.
ms.date: 12/15/2020
ms.openlocfilehash: a5e2316b8d76593f4eb53760d2609b5bbbc9d2c5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938538"
---
# <a name="self-hosted-grpc-applications"></a>Aplicaciones autohospedadas de gRPC

Aunque las aplicaciones ASP.NET Core 5,0 se pueden hospedar en IIS en Windows Server, actualmente no es posible hospedar una aplicación gRPC en IIS porque no se admiten algunas de las funcionalidades de HTTP/2. Esta funcionalidad es un objetivo para una futura actualización de Windows Server.

Puede ejecutar la aplicación como un servicio de Windows. O bien, puede ejecutarlo como un servicio de Linux controlado por el [sistema](https://en.wikipedia.org/wiki/Systemd), debido a las nuevas características de las extensiones de hospedaje de .net 5,0.

## <a name="run-your-app-as-a-windows-service"></a>Ejecutar la aplicación como un servicio de Windows

Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Windows, instale el paquete [Microsoft. Extensions. Hosting. WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) de NuGet. A continuación, agregue una llamada a `UseWindowsService` al `CreateHostBuilder` método en `Program.cs` .

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
> Si la aplicación no se está ejecutando como un servicio de Windows, el `UseWindowsService` método no hace nada.

Ahora, publique la aplicación mediante uno de estos métodos:

* En Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **publicar** en el menú contextual.
* Desde la CLI de .NET.

Al publicar una aplicación .NET, puede optar por crear una implementación *dependiente del marco* o una implementación *autocontenida* . Las implementaciones dependientes del marco requieren que el entorno de tiempo de ejecución compartido de .NET esté instalado en el host donde se ejecutan. Las implementaciones independientes se publican con una copia completa del entorno de tiempo de ejecución de .NET y el marco de trabajo, y se pueden ejecutar en cualquier host. Para obtener más información, incluidas las ventajas y desventajas de cada método, consulte la documentación de [implementación de aplicaciones .net](../../core/deploying/index.md) .

Para publicar una compilación independiente de la aplicación que no requiere la instalación del tiempo de ejecución de .NET 5,0 en el host, especifique el tiempo de ejecución que se va a incluir con la aplicación. Use la `-r` marca (o `--runtime` ).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Para publicar una compilación dependiente del marco, omita la `-r` marca.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Copie el contenido completo del `publish` directorio en una carpeta de instalación. A continuación, use la [herramienta SC](/windows/desktop/services/controlling-a-service-using-sc) para crear un servicio de Windows para el archivo ejecutable.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Registro en el registro de eventos de Windows

El `UseWindowsService` método agrega automáticamente un proveedor de [registro](/aspnet/core/fundamentals/logging/) que escribe mensajes de registro en el registro de eventos de Windows. Puede configurar el registro para este proveedor agregando una `EventLog` entrada a la `Logging` sección de `appsettings.json` u otro origen de configuración.

Puede invalidar el nombre de origen utilizado en el registro de eventos estableciendo una `SourceName` propiedad en esta configuración. Si no especifica un nombre, se usará el nombre predeterminado de la aplicación (normalmente el nombre del ensamblado ejecutable).

Al final de este capítulo encontrará más información sobre el registro.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Ejecución de la aplicación como un servicio de Linux con systemd

Para configurar la aplicación de ASP.NET Core para que se ejecute como un servicio de Linux (o *demonio* en la jerga de Linux), instale el paquete de [Microsoft.Extensions.Hosting.SysTEMD](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) desde NuGet. A continuación, agregue una llamada a `UseSystemd` al `CreateHostBuilder` método en `Program.cs` .

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
> Si la aplicación no se está ejecutando como un servicio de Linux, el `UseSystemd` método no hace nada.

Publique la aplicación ahora. La aplicación puede ser dependiente del marco de trabajo o independiente para el tiempo de ejecución de Linux pertinente (por ejemplo, `linux-x64` ). Puede publicar mediante uno de estos métodos:

* En Visual Studio, haga clic con el botón derecho en el proyecto y seleccione **publicar** en el menú contextual.
* En la CLI de .NET, use el siguiente comando:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
Copie el contenido completo del `publish` directorio en una carpeta de instalación del host de Linux. El registro del servicio requiere que se agregue al directorio un archivo especial, denominado *archivo de unidad* `/etc/systemd/system` . Necesitará el permiso raíz para crear un archivo en esta carpeta. Asigne al archivo el nombre que desee `systemd` usar y la `.service` extensión. Por ejemplo, use `/etc/systemd/system/myapp.service`.

El archivo de servicio usa el formato INI, tal como se muestra en este ejemplo:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

La `Type=notify` propiedad indica `systemd` que la aplicación se lo notificará en el inicio y el apagado. La `WantedBy=multi-user.target` configuración hará que el servicio se inicie cuando el sistema Linux alcance "nivel 2", lo que significa que un shell de varios usuarios no gráfico está activo.

Antes `systemd` de que reconozca el servicio, debe volver a cargar su configuración. Puede controlar mediante `systemd` el `systemctl` comando. Después de volver a cargar, use el `status` subcomando para confirmar que la aplicación se ha registrado correctamente.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Si ha configurado el servicio correctamente, obtendrá el siguiente resultado:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Use el `start` comando para iniciar el servicio.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> La `.service` extensión es opcional cuando se usa `systemctl start` .

Para indicar `systemd` a que inicie el servicio automáticamente en el inicio del sistema, use el `enable` comando.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Registrar en el diario

El equivalente de Linux del registro de eventos de Windows es `journald` , un servicio de sistema de registro estructurado que forma parte de `systemd` . Los mensajes de registro que se escriben en la salida estándar mediante un demonio de Linux se escriben automáticamente en `journald` . Para configurar los niveles de registro, use la `Console` sección de la configuración de registro. El `UseSystemd` método del generador de hosts configura automáticamente el formato de salida de la consola para que se adapte al diario.

Dado que `journald` es el estándar para los registros de Linux, se integra una gran variedad de herramientas. Puede enrutar fácilmente los registros desde `journald` a un sistema de registro externo. Al trabajar localmente en el host, puede usar el `journalctl` comando para ver los registros desde la línea de comandos.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Si tiene un entorno de GUI disponible en el host, algunos visores de registros gráficos están disponibles para Linux, como *QJournalctl* y *GNOME-logs*.

Para obtener más información sobre cómo consultar el `systemd` diario desde la línea de comandos mediante `journalctl` , vea [las páginas](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificados HTTPS para aplicaciones autohospedadas

Al ejecutar una aplicación de gRPC en producción, debe usar un certificado TLS de una entidad de certificación (CA) de confianza. Esta CA puede ser una CA pública o una interna para su organización.

En los hosts de Windows, puede cargar el certificado desde un [almacén de certificados](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) seguro mediante la <xref:System.Security.Cryptography.X509Certificates.X509Store> clase. También puede usar la `X509Store` clase con el almacén de claves de OpenSSL en algunos hosts de Linux.

También puede crear certificados con uno de los [constructores X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), desde:

* Un archivo, como un `.pfx` archivo protegido por una contraseña segura
* Datos binarios recuperados de un servicio de almacenamiento seguro como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)

Puede configurar Kestrel para usar un certificado de dos maneras: desde la configuración o en el código.

### <a name="set-https-certificates-by-using-configuration"></a>Establecer certificados HTTPS mediante la configuración

El enfoque de configuración requiere establecer la ruta de acceso al archivo de certificado `.pfx` y la contraseña en la sección de configuración Kestrel. En `appsettings.json` , tendrá el siguiente aspecto:

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

Proporcione la contraseña mediante un origen de configuración seguro, como Azure Key Vault o el almacén Hashicorp.

> [!IMPORTANT]
> No almacene contraseñas sin cifrar en archivos de configuración.

### <a name="set-https-certificates-in-code"></a>Establecimiento de certificados HTTPS en el código

Para configurar HTTPS en Kestrel en el código, use el `ConfigureKestrel` método en `IWebHostBuilder` la `Program` clase.

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

De nuevo, asegúrese de almacenar la contraseña del `.pfx` archivo en y recuperarlo de un origen de configuración seguro.

>[!div class="step-by-step"]
>[Anterior](grpc-in-production.md)
>[Siguiente](docker.md)
