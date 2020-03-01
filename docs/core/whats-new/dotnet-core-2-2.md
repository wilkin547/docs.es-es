---
title: Novedades de .NET Core 2.2
description: Obtenga información sobre las características nuevas de .NET Core 2.2.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: e045c39240c99777d05ca86ee0a8cd1fa4309c4f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156587"
---
# <a name="whats-new-in-net-core-22"></a><span data-ttu-id="4b44e-103">Novedades de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="4b44e-103">What's new in .NET Core 2.2</span></span>

<span data-ttu-id="4b44e-104">.NET Core 2.2 incluye mejoras en la implementación de aplicaciones, en el control de eventos de los servicios en tiempo de ejecución, en la autenticación de bases de datos SQL de Azure, en el rendimiento del compilador JIT y la inyección de código antes de la ejecución del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="4b44e-104">.NET Core 2.2 includes enhancements in application deployment, event handling for runtime services, authentication to Azure SQL databases, JIT compiler performance, and code injection prior to the execution of the `Main` method.</span></span>

## <a name="new-deployment-mode"></a><span data-ttu-id="4b44e-105">Nuevo modo de implementación</span><span class="sxs-lookup"><span data-stu-id="4b44e-105">New deployment mode</span></span>

<span data-ttu-id="4b44e-106">A partir de .NET Core 2.2, puede implementar [archivos ejecutables dependientes del marco](../deploying/index.md#publish-runtime-dependent), que son archivos **.exe** en lugar de **.dll**.</span><span class="sxs-lookup"><span data-stu-id="4b44e-106">Starting with .NET Core 2.2, you can deploy [framework-dependent executables](../deploying/index.md#publish-runtime-dependent), which are **.exe** files instead of **.dll** files.</span></span> <span data-ttu-id="4b44e-107">Los archivos ejecutable dependientes del marco (FDE), que funcionan de forma similar a las implementaciones dependientes del marco, todavía se basan en la presencia de una versión compartida por todo el sistema de .NET Core para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4b44e-107">Functionally similar to framework-dependent deployments, framework-dependent executables (FDE) still rely on the presence of a shared system-wide version of .NET Core to run.</span></span> <span data-ttu-id="4b44e-108">Su aplicación contiene solo el código y cualquier dependencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="4b44e-108">Your app contains only your code and any third-party dependencies.</span></span> <span data-ttu-id="4b44e-109">A diferencia de las implementaciones dependientes del marco, los FDE son específicos de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="4b44e-109">Unlike framework-dependent deployments, FDEs are platform-specific.</span></span>

<span data-ttu-id="4b44e-110">Este nuevo modo de implementación tiene la ventaja de compilar un archivo ejecutable en lugar de una biblioteca, lo que significa que puede ejecutar la aplicación directamente sin invocar `dotnet` primero.</span><span class="sxs-lookup"><span data-stu-id="4b44e-110">This new deployment mode has the distinct advantage of building an executable instead of a library, which means you can run your app directly without invoking `dotnet` first.</span></span>

## <a name="core"></a><span data-ttu-id="4b44e-111">Principal</span><span class="sxs-lookup"><span data-stu-id="4b44e-111">Core</span></span>

<span data-ttu-id="4b44e-112">**Control de eventos en los servicios en tiempo de ejecución**</span><span class="sxs-lookup"><span data-stu-id="4b44e-112">**Handling events in runtime services**</span></span>

<span data-ttu-id="4b44e-113">A menudo es posible que desee supervisar el uso que hace la aplicación de los servicios de tiempo de ejecución, como GC, JIT y ThreadPool, para comprender cómo afectan a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b44e-113">You may often want to monitor your application's use of runtime services, such as the GC, JIT, and ThreadPool, to understand how they impact your application.</span></span><span data-ttu-id="4b44e-114"> En los sistemas Windows, esto se hace normalmente mediante la supervisión de los eventos ETW del proceso actual.</span><span class="sxs-lookup"><span data-stu-id="4b44e-114"> On Windows systems, this is commonly done by monitoring the ETW events of the current process.</span></span><span data-ttu-id="4b44e-115"> Aunque este método sigue funcionando bien, no siempre es posible usar ETW si la ejecución se realiza en un entorno con pocos privilegios o en Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="4b44e-115"> While this continues to work well, it's not always possible to use ETW if you're running in a low-privilege environment or on Linux or macOS.</span></span>

<span data-ttu-id="4b44e-116">A partir de .NET Core 2.2, ahora se pueden consumir eventos CoreCLR utilizando la clase <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b44e-116">Starting with .NET Core 2.2, CoreCLR events can now be consumed using the <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4b44e-117">Estos eventos describen el comportamiento de esos servicios en tiempo de ejecución como la interoperabilidad, ThreadPool, JIT y GC.</span><span class="sxs-lookup"><span data-stu-id="4b44e-117">These events describe the behavior of such runtime services as GC, JIT, ThreadPool, and interop.</span></span> <span data-ttu-id="4b44e-118">Estos son los mismos eventos que se exponen como parte del proveedor ETW de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4b44e-118">These are the same events that are exposed as part of the CoreCLR ETW provider.</span></span><span data-ttu-id="4b44e-119">  De esta forma, las aplicaciones pueden consumir estos eventos o usar un mecanismo de transporte para enviarlos a un servicio de agregación de telemetría.</span><span class="sxs-lookup"><span data-stu-id="4b44e-119">  This allows for applications to consume these events or use a transport mechanism to send them to a telemetry aggregation service.</span></span> <span data-ttu-id="4b44e-120">Puede ver cómo suscribirse a eventos en el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b44e-120">You can see how to subscribe to events in the following code sample:</span></span>

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

<span data-ttu-id="4b44e-121">Además, .NET Core 2.2 agrega las dos propiedades siguientes a la clase <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> para proporcionar información adicional sobre los eventos ETW:</span><span class="sxs-lookup"><span data-stu-id="4b44e-121">In addition, .NET Core 2.2 adds the following two properties to the <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> class to provide additional information about ETW events:</span></span>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a><span data-ttu-id="4b44e-122">Datos</span><span class="sxs-lookup"><span data-stu-id="4b44e-122">Data</span></span>

<span data-ttu-id="4b44e-123">**Autenticación de AAD en bases de datos SQL de Azure con la propiedad SqlConnection.AccessToken**</span><span class="sxs-lookup"><span data-stu-id="4b44e-123">**AAD authentication to Azure SQL databases with the SqlConnection.AccessToken property**</span></span>

<span data-ttu-id="4b44e-124">A partir de .NET Core 2.2, puede usarse un token de acceso emitido por Azure Active Directory para autenticarse en una base de datos SQL de Azure.</span><span class="sxs-lookup"><span data-stu-id="4b44e-124">Starting with .NET Core 2.2, an access token issued by Azure Active Directory can be used to authenticate to an Azure SQL database.</span></span> <span data-ttu-id="4b44e-125">Para admitir tokens de acceso, la propiedad <xref:System.Data.SqlClient.SqlConnection.AccessToken> se ha agregado a la clase <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="4b44e-125">To support access tokens, the <xref:System.Data.SqlClient.SqlConnection.AccessToken> property has been added to the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="4b44e-126">Para aprovechar las ventajas de la autenticación de AAD, descargue la versión 4.6 del paquete System.Data.SqlClient NuGet.</span><span class="sxs-lookup"><span data-stu-id="4b44e-126">To take advantage of AAD authentication, download version 4.6 of the System.Data.SqlClient NuGet package.</span></span> <span data-ttu-id="4b44e-127">Para poder usar la característica, puede obtener el valor del token de acceso mediante la [biblioteca de autenticación de Active Directory para .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contenida en el paquete NuGet [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="4b44e-127">In order to use the feature, you can obtain the access token value using the [Active Directory Authentication Library for .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contained in the [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet package.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="4b44e-128">Mejoras del compilador JIT</span><span class="sxs-lookup"><span data-stu-id="4b44e-128">JIT compiler improvements</span></span>

<span data-ttu-id="4b44e-129">**La compilación en niveles sigue siendo una característica opcional**</span><span class="sxs-lookup"><span data-stu-id="4b44e-129">**Tiered compilation remains an opt-in feature**</span></span>

<span data-ttu-id="4b44e-130">En .NET Core 2.1, el compilador JIT implementó una nueva tecnología de compilador, la *compilación en niveles*, como característica opcional.</span><span class="sxs-lookup"><span data-stu-id="4b44e-130">In .NET Core 2.1, the JIT compiler implemented a new compiler technology, *tiered compilation*, as an opt-in feature.</span></span> <span data-ttu-id="4b44e-131">El objetivo de la compilación en niveles es mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4b44e-131">The goal of tiered compilation is improved performance.</span></span> <span data-ttu-id="4b44e-132">Una de las tareas importantes realizadas por el compilador JIT es optimizar la ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="4b44e-132">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="4b44e-133">Sin embargo, para las rutas de código poco utilizadas, el compilador puede dedicar más tiempo a la optimización del código del que dedica el tiempo de ejecución al ejecutar el código no optimizado.</span><span class="sxs-lookup"><span data-stu-id="4b44e-133">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends executing unoptimized code.</span></span> <span data-ttu-id="4b44e-134">La compilación por niveles incluye dos fases en la compilación JIT:</span><span class="sxs-lookup"><span data-stu-id="4b44e-134">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="4b44e-135">Un **primer nivel**, que genera código tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="4b44e-135">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="4b44e-136">Un **segundo nivel**, que genera código optimizado para los métodos que se ejecutan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="4b44e-136">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="4b44e-137">El segundo nivel de la compilación se realiza en paralelo para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4b44e-137">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="4b44e-138">Para obtener información sobre la mejora del rendimiento que puede obtenerse gracias a la compilación en niveles, vea [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/) (Anuncio de la versión preliminar 2 de .NET Core 2.2).</span><span class="sxs-lookup"><span data-stu-id="4b44e-138">For information on the performance improvement that can result from tiered compilation, see [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span>

<span data-ttu-id="4b44e-139">En la versión preliminar 2 de .NET Core 2.2, la compilación en niveles se habilitó de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b44e-139">In .NET Core 2.2 Preview 2, tiered compilation was enabled by default.</span></span> <span data-ttu-id="4b44e-140">Sin embargo, hemos decidido que aún no estamos listos para habilitar la compilación en niveles de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b44e-140">However, we've decided that we are still not ready to enable tiered compilation by default.</span></span> <span data-ttu-id="4b44e-141">Por tanto, en .NET Core 2.2, la compilación en nieves sigue siendo una característica opcional.</span><span class="sxs-lookup"><span data-stu-id="4b44e-141">So in .NET Core 2.2, tiered compilation continues to be an opt-in feature.</span></span> <span data-ttu-id="4b44e-142">Para obtener información sobre cómo usar la compilación en niveles, vea [Mejoras del compilador JIT](dotnet-core-2-1.md#jit-compiler-improvements) en [Novedades de .NET Core 2.1](dotnet-core-2-1.md).</span><span class="sxs-lookup"><span data-stu-id="4b44e-142">For information on opting in to tiered compilation, see [Jit compiler improvements](dotnet-core-2-1.md#jit-compiler-improvements) in [What's new in .NET Core 2.1](dotnet-core-2-1.md).</span></span>

## <a name="runtime"></a><span data-ttu-id="4b44e-143">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4b44e-143">Runtime</span></span>

<span data-ttu-id="4b44e-144">**Inyección de código antes de ejecutar el método Main**</span><span class="sxs-lookup"><span data-stu-id="4b44e-144">**Injecting code prior to executing the Main method**</span></span>

<span data-ttu-id="4b44e-145">A partir de .NET Core 2.2, puede usar un enlace de inicio para inyectar código antes de ejecutar el método Main de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b44e-145">Starting with .NET Core 2.2, you can use a startup hook to inject code prior to running an application's Main method.</span></span> <span data-ttu-id="4b44e-146">Los enlaces de inicio permiten a un host personalizar el comportamiento de las aplicaciones una vez que se hayan implementado sin necesidad de volver a compilar o cambiar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b44e-146">Startup hooks make it possible for a host to customize the behavior of applications after they have been deployed without needing to recompile or change the application.</span></span>

<span data-ttu-id="4b44e-147">Los proveedores de hospedaje deberían definir la directiva y la configuración personalizadas, incluida la configuración que posiblemente influya en el comportamiento de carga del punto de entrada principal, como el comportamiento  <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4b44e-147">We expect hosting providers to define custom configuration and policy, including settings that potentially influence the load behavior of the main entry point, such as the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> behavior.</span></span> <span data-ttu-id="4b44e-148">El enlace puede usarse para configurar la inyección de telemetría o el seguimiento, configurar las devoluciones de llamada para el control, así como definir otros comportamientos dependientes del entorno.</span><span class="sxs-lookup"><span data-stu-id="4b44e-148">The hook can be used to set up tracing or telemetry injection, to set up callbacks for handling, or to define other environment-dependent behavior.</span></span> <span data-ttu-id="4b44e-149">El enlace es independiente del punto de entrada, por lo que no es necesario modificar el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="4b44e-149">The hook is separate from the entry point, so that user code doesn't need to be modified.</span></span>

<span data-ttu-id="4b44e-150">Consulte [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) (Hospedaje del enlace de inicio) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4b44e-150">See [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b44e-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b44e-151">See also</span></span>

- [<span data-ttu-id="4b44e-152">Novedades de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4b44e-152">What's new in .NET Core</span></span>](index.md)
- [<span data-ttu-id="4b44e-153">Novedades de ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="4b44e-153">What's new in ASP.NET Core 2.2</span></span>](/aspnet/core/release-notes/aspnetcore-2.2)
- [<span data-ttu-id="4b44e-154">Novedades de EF Core 2.2</span><span class="sxs-lookup"><span data-stu-id="4b44e-154">New features in EF Core 2.2</span></span>](/ef/core/what-is-new/ef-core-2.2)
