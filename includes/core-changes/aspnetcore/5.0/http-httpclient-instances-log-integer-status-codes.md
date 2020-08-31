---
ms.openlocfilehash: 47f42305f4106f5e05e555a859f13c41bb950519
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811290"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="b9f71-101">HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="b9f71-101">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="b9f71-102">Instancias de <xref:System.Net.Http.HttpClient> creadas como enteros por códigos de estado HTTP del registro de <xref:System.Net.Http.IHttpClientFactory>, en lugar de con nombres de código de estado.</span><span class="sxs-lookup"><span data-stu-id="b9f71-102"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b9f71-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b9f71-103">Version introduced</span></span>

<span data-ttu-id="b9f71-104">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="b9f71-104">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b9f71-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b9f71-105">Old behavior</span></span>

<span data-ttu-id="b9f71-106">El registro usa las descripciones textuales de los códigos de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="b9f71-106">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="b9f71-107">Considere los siguientes mensajes de registro:</span><span class="sxs-lookup"><span data-stu-id="b9f71-107">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a><span data-ttu-id="b9f71-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b9f71-108">New behavior</span></span>

<span data-ttu-id="b9f71-109">El registro usa los valores enteros de los códigos de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="b9f71-109">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="b9f71-110">Considere los siguientes mensajes de registro:</span><span class="sxs-lookup"><span data-stu-id="b9f71-110">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a><span data-ttu-id="b9f71-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b9f71-111">Reason for change</span></span>

<span data-ttu-id="b9f71-112">El comportamiento original de este registro es incoherente con otras partes de ASP.NET Core que siempre han usado valores enteros.</span><span class="sxs-lookup"><span data-stu-id="b9f71-112">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="b9f71-113">La incoherencia hace que los registros resulten difíciles de consultar a través de sistemas de registro estructurados, como [Elasticsearch](https://www.elastic.co/elasticsearch/).</span><span class="sxs-lookup"><span data-stu-id="b9f71-113">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="b9f71-114">Para obtener más contexto, vea [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="b9f71-114">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="b9f71-115">El uso de valores enteros es más flexible que el uso de texto, ya que permite realizar consultas en intervalos de valores.</span><span class="sxs-lookup"><span data-stu-id="b9f71-115">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="b9f71-116">Se consideró la posibilidad de agregar otro valor de registro para capturar el código de estado entero.</span><span class="sxs-lookup"><span data-stu-id="b9f71-116">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="b9f71-117">Desafortunadamente, al hacerlo, se introduciría otra incoherencia con el resto de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b9f71-117">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="b9f71-118">El registro de HttpClient y el registro de HTTP de servidor/hospedaje ya usan el mismo nombre de clave de `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="b9f71-118">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b9f71-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b9f71-119">Recommended action</span></span>

<span data-ttu-id="b9f71-120">La mejor opción consiste en actualizar las consultas de registros para usar los valores enteros de los códigos de estado.</span><span class="sxs-lookup"><span data-stu-id="b9f71-120">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="b9f71-121">Esta opción puede hacer que sea algo difícil escribir consultas en varias versiones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b9f71-121">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="b9f71-122">Aun así, el uso de enteros para este propósito es mucho más flexible para la consulta de registros.</span><span class="sxs-lookup"><span data-stu-id="b9f71-122">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="b9f71-123">Si necesita forzar la compatibilidad con el comportamiento anterior y usar códigos de estado textuales, reemplace el registro de `IHttpClientFactory` por el suyo propio:</span><span class="sxs-lookup"><span data-stu-id="b9f71-123">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="b9f71-124">Copie las versiones de .NET Core 3.1 de las siguientes clases en el proyecto:</span><span class="sxs-lookup"><span data-stu-id="b9f71-124">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="b9f71-125">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="b9f71-125">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="b9f71-126">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="b9f71-126">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="b9f71-127">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="b9f71-127">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="b9f71-128">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="b9f71-128">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="b9f71-129">Cambie el nombre de las clases para evitar conflictos con tipos públicos en el paquete NuGet de [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http).</span><span class="sxs-lookup"><span data-stu-id="b9f71-129">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="b9f71-130">Reemplace la implementación integrada de `LoggingHttpMessageHandlerBuilderFilter` por la suya propia en el método `Startup.ConfigureServices` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b9f71-130">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="b9f71-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9f71-131">For example:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        var descriptors = services.Where(
            s => s.ServiceType == typeof(IHttpMessageHandlerBuilderFilter));
        foreach (var descriptor in descriptors)
        {
            services.Remove(descriptor);
        }

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a><span data-ttu-id="b9f71-132">Categoría</span><span class="sxs-lookup"><span data-stu-id="b9f71-132">Category</span></span>

<span data-ttu-id="b9f71-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b9f71-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b9f71-134">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b9f71-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
