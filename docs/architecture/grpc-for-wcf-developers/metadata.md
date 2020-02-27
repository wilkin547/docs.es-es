---
title: 'Metadatos: gRPC para desarrolladores de WCF'
description: Cómo se usan los metadatos en gRPC para pasar contexto adicional entre clientes y servidores.
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628584"
---
# <a name="metadata"></a><span data-ttu-id="425fa-103">Metadatos</span><span class="sxs-lookup"><span data-stu-id="425fa-103">Metadata</span></span>

<span data-ttu-id="425fa-104">Los metadatos *hacen referencia* a datos adicionales que pueden resultar útiles durante el procesamiento de solicitudes y respuestas, pero que no forman parte de los datos de aplicación reales.</span><span class="sxs-lookup"><span data-stu-id="425fa-104">*Metadata* refers to additional data that might be useful during the processing of requests and responses but that’s not part of the actual application data.</span></span> <span data-ttu-id="425fa-105">Los metadatos pueden incluir tokens de autenticación, identificadores de solicitud y etiquetas para fines de supervisión e información sobre los datos, como el número de registros de un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="425fa-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, and information about the data, like the number of records in a dataset.</span></span>

<span data-ttu-id="425fa-106">Es posible agregar encabezados de clave y valor genéricos a mensajes de Windows Communication Foundation (WCF) mediante el uso de un <xref:System.ServiceModel.OperationContextScope> y la propiedad <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> y controlarlos mediante el uso de <xref:System.ServiceModel.Channels.MessageProperties>.</span><span class="sxs-lookup"><span data-stu-id="425fa-106">It's possible to add generic key/value headers to Windows Communication Foundation (WCF) messages by using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property and handle them by using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="425fa-107">las llamadas y respuestas gRPC también pueden incluir metadatos similares a los encabezados HTTP.</span><span class="sxs-lookup"><span data-stu-id="425fa-107">gRPC calls and responses can also include metadata that's similar to HTTP headers.</span></span> <span data-ttu-id="425fa-108">Estos metadatos son principalmente invisibles para gRPC y se pasan para ser procesados por su código de aplicación o middleware.</span><span class="sxs-lookup"><span data-stu-id="425fa-108">This metadata is mostly invisible to gRPC itself and is passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="425fa-109">Los metadatos se representan como pares clave-valor, donde la clave es una cadena y el valor es una cadena o datos binarios.</span><span class="sxs-lookup"><span data-stu-id="425fa-109">Metadata is represented as key/value pairs, where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="425fa-110">No es necesario especificar metadatos en el archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="425fa-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="425fa-111">Los metadatos se controlan mediante la clase `Metadata` del paquete de NuGet [GRPC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) .</span><span class="sxs-lookup"><span data-stu-id="425fa-111">Metadata is handled by the `Metadata` class of the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="425fa-112">Esta clase se puede utilizar con la sintaxis del inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="425fa-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="425fa-113">En este ejemplo se muestra cómo agregar metadatos a una llamada C# de un cliente:</span><span class="sxs-lookup"><span data-stu-id="425fa-113">This example shows how to add metadata to a call from a C# client:</span></span>

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

<span data-ttu-id="425fa-114">los servicios de gRPC pueden tener acceso a los metadatos de la propiedad `RequestHeaders` del argumento `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="425fa-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

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

<span data-ttu-id="425fa-115">Los servicios pueden enviar metadatos a los clientes mediante la propiedad `ResponseTrailers` de `ServerCallContext`:</span><span class="sxs-lookup"><span data-stu-id="425fa-115">Services can send metadata to clients by using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="425fa-116">[Anterior](rpc-types.md)
>[Siguiente](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="425fa-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
