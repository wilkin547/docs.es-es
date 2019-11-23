---
title: 'Metadatos: gRPC para desarrolladores de WCF'
description: Cómo se usan los metadatos en gRPC para pasar contexto adicional entre clientes y servidores
ms.date: 09/02/2019
ms.openlocfilehash: 723d877bfbf0c2b0785949ff15939aedbac4d4e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971973"
---
# <a name="metadata"></a><span data-ttu-id="d317d-103">Metadatos</span><span class="sxs-lookup"><span data-stu-id="d317d-103">Metadata</span></span>

<span data-ttu-id="d317d-104">"Metadatos" hace referencia a datos adicionales que pueden ser útiles mientras se procesan las solicitudes y las respuestas, pero no forman parte de los datos reales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d317d-104">"Metadata" refers to additional data that may be useful while processing requests and responses but is not part of the actual application data.</span></span> <span data-ttu-id="d317d-105">Los metadatos pueden incluir tokens de autenticación, identificadores de solicitud y etiquetas para fines de supervisión, o información sobre los datos, como el número de registros de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="d317d-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, or information about the data like the number of records in a dataset.</span></span>

<span data-ttu-id="d317d-106">Es posible agregar encabezados de clave y valor genéricos a los mensajes WCF mediante una <xref:System.ServiceModel.OperationContextScope> y la propiedad <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType>, y controlarlos mediante <xref:System.ServiceModel.Channels.MessageProperties>.</span><span class="sxs-lookup"><span data-stu-id="d317d-106">It's possible to add generic key/value headers to WCF messages using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property, and handle them using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="d317d-107">las llamadas y respuestas gRPC también pueden incluir metadatos similares a los encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="d317d-107">gRPC calls and responses can also include metadata similar to HTTP headers.</span></span> <span data-ttu-id="d317d-108">Son principalmente invisibles para gRPC y se pasan para ser procesados por su código de aplicación o middleware.</span><span class="sxs-lookup"><span data-stu-id="d317d-108">These are mostly invisible to gRPC itself and are passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="d317d-109">Los metadatos se representan como pares clave-valor, donde la clave es una cadena y el valor es una cadena o datos binarios.</span><span class="sxs-lookup"><span data-stu-id="d317d-109">Metadata is represented as key/value pairs where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="d317d-110">No es necesario especificar metadatos en el archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="d317d-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="d317d-111">Los metadatos se controlan mediante la clase `Metadata` del paquete de NuGet [GRPC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) .</span><span class="sxs-lookup"><span data-stu-id="d317d-111">Metadata is handled using the `Metadata` class from the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="d317d-112">Esta clase se puede utilizar con la sintaxis del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="d317d-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="d317d-113">En el ejemplo siguiente se muestra cómo agregar metadatos a una llamada C# de un cliente:</span><span class="sxs-lookup"><span data-stu-id="d317d-113">The following example shows how to add metadata to a call from a C# client:</span></span>

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

<span data-ttu-id="d317d-114">los servicios de gRPC pueden tener acceso a los metadatos de la propiedad `RequestHeaders` del argumento `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="d317d-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

<span data-ttu-id="d317d-115">Los servicios pueden enviar metadatos a los clientes mediante la propiedad `ResponseTrailers` de `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="d317d-115">Services can send metadata to clients using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="d317d-116">[Anterior](rpc-types.md)
>[Siguiente](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="d317d-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
