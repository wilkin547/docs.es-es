---
title: Host genérico de .NET
author: IEvangelist
description: Obtenga información sobre el host genérico de .NET, que es responsable de la administración de inicio y duración de la aplicación.
ms.author: dapine
ms.date: 12/18/2020
ms.openlocfilehash: bf6d5ad624bbed46994633abace0af64712757f3
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "102402199"
---
# <a name="net-generic-host"></a>Host genérico de .NET

Las plantillas de servicio de trabajo crean un host genérico de .NET, <xref:Microsoft.Extensions.Hosting.HostBuilder>. El host genérico se puede usar con otros tipos de aplicaciones .NET, como aplicaciones de consola.

El *host* es un objeto que encapsula todos los recursos de la aplicación, como:

- Inserción de dependencias (ID)
- Registro
- Configuración
- Implementaciones de `IHostedService`

Cuando se inicia un host, llama a <xref:Microsoft.Extensions.Hosting.IHostedService.StartAsync%2A?displayProperty=nameWithType> en cada implementación de <xref:Microsoft.Extensions.Hosting.IHostedService> registrada en la colección de servicios hospedados del contenedor de servicios. En una aplicación de servicio de trabajo, todas las implementaciones de `IHostedService` que contienen instancias de <xref:Microsoft.Extensions.Hosting.BackgroundService> tienen los métodos <xref:Microsoft.Extensions.Hosting.BackgroundService.ExecuteAsync%2A?displayProperty=nameWithType> a los que se llama.

La razón principal para incluir todos los recursos interdependientes de la aplicación en un objeto es la administración de la duración: el control sobre el inicio de la aplicación y el apagado estable. Esto se logra con el paquete NuGet [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting).

## <a name="set-up-a-host"></a>Configuración de un host

Normalmente se configura, compila y ejecuta el host por el código de la clase `Program`. El método `Main` realiza las acciones siguientes:

- Llama a un método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder> para crear y configurar un objeto del generador.
- Llama a <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> para crear una instancia de <xref:Microsoft.Extensions.Hosting.IHost>.
- Llama al método <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.Run%2A> o <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.RunAsync%2A> en el objeto host.

