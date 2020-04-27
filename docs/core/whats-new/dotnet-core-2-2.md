---
title: Novedades de .NET Core 2.2
description: Obtenga información sobre las características nuevas de .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: 64cb561acd72ff5d4a11fcae7ce59eaad750f74e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644370"
---
# <a name="whats-new-in-net-core-22"></a>Novedades de .NET Core 2.2

.NET Core 2.2 incluye mejoras en la implementación de aplicaciones, en el control de eventos de los servicios en tiempo de ejecución, en la autenticación de bases de datos SQL de Azure, en el rendimiento del compilador JIT y la inyección de código antes de la ejecución del método `Main`.

## <a name="new-deployment-mode"></a>Nuevo modo de implementación

A partir de .NET Core 2.2, puede implementar [archivos ejecutables dependientes del marco](../deploying/index.md#publish-runtime-dependent), que son archivos **.exe** en lugar de **.dll**. Los archivos ejecutable dependientes del marco (FDE), que funcionan de forma similar a las implementaciones dependientes del marco, todavía se basan en la presencia de una versión compartida por todo el sistema de .NET Core para ejecutar. Su aplicación contiene solo el código y cualquier dependencia de terceros. A diferencia de las implementaciones dependientes del marco, los FDE son específicos de la plataforma.

Este nuevo modo de implementación tiene la ventaja de compilar un archivo ejecutable en lugar de una biblioteca, lo que significa que puede ejecutar la aplicación directamente sin invocar `dotnet` primero.

## <a name="core"></a>Principal

**Control de eventos en los servicios en tiempo de ejecución**

A menudo es posible que desee supervisar el uso que hace la aplicación de los servicios de tiempo de ejecución, como GC, JIT y ThreadPool, para comprender cómo afectan a la aplicación. En los sistemas Windows, esto se hace normalmente mediante la supervisión de los eventos ETW del proceso actual. Aunque este método sigue funcionando bien, no siempre es posible usar ETW si la ejecución se realiza en un entorno con pocos privilegios o en Linux o macOS.

A partir de .NET Core 2.2, ahora se pueden consumir eventos CoreCLR utilizando la clase <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>. Estos eventos describen el comportamiento de esos servicios en tiempo de ejecución como la interoperabilidad, ThreadPool, JIT y GC. Estos son los mismos eventos que se exponen como parte del proveedor ETW de CoreCLR.  De esta forma, las aplicaciones pueden consumir estos eventos o usar un mecanismo de transporte para enviarlos a un servicio de agregación de telemetría. Puede ver cómo suscribirse a eventos en el código de ejemplo siguiente:

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

Además, .NET Core 2.2 agrega las dos propiedades siguientes a la clase <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> para proporcionar información adicional sobre los eventos ETW:

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a>Datos

**Autenticación de AAD en bases de datos SQL de Azure con la propiedad SqlConnection.AccessToken**

A partir de .NET Core 2.2, puede usarse un token de acceso emitido por Azure Active Directory para autenticarse en una base de datos SQL de Azure. Para admitir tokens de acceso, la propiedad <xref:System.Data.SqlClient.SqlConnection.AccessToken> se ha agregado a la clase <xref:System.Data.SqlClient.SqlConnection>. Para aprovechar las ventajas de la autenticación de AAD, descargue la versión 4.6 del paquete System.Data.SqlClient NuGet. Para poder usar la característica, puede obtener el valor del token de acceso mediante la [biblioteca de autenticación de Active Directory para .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contenida en el paquete NuGet [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

## <a name="jit-compiler-improvements"></a>Mejoras del compilador JIT

**La compilación en niveles sigue siendo una característica opcional**

En .NET Core 2.1, el compilador JIT implementó una nueva tecnología de compilador, la *compilación en niveles*, como característica opcional. El objetivo de la compilación en niveles es mejorar el rendimiento. Una de las tareas importantes realizadas por el compilador JIT es optimizar la ejecución de código. Sin embargo, para las rutas de código poco utilizadas, el compilador puede dedicar más tiempo a la optimización del código del que dedica el tiempo de ejecución al ejecutar el código no optimizado. La compilación por niveles incluye dos fases en la compilación JIT:

- Un **primer nivel**, que genera código tan pronto como sea posible.

- Un **segundo nivel**, que genera código optimizado para los métodos que se ejecutan con frecuencia. El segundo nivel de la compilación se realiza en paralelo para mejorar el rendimiento.

Para obtener información sobre la mejora del rendimiento que puede obtenerse gracias a la compilación en niveles, vea [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/) (Anuncio de la versión preliminar 2 de .NET Core 2.2).

En la versión preliminar 2 de .NET Core 2.2, la compilación en niveles se habilitó de forma predeterminada. Sin embargo, hemos decidido que aún no estamos listos para habilitar la compilación en niveles de forma predeterminada. Por tanto, en .NET Core 2.2, la compilación en nieves sigue siendo una característica opcional. Para obtener información sobre cómo usar la compilación en niveles, vea [Mejoras del compilador JIT](dotnet-core-2-1.md#jit-compiler-improvements) en [Novedades de .NET Core 2.1](dotnet-core-2-1.md).

## <a name="runtime"></a>Tiempo de ejecución

**Inyección de código antes de ejecutar el método Main**

A partir de .NET Core 2.2, puede usar un enlace de inicio para inyectar código antes de ejecutar el método Main de la aplicación. Los enlaces de inicio permiten a un host personalizar el comportamiento de las aplicaciones una vez que se hayan implementado sin necesidad de volver a compilar o cambiar la aplicación.

Los proveedores de hospedaje deberían definir la directiva y la configuración personalizadas, incluida la configuración que posiblemente influya en el comportamiento de carga del punto de entrada principal, como el comportamiento  <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> . El enlace puede usarse para configurar la inyección de telemetría o el seguimiento, configurar las devoluciones de llamada para el control, así como definir otros comportamientos dependientes del entorno. El enlace es independiente del punto de entrada, por lo que no es necesario modificar el código de usuario.

Consulte [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) (Hospedaje del enlace de inicio) para obtener más información.

## <a name="see-also"></a>Vea también

- [Novedades de .NET Core 3.1](dotnet-core-3-1.md)
- [Novedades de ASP.NET Core 2.2](/aspnet/core/release-notes/aspnetcore-2.2)
- [Novedades de EF Core 2.2](/ef/core/what-is-new/ef-core-2.2)
