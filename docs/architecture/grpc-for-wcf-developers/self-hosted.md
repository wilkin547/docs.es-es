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
# <a name="self-hosted-grpc-applications"></a>Aplicaciones gRPC autohospedadas

Aunque ASP.NET aplicaciones DeCore 3.0 se pueden hospedar en IIS en Windows Server, actualmente no es posible hospedar una aplicación gRPC en IIS porque no se admite parte de la funcionalidad HTTP/2. Esta funcionalidad es un objetivo para una futura actualización de Windows Server.

Puede ejecutar la aplicación como un servicio de Windows. O bien, puede ejecutarlo como un servicio Linux controlado por [systemd](https://en.wikipedia.org/wiki/Systemd), debido a las nuevas características de las extensiones de hospedaje de .NET Core 3.0.

## <a name="run-your-app-as-a-windows-service"></a>Ejecute la aplicación como un servicio de Windows

Para configurar la aplicación ASP.NET Core para que se ejecute como un servicio de Windows, instale el paquete [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) desde NuGet. A continuación, `UseWindowsService` agregue `CreateHostBuilder` una `Program.cs`llamada al método en .

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
> Si la aplicación no se ejecuta como `UseWindowsService` un servicio de Windows, el método no hace nada.

Ahora publique la aplicación mediante uno de estos métodos:

* Desde Visual Studio haciendo clic con el botón derecho en el proyecto y seleccionando **Publicar** en el menú contextual.
* Desde la CLI de .NET Core.

Al publicar una aplicación de .NET Core, puede elegir crear una implementación *dependiente del marco* de trabajo o una implementación *independiente.* Las implementaciones dependientes de Framework requieren que el tiempo de ejecución compartido de .NET Core se instale en el host donde se ejecutan. Las implementaciones independientes se publican con una copia completa del tiempo de ejecución y el marco de trabajo de .NET Core y se pueden ejecutar en cualquier host. Para obtener más información, incluidas las ventajas y desventajas de cada enfoque, consulte la documentación de implementación de la [aplicación .NET Core.](../../core/deploying/index.md)

Para publicar una compilación independiente de la aplicación que no requiera que el tiempo de ejecución de .NET Core 3.0 se instale en el host, especifique el tiempo de ejecución que se incluirá con la aplicación. Utilice `-r` la `--runtime`marca (o).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Para publicar una compilación dependiente `-r` del marco de trabajo, omita la marca.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Copie el contenido `publish` completo del directorio en una carpeta de instalación. A continuación, utilice la [herramienta sc](/windows/desktop/services/controlling-a-service-using-sc) para crear un servicio de Windows para el archivo ejecutable.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Inicie sesión en el registro de eventos de Windows

El `UseWindowsService` método agrega automáticamente un proveedor de [registro](/aspnet/core/fundamentals/logging/) que escribe mensajes de registro en el registro de eventos de Windows. Puede configurar el registro para `EventLog` este proveedor `Logging` agregando una entrada a la sección de u otro origen de `appsettings.json` configuración.

Puede invalidar el nombre de origen utilizado `SourceName` en el registro de eventos estableciendo una propiedad en esta configuración. Si no especifica un nombre, se utilizará el nombre de aplicación predeterminado (normalmente el nombre del ensamblado ejecutable).

Más información sobre el registro está al final de este capítulo.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Ejecute la aplicación como un servicio Linux con systemd

Para configurar la aplicación ASP.NET Core para que se ejecute como un servicio Linux (o *daemon* en el lenguaje Linux), instale el paquete [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) desde NuGet. A continuación, `UseSystemd` agregue `CreateHostBuilder` una `Program.cs`llamada al método en .

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
> Si la aplicación no se ejecuta como `UseSystemd` un servicio Linux, el método no hace nada.

Ahora publique su aplicación. La aplicación puede ser dependiente del marco de trabajo o independiente `linux-x64`para el tiempo de ejecución de Linux relevante (por ejemplo, ). Puede publicar mediante uno de estos métodos:

* Desde Visual Studio haciendo clic con el botón derecho en el proyecto y seleccionando **Publicar** en el menú contextual.
* Desde la CLI de .NET Core, mediante el siguiente comando:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
Copie el contenido `publish` completo del directorio en una carpeta de instalación en el host Linux. El registro del servicio requiere que se agregue un archivo `/etc/systemd/system` especial, denominado archivo de *unidad,* al directorio. Necesitará permiso de root para crear un archivo en esta carpeta. Asigne al archivo el nombre `systemd` con el `.service` identificador que desea usar y la extensión. Por ejemplo, use `/etc/systemd/system/myapp.service`.

El archivo de servicio utiliza el formato INI, tal y como se muestra en de este ejemplo:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

La `Type=notify` propiedad `systemd` indica que la aplicación le notificará al iniciar y apagar. La `WantedBy=multi-user.target` configuración hará que el servicio se inicie cuando el sistema Linux alcance el "nivel de ejecución 2", lo que significa que un shell multiusuario no gráfico está activo.

Antes `systemd` de reconocer el servicio, necesita volver a cargar su configuración. Puede `systemd` controlar mediante `systemctl` el comando. Después de volver `status` a cargar, utilice el subcomando para confirmar que la aplicación se ha registrado correctamente.

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

Utilice `start` el comando para iniciar el servicio.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> La `.service` extensión es opcional cuando `systemctl start`se utiliza .

Para `systemd` indicar que se inicie el servicio `enable` automáticamente al iniciar el sistema, utilice el comando.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Registro en diario

El equivalente de Linux del `journald`registro de eventos de Windows `systemd`es , un servicio de sistema de registro estructurado que forma parte de . Los mensajes de registro escritos en la `journald`salida estándar por un demonio Linux se escriben automáticamente en . Para configurar los niveles `Console` de registro, utilice la sección de la configuración de registro. El `UseSystemd` método del generador de hosts configura automáticamente el formato de salida de la consola para que se adapte al diario.

Debido `journald` a que es el estándar para los registros de Linux, una variedad de herramientas se integran con él. Puede enrutar fácilmente `journald` los registros desde un sistema de registro externo. Al trabajar localmente en el `journalctl` host, puede utilizar el comando para ver los registros de la línea de comandos.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Si tiene un entorno GUI disponible en el host, algunos visores de registrográficos están disponibles para Linux, como *QJournalctl* y *gnome-logs*.

Para obtener más información `systemd` sobre cómo consultar `journalctl`el diario desde la línea de comandos mediante , consulte [las páginas de comando man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>Certificados HTTPS para aplicaciones autohospedadas

Cuando ejecute una aplicación gRPC en producción, debe usar un certificado TLS de una entidad de certificación (CA) de confianza. Esta CA puede ser una CA pública o una ca interna para su organización.

En hosts de Windows, puede cargar el certificado <xref:System.Security.Cryptography.X509Certificates.X509Store> desde un [almacén](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) de certificados seguro mediante la clase. También puede utilizar `X509Store` la clase con el almacén de claves OpenSSL en algunos hosts Linux.

También puede crear certificados mediante uno de los [constructores X509Certificate2,](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)desde:

* Un archivo, como `.pfx` un archivo protegido por una contraseña segura
* Datos binarios recuperados de un servicio de almacenamiento seguro como [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)

Puede configurar Kestrel para que use un certificado de dos maneras: desde la configuración o en el código.

### <a name="set-https-certificates-by-using-configuration"></a>Establecer certificados HTTPS mediante la configuración

El enfoque de configuración requiere establecer `.pfx` la ruta de acceso al archivo de certificado y la contraseña en la sección de configuración de Kestrel. En `appsettings.json`, que se vería así:

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

Proporcione la contraseña mediante un origen de configuración seguro como Azure Key Vault o Hashicorp Vault.

> [!IMPORTANT]
> No almacene contraseñas sin cifrar en archivos de configuración.

### <a name="set-https-certificates-in-code"></a>Establecer certificados HTTPS en código

Para configurar HTTPS en Kestrel `ConfigureKestrel` en `IWebHostBuilder` el `Program` código, utilice el método on en la clase.

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

Una vez más, asegúrese `.pfx` de almacenar la contraseña del archivo y recuperarla de un origen de configuración seguro.

>[!div class="step-by-step"]
>[Anterior](grpc-in-production.md)
>[Siguiente](docker.md)
