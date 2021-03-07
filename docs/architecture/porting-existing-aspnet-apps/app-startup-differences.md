---
title: Diferencias de inicio de la aplicación entre ASP.NET MVC y ASP.NET Core
description: ASP.NET MVC y ASP.NET Core difieren significativamente en el modo en que se inician las aplicaciones. Obtenga información sobre las diferencias importantes y cómo migrar de ASP.NET MVC a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: eaf8d8fac42ddebbb944273b672666e0bd2b1a67
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401824"
---
# <a name="app-startup-differences-between-aspnet-mvc-and-aspnet-core"></a>Diferencias de inicio de la aplicación entre ASP.NET MVC y ASP.NET Core

La vida de las aplicaciones ASP.NET MVC en Internet Information Server (IIS), el servidor web principal está disponible en los sistemas operativos Windows. A diferencia de ASP.NET MVC, las aplicaciones ASP.NET Core son aplicaciones ejecutables. Puede ejecutarlos desde la línea de comandos mediante `dotnet run` . Tienen un método de punto de entrada como todos los programas de C#, normalmente `public static void Main()` o una variación similar (quizás con argumentos o `async` soporte técnico). Tal vez sea la mayor diferencia arquitectónica entre ASP.NET Core y ASP.NET MVC, y es una de las diversas diferencias que permiten que ASP.NET Core se ejecute en sistemas que no son de Windows.

## <a name="aspnet-mvc-startup"></a>Inicio de ASP.NET MVC

Hospedado en IIS, las aplicaciones de ASP.NET confían en IIS para crear instancias de determinados objetos y llamar a determinados métodos cuando llega una solicitud. ASP.NET crea una instancia de la clase del archivo *global. asax* , que deriva de `HttpApplication` . Cuando se recibe la primera solicitud, antes de controlar la solicitud, ASP.NET llama al `Application_Start` método en la clase del archivo *global. asax* . Cualquier lógica que deba ejecutarse cuando se inicie la aplicación ASP.NET MVC puede agregarse a este método.

Muchos paquetes NuGet para ASP.NET MVC y Web API usan el paquete [webactivator](https://github.com/davidebbo/WebActivator) para permitirles ejecutar código durante el inicio de la aplicación. Por Convención, este código normalmente se agregaría a una carpeta *App_Start* y se configuraría mediante el atributo para ejecutarse inmediatamente antes o justo después `Application_Start` .

También es posible usar [Open Web Interface for .net (OWIN) y Project Katana con ASP.NET MVC](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana). Al hacerlo, la aplicación incluirá un archivo *Startup.CS* que es responsable de configurar el middleware de solicitudes de una manera muy similar a la forma en que se comporta ASP.net Core.

Si necesita ejecutar código cuando se inicia la aplicación ASP.NET MVC, normalmente usará uno de estos métodos.

## <a name="aspnet-core-startup"></a>Inicio de ASP.NET Core

Como se indicó anteriormente, ASP.NET Core aplicaciones son programas independientes. Por lo tanto, normalmente incluyen un archivo *Program.CS* que contiene el punto de entrada de la aplicación. En la figura 2-1 se muestra un ejemplo típico de este archivo.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

**Figura 2-1**. Un archivo ASP.NET Core *Program.CS* típico.

El código que se muestra en la figura 2-1 crea un *host* para la aplicación, lo compila y lo ejecuta. La aplicación ASP.NET Core se ejecuta en el host configurado por el `IHostBuilder` mostrado. Aunque es posible configurar por completo una aplicación ASP.NET Core mediante `IHostBuilder` , normalmente la mayor parte de este trabajo se realiza en una `Startup` clase.

La `Startup` clase expone dos métodos al host: `ConfigureServices` y `Configure` . El `ConfigureServices` método se usa para definir los servicios que la aplicación usará y sus respectivas duraciones. El `Configure` método se usa para definir cómo se administrará cada solicitud a la aplicación mediante la configuración de una canalización de solicitud formada por middleware.

Además del código relacionado con la configuración de los servicios de la aplicación o la canalización de solicitudes, las aplicaciones pueden tener otro código que se debe ejecutar cuando se inicia la aplicación. Normalmente, este código se coloca en *Program.CS* o se registra como un `IHostedService` , que lo iniciará el [host genérico](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1) cuando se inicie la aplicación.

La `IHostedService` interfaz simplemente expone dos métodos, `StartAsync` y `StopAsync` . Registra la interfaz en `ConfigureServices` y el host realiza el resto, llamando al `StartAsync` método antes de que se inicie la aplicación.

## <a name="porting-considerations"></a>Consideraciones sobre la migración

Los equipos que desean migrar sus aplicaciones de ASP.NET MVC a ASP.NET Core necesitan identificar qué código se ejecuta cuando se inicia la aplicación y determinar la ubicación adecuada para ese código en su aplicación ASP.NET Core. Para el código personalizado que se debe ejecutar cuando se inicia la aplicación, especialmente el código asincrónico, el enfoque recomendado es normalmente incluir dicho código en `IHostedService` implementaciones.

## <a name="references"></a>Referencias

- [Información general del ciclo de vida de la aplicación ASP.NET para IIS 7](/previous-versions/aspnet/bb470252(v=vs.100))
- [Introducción al ciclo de vida de la aplicación ASP.NET para IIS 5 y 6](/previous-versions/aspnet/ms178473(v=vs.100))
- [Introducción a OWIN y Katana](/aspnet/aspnet/overview/owin-and-katana/getting-started-with-owin-and-katana)
- [Webactivator](https://github.com/davidebbo/WebActivator)
- [Inicio de la aplicación en ASP.NET Core](/aspnet/core/fundamentals/startup?preserve-view=true&view=aspnetcore-3.1)
- [Host genérico de .NET en ASP.NET Core](/aspnet/core/fundamentals/host/generic-host?preserve-view=true&view=aspnetcore-3.1)
- [IHostedService](../microservices/multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)

>[!div class="step-by-step"]
>[Anterior](architectural-differences.md)
>[Siguiente](hosting-differences.md)
