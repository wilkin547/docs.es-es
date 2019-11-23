---
title: 'Control de errores: gRPC para desarrolladores de WCF'
description: PENDIENTE DE REDACTAR
ms.date: 09/02/2019
ms.openlocfilehash: 2c44bd9264c877a7c7a86c115b6da9f759006016
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967790"
---
# <a name="error-handling"></a><span data-ttu-id="81317-103">Control de errores</span><span class="sxs-lookup"><span data-stu-id="81317-103">Error handling</span></span>

<span data-ttu-id="81317-104">WCF usa `FaultException<T>` y `FaultContract` para proporcionar información de error detallada, incluida la compatibilidad con el estándar de error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="81317-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="81317-105">Desafortunadamente, la versión actual de gRPC carece de la sofisticación que se encuentra en WCF y solo tiene un control de errores integrado limitado basado en códigos de estado y metadatos simples.</span><span class="sxs-lookup"><span data-stu-id="81317-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="81317-106">La tabla siguiente es una guía rápida de los códigos de estado usados más comúnmente:</span><span class="sxs-lookup"><span data-stu-id="81317-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="81317-107">Código de estado</span><span class="sxs-lookup"><span data-stu-id="81317-107">Status Code</span></span> | <span data-ttu-id="81317-108">Problema</span><span class="sxs-lookup"><span data-stu-id="81317-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="81317-109">No se ha escrito el método.</span><span class="sxs-lookup"><span data-stu-id="81317-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="81317-110">Problema con el servicio completo.</span><span class="sxs-lookup"><span data-stu-id="81317-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="81317-111">Respuesta no válida.</span><span class="sxs-lookup"><span data-stu-id="81317-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="81317-112">Problema con la codificación y la descodificación.</span><span class="sxs-lookup"><span data-stu-id="81317-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="81317-113">Error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="81317-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="81317-114">Error de autorización.</span><span class="sxs-lookup"><span data-stu-id="81317-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="81317-115">Se canceló la llamada, normalmente por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="81317-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="81317-116">Generar errores en ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="81317-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="81317-117">Un servicio ASP.NET Core gRPC puede enviar una respuesta de error iniciando una `RpcException`, que puede ser detectada por el cliente como si estuviera en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="81317-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="81317-118">El `RpcException` debe incluir un código de estado y una descripción, y puede incluir opcionalmente metadatos y un mensaje de excepción más largo.</span><span class="sxs-lookup"><span data-stu-id="81317-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="81317-119">Los metadatos se pueden usar para enviar datos compatibles, de forma similar a cómo `FaultContract` objetos podrían contener datos adicionales para errores de WCF.</span><span class="sxs-lookup"><span data-stu-id="81317-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

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

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="81317-120">Detección de errores en clientes de gRPC</span><span class="sxs-lookup"><span data-stu-id="81317-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="81317-121">Al igual que los clientes de WCF pueden detectar errores de <xref:System.ServiceModel.FaultException%601>, un cliente de gRPC puede detectar un `RpcException` para controlar los errores.</span><span class="sxs-lookup"><span data-stu-id="81317-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="81317-122">Dado que `RpcException` no es un tipo genérico, no puede detectar distintos tipos de error en bloques diferentes, pero C#puede usar la característica de *filtros de excepciones* de para declarar bloques de `catch` independientes para códigos de estado diferentes, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="81317-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="81317-123">Cuando proporcione metadatos adicionales para los errores, asegúrese de documentar las claves y los valores relevantes en la documentación de la API, o en los comentarios del archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="81317-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="81317-124">Modelo de error más completo de gRPC</span><span class="sxs-lookup"><span data-stu-id="81317-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="81317-125">En el futuro, Google ha desarrollado un [modelo de errores más completo](https://cloud.google.com/apis/design/errors#error_model) que es más parecido a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)de WCF, pero C# todavía no se admite en.</span><span class="sxs-lookup"><span data-stu-id="81317-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="81317-126">Actualmente, solo está disponible para Go, Java, Python y C++, pero se espera que C# el soporte técnico de sea el próximo año.</span><span class="sxs-lookup"><span data-stu-id="81317-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="81317-127">[Anterior](metadata.md)
>[Siguiente](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="81317-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
