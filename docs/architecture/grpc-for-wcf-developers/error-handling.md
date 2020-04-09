---
title: Control de errores - gRPC para desarrolladores de WCF
description: Temas relacionados con el manejo de errores en gRPC. Incluye una tabla de los códigos de estado más utilizados.
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988952"
---
# <a name="error-handling"></a><span data-ttu-id="4fb18-104">Control de errores</span><span class="sxs-lookup"><span data-stu-id="4fb18-104">Error handling</span></span>

<span data-ttu-id="4fb18-105">Windows Communication Foundation (WCF) usa <xref:System.ServiceModel.FaultException%601> y [FaultContract](xref:System.ServiceModel.FaultContractAttribute) para proporcionar información de error detallada, incluida la compatibilidad con el estándar de error SOAP.</span><span class="sxs-lookup"><span data-stu-id="4fb18-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="4fb18-106">Desafortunadamente, la versión actual de gRPC carece de la sofisticación que se encuentra con WCF, y solo tiene un control de errores integrado limitado basado en códigos de estado y metadatos simples.</span><span class="sxs-lookup"><span data-stu-id="4fb18-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="4fb18-107">La siguiente tabla es una guía rápida de los códigos de estado más utilizados:</span><span class="sxs-lookup"><span data-stu-id="4fb18-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="4fb18-108">status code</span><span class="sxs-lookup"><span data-stu-id="4fb18-108">Status code</span></span> | <span data-ttu-id="4fb18-109">Problema</span><span class="sxs-lookup"><span data-stu-id="4fb18-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="4fb18-110">El método no ha sido escrito.</span><span class="sxs-lookup"><span data-stu-id="4fb18-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="4fb18-111">Problema con todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="4fb18-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="4fb18-112">Respuesta no válida.</span><span class="sxs-lookup"><span data-stu-id="4fb18-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="4fb18-113">Problema con la codificación/decodificación.</span><span class="sxs-lookup"><span data-stu-id="4fb18-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="4fb18-114">Error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="4fb18-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="4fb18-115">Error de autorización.</span><span class="sxs-lookup"><span data-stu-id="4fb18-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="4fb18-116">La llamada fue cancelada, normalmente por la persona que llamó.</span><span class="sxs-lookup"><span data-stu-id="4fb18-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="4fb18-117">Generar errores en ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="4fb18-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="4fb18-118">Un servicio gRPC de ASP.NET Core puede `RpcException`enviar una respuesta de error lanzando un , que puede ser capturado por el cliente como si estuviera en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="4fb18-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="4fb18-119">El `RpcException` debe incluir un código de estado y una descripción, y opcionalmente puede incluir metadatos y un mensaje de excepción más largo.</span><span class="sxs-lookup"><span data-stu-id="4fb18-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="4fb18-120">Los metadatos se pueden usar para enviar `FaultContract` datos auxiliares, de forma similar a cómo los objetos pueden transportar datos adicionales para errores WCF.</span><span class="sxs-lookup"><span data-stu-id="4fb18-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="4fb18-121">Detectar errores en clientes gRPC</span><span class="sxs-lookup"><span data-stu-id="4fb18-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="4fb18-122">Al igual que <xref:System.ServiceModel.FaultException%601> los clientes WCF pueden `RpcException` detectar errores, un cliente gRPC puede detectar un para controlar los errores.</span><span class="sxs-lookup"><span data-stu-id="4fb18-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="4fb18-123">Dado `RpcException` que no es un tipo genérico, no puede detectar diferentes tipos de error en bloques diferentes.</span><span class="sxs-lookup"><span data-stu-id="4fb18-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="4fb18-124">Pero puede utilizar la característica de filtros `catch` de *excepción* de C's para declarar bloques independientes para diferentes códigos de estado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fb18-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="4fb18-125">Cuando proporcione metadatos adicionales para errores, asegúrese de documentar las claves y valores `.proto` relevantes en la documentación de la API o en los comentarios del archivo.</span><span class="sxs-lookup"><span data-stu-id="4fb18-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="4fb18-126">modelo de error gRPC más rico</span><span class="sxs-lookup"><span data-stu-id="4fb18-126">gRPC richer error model</span></span>

<span data-ttu-id="4fb18-127">Google ha desarrollado un modelo de [error más enriquecido](https://cloud.google.com/apis/design/errors#error_model) que se parece más a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)de WCF, pero este modelo aún no se admite en C.</span><span class="sxs-lookup"><span data-stu-id="4fb18-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="4fb18-128">Actualmente, solo está disponible para Go, Java, Python y C++.</span><span class="sxs-lookup"><span data-stu-id="4fb18-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4fb18-129">[Anterior](metadata.md)
>[Siguiente](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="4fb18-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