Las plantillas de servicio de trabajo de .NET generan el código siguiente para crear un host genérico:

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureServices((hostContext, services) =>
            {
                services.AddHostedService<Worker>();
            });
}
```

## <a name="default-builder-settings"></a>Configuración predeterminada del generador

El método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> realiza las acciones siguientes:

- Establece la raíz de contenido en la ruta de acceso devuelta por <xref:System.IO.Directory.GetCurrentDirectory>.
- Carga la [configuración de host](#host-configuration) de:
  - Variables de entorno con el prefijo `DOTNET_`.
  - Argumentos de la línea de comandos.
- Carga la configuración de aplicación de:
  - *appsettings.json*.
  - *appsettings.{Environment}.json*.
  - Administrador de secretos, cuando la aplicación se ejecuta en el entorno `Development`.
  - Variables de entorno.
  - Argumentos de la línea de comandos.
- Agrega los siguientes proveedores de registro:
  - Consola
  - Depuración
  - EventSource
  - EventLog (solo si se ejecuta en Windows)
- Permite la validación del ámbito y la [validación de dependencias](xref:Microsoft.Extensions.DependencyInjection.ServiceProviderOptions.ValidateOnBuild) si el entorno es `Development`.

El método `ConfigureServices` expone la capacidad de agregar servicios a la instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection?displayProperty=nameWithType>. Más adelante, estos servicios se pueden poner a disposición de la inserción de dependencias.

## <a name="framework-provided-services"></a>Servicios proporcionados por el marco de trabajo

Los servicios siguientes se registran de forma automática:

- [IHostApplicationLifetime](#ihostapplicationlifetime)
- [IHostLifetime](#ihostlifetime)
- [IHostEnvironment](#ihostenvironment)

## <a name="ihostapplicationlifetime"></a>IHostApplicationLifetime

Permite insertar el servicio <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime> en cualquier clase para controlar las tareas posteriores al inicio y el cierre estable. Tres de las propiedades de la interfaz son tokens de cancelación que se usan para registrar los métodos del controlador de eventos de inicio y detención de las aplicaciones. La interfaz también incluye un método <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication>.

El ejemplo siguiente es una implementación de `IHostedService` que registra los eventos `IHostApplicationLifetime`:

:::code language="csharp" source="snippets/configuration/app-lifetime/ExampleHostedService.cs" highlight="18-20":::

La plantilla de servicio de trabajo se puede modificar para agregar la implementación de `ExampleHostedService`:

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="1-16,36" highlight="15":::

La aplicación escribiría la siguiente salida de ejemplo:

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="17-35":::

## <a name="ihostlifetime"></a>IHostLifetime

La implementación de <xref:Microsoft.Extensions.Hosting.IHostLifetime> controla cuándo se inicia el host y cuándo se detiene. Se usa la última implementación registrada.

`Microsoft.Extensions.Hosting.Internal.ConsoleLifetime` es la implementación predeterminada de `IHostLifetime`. `ConsoleLifetime`:

- Escucha <kbd>Ctrl</kbd>+<kbd>C</kbd>, [SIGINT](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGINT) o [SIGTERM](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM), y llama a <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication%2A> para iniciar el proceso de apagado.
- Desbloquea extensiones como `RunAsync` y `WaitForShutdownAsync`.

## <a name="ihostenvironment"></a>IHostEnvironment

Permite insertar el servicio <xref:Microsoft.Extensions.Hosting.IHostEnvironment> en una clase para obtener información sobre los valores siguientes:

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ApplicationName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootFileProvider?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootPath?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.EnvironmentName?displayProperty=nameWithType>

## <a name="host-configuration"></a>Configuración de host

La configuración de host se usa para configurar las propiedades de la implementación de [IHostEnvironment](#ihostenvironment).

La configuración de host está disponible en [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration) dentro del método <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A>. Al llamar al método `ConfigureAppConfiguration`, `HostBuilderContext` y `IConfigurationBuilder` se pasan a `configureDelegate`. `configureDelegate` se define como `Action<HostBuilderContext, IConfigurationBuilder>`. El contexto del generador de hosts expone la propiedad `.Configuration`, que es una instancia de `IConfiguration`. Representa la configuración generada a partir del host, mientras que `IConfigurationBuilder` es el objeto de generador que se usa para configurar la aplicación.

> [!TIP]
> Después de llamar a `ConfigureAppConfiguration`, `HostBuilderContext.Configuration` se reemplaza por la [configuración de la aplicación](#app-configuration).

Para agregar la configuración de host, llame a <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureHostConfiguration%2A> en `IHostBuilder`. Se puede llamar varias veces a `ConfigureHostConfiguration` con resultados de suma. El host usa cualquier opción que establezca un valor en último lugar en una clave determinada.

En el ejemplo siguiente se crea la configuración de host:

:::code language="csharp" source="snippets/configuration/console-host/Program.cs" highlight="19-25":::

## <a name="app-configuration"></a>Configuración de aplicaciones

La configuración de la aplicación se crea llamando a <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> en `IHostBuilder`. Se puede llamar varias veces a `ConfigureAppConfiguration` con resultados de suma. La aplicación usa cualquier opción que establezca un valor en último lugar en una clave determinada.

La configuración creada por `ConfigureAppConfiguration` está disponible en [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration%2A) para las operaciones posteriores y como servicio de ID. La configuración de host también se agrega a la configuración de la aplicación.

Para obtener más información, vea [Configuración en .NET](configuration.md).

## <a name="see-also"></a>Vea también

- [Configuración en .NET](configuration.md)
- [Host web de ASP.NET Core](/aspnet/core/fundamentals/host/web-host)
- Los errores del host genérico deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).
