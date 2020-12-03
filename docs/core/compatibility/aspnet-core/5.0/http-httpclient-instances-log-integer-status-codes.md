---
title: 'Cambio importante: HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 964c0a65a07816acea8016d42a66a6bf84aba7c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760100"
---
# <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="f88c0-103">HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="f88c0-103">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="f88c0-104">Instancias de <xref:System.Net.Http.HttpClient> creadas como enteros por códigos de estado HTTP del registro de <xref:System.Net.Http.IHttpClientFactory>, en lugar de con nombres de código de estado.</span><span class="sxs-lookup"><span data-stu-id="f88c0-104"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f88c0-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f88c0-105">Version introduced</span></span>

<span data-ttu-id="f88c0-106">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="f88c0-106">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="f88c0-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="f88c0-107">Old behavior</span></span>

<span data-ttu-id="f88c0-108">El registro usa las descripciones textuales de los códigos de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="f88c0-108">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="f88c0-109">Considere los siguientes mensajes de registro:</span><span class="sxs-lookup"><span data-stu-id="f88c0-109">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

## <a name="new-behavior"></a><span data-ttu-id="f88c0-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="f88c0-110">New behavior</span></span>

<span data-ttu-id="f88c0-111">El registro usa los valores enteros de los códigos de estado HTTP.</span><span class="sxs-lookup"><span data-stu-id="f88c0-111">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="f88c0-112">Considere los siguientes mensajes de registro:</span><span class="sxs-lookup"><span data-stu-id="f88c0-112">Consider the following log messages:</span></span>

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

## <a name="reason-for-change"></a><span data-ttu-id="f88c0-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f88c0-113">Reason for change</span></span>

<span data-ttu-id="f88c0-114">El comportamiento original de este registro es incoherente con otras partes de ASP.NET Core que siempre han usado valores enteros.</span><span class="sxs-lookup"><span data-stu-id="f88c0-114">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="f88c0-115">La incoherencia hace que los registros resulten difíciles de consultar a través de sistemas de registro estructurados, como [Elasticsearch](https://www.elastic.co/elasticsearch/).</span><span class="sxs-lookup"><span data-stu-id="f88c0-115">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="f88c0-116">Para obtener más contexto, vea [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="f88c0-116">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="f88c0-117">El uso de valores enteros es más flexible que el uso de texto, ya que permite realizar consultas en intervalos de valores.</span><span class="sxs-lookup"><span data-stu-id="f88c0-117">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="f88c0-118">Se consideró la posibilidad de agregar otro valor de registro para capturar el código de estado entero.</span><span class="sxs-lookup"><span data-stu-id="f88c0-118">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="f88c0-119">Desafortunadamente, al hacerlo, se introduciría otra incoherencia con el resto de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f88c0-119">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="f88c0-120">El registro de HttpClient y el registro de HTTP de servidor/hospedaje ya usan el mismo nombre de clave de `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="f88c0-120">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f88c0-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f88c0-121">Recommended action</span></span>

<span data-ttu-id="f88c0-122">La mejor opción consiste en actualizar las consultas de registros para usar los valores enteros de los códigos de estado.</span><span class="sxs-lookup"><span data-stu-id="f88c0-122">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="f88c0-123">Esta opción puede hacer que sea algo difícil escribir consultas en varias versiones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f88c0-123">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="f88c0-124">Aun así, el uso de enteros para este propósito es mucho más flexible para la consulta de registros.</span><span class="sxs-lookup"><span data-stu-id="f88c0-124">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="f88c0-125">Si necesita forzar la compatibilidad con el comportamiento anterior y usar códigos de estado textuales, reemplace el registro de `IHttpClientFactory` por el suyo propio:</span><span class="sxs-lookup"><span data-stu-id="f88c0-125">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="f88c0-126">Copie las versiones de .NET Core 3.1 de las siguientes clases en el proyecto:</span><span class="sxs-lookup"><span data-stu-id="f88c0-126">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="f88c0-127">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="f88c0-127">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="f88c0-128">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="f88c0-128">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="f88c0-129">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="f88c0-129">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="f88c0-130">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="f88c0-130">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="f88c0-131">Cambie el nombre de las clases para evitar conflictos con tipos públicos en el paquete NuGet de [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http).</span><span class="sxs-lookup"><span data-stu-id="f88c0-131">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="f88c0-132">Reemplace la implementación integrada de `LoggingHttpMessageHandlerBuilderFilter` por la suya propia en el método `Startup.ConfigureServices` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f88c0-132">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="f88c0-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f88c0-133">For example:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        services.RemoveAll<IHttpMessageHandlerBuilderFilter>();

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

## <a name="affected-apis"></a><span data-ttu-id="f88c0-134">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f88c0-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:System.Net.Http.HttpClient`

-->
