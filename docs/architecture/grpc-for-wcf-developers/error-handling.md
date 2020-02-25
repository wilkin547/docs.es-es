---
title: 'Control de errores: gRPC para desarrolladores de WCF'
description: Temas relacionados con el control de errores en gRPC. Incluye una tabla de los códigos de estado usados con más frecuencia.
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542798"
---
# <a name="error-handling"></a><span data-ttu-id="d8387-104">Control de errores</span><span class="sxs-lookup"><span data-stu-id="d8387-104">Error handling</span></span>

<span data-ttu-id="d8387-105">Windows Communication Foundation (WCF) usa <xref:System.ServiceModel.FaultException%601> y [FaultContract](xref:System.ServiceModel.FaultContractAttribute) para proporcionar información de error detallada, incluida la compatibilidad con el estándar de error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="d8387-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="d8387-106">Desafortunadamente, la versión actual de gRPC carece de la sofisticación que se encuentra en WCF y solo tiene un control de errores integrado limitado basado en códigos de estado y metadatos simples.</span><span class="sxs-lookup"><span data-stu-id="d8387-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="d8387-107">La tabla siguiente es una guía rápida de los códigos de estado usados más comúnmente:</span><span class="sxs-lookup"><span data-stu-id="d8387-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="d8387-108">Código de estado</span><span class="sxs-lookup"><span data-stu-id="d8387-108">Status code</span></span> | <span data-ttu-id="d8387-109">Problema</span><span class="sxs-lookup"><span data-stu-id="d8387-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="d8387-110">No se ha escrito el método.</span><span class="sxs-lookup"><span data-stu-id="d8387-110">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="d8387-111">Problema con el servicio completo.</span><span class="sxs-lookup"><span data-stu-id="d8387-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="d8387-112">Respuesta no válida.</span><span class="sxs-lookup"><span data-stu-id="d8387-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="d8387-113">Problema con la codificación y la descodificación.</span><span class="sxs-lookup"><span data-stu-id="d8387-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="d8387-114">Error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="d8387-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="d8387-115">Error de autorización.</span><span class="sxs-lookup"><span data-stu-id="d8387-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="d8387-116">Se canceló la llamada, normalmente por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d8387-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="d8387-117">Generar errores en ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="d8387-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="d8387-118">Un servicio ASP.NET Core gRPC puede enviar una respuesta de error iniciando una `RpcException`, que puede ser detectada por el cliente como si estuviera en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="d8387-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="d8387-119">El `RpcException` debe incluir un código de estado y una descripción, y puede incluir opcionalmente metadatos y un mensaje de excepción más largo.</span><span class="sxs-lookup"><span data-stu-id="d8387-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="d8387-120">Los metadatos se pueden usar para enviar datos compatibles, de forma similar a cómo `FaultContract` objetos pueden contener datos adicionales para errores de WCF.</span><span class="sxs-lookup"><span data-stu-id="d8387-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="d8387-121">Detección de errores en clientes de gRPC</span><span class="sxs-lookup"><span data-stu-id="d8387-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="d8387-122">Al igual que los clientes de WCF pueden detectar errores de <xref:System.ServiceModel.FaultException%601>, un cliente de gRPC puede detectar un `RpcException` para controlar los errores.</span><span class="sxs-lookup"><span data-stu-id="d8387-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="d8387-123">Dado que `RpcException` no es un tipo genérico, no se pueden detectar distintos tipos de error en bloques diferentes.</span><span class="sxs-lookup"><span data-stu-id="d8387-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="d8387-124">Pero puede usar C#la característica de *filtros de excepciones* de para declarar bloques de `catch` independientes para diferentes códigos de estado, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8387-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="d8387-125">Cuando proporcione metadatos adicionales para los errores, asegúrese de documentar las claves y los valores relevantes en la documentación de la API, o en los comentarios del archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="d8387-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="d8387-126">modelo de error más completo de gRPC</span><span class="sxs-lookup"><span data-stu-id="d8387-126">gRPC richer error model</span></span>

<span data-ttu-id="d8387-127">Google ha desarrollado un [modelo de errores más completo](https://cloud.google.com/apis/design/errors#error_model) , como [FaultContract](xref:System.ServiceModel.FaultContractAttribute)de WCF, pero C# aún no se admite este modelo.</span><span class="sxs-lookup"><span data-stu-id="d8387-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="d8387-128">Actualmente, solo está disponible para Go, Java, Python y C++.</span><span class="sxs-lookup"><span data-stu-id="d8387-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d8387-129">[Anterior](metadata.md)
>[Siguiente](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="d8387-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
