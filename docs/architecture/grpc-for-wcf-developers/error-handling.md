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
# <a name="error-handling"></a>Control de errores

Windows Communication Foundation (WCF) usa <xref:System.ServiceModel.FaultException%601> y [FaultContract](xref:System.ServiceModel.FaultContractAttribute) para proporcionar información de error detallada, incluida la compatibilidad con el estándar de error de SOAP.

Desafortunadamente, la versión actual de gRPC carece de la sofisticación que se encuentra en WCF y solo tiene un control de errores integrado limitado basado en códigos de estado y metadatos simples. La tabla siguiente es una guía rápida de los códigos de estado usados más comúnmente:

| Código de estado | Problema |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | No se ha escrito el método. |
| `GRPC_STATUS_UNAVAILABLE` | Problema con el servicio completo. |
| `GRPC_STATUS_UNKNOWN` | Respuesta no válida. |
| `GRPC_STATUS_INTERNAL` | Problema con la codificación y la descodificación. |
| `GRPC_STATUS_UNAUTHENTICATED` | Error de autenticación. |
| `GRPC_STATUS_PERMISSION_DENIED` | Error de autorización. |
| `GRPC_STATUS_CANCELLED` | Se canceló la llamada, normalmente por el autor de la llamada. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>Generar errores en ASP.NET Core gRPC

Un servicio ASP.NET Core gRPC puede enviar una respuesta de error iniciando una `RpcException`, que puede ser detectada por el cliente como si estuviera en el mismo proceso. El `RpcException` debe incluir un código de estado y una descripción, y puede incluir opcionalmente metadatos y un mensaje de excepción más largo. Los metadatos se pueden usar para enviar datos compatibles, de forma similar a cómo `FaultContract` objetos pueden contener datos adicionales para errores de WCF.

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

## <a name="catch-errors-in-grpc-clients"></a>Detección de errores en clientes de gRPC

Al igual que los clientes de WCF pueden detectar errores de <xref:System.ServiceModel.FaultException%601>, un cliente de gRPC puede detectar un `RpcException` para controlar los errores. Dado que `RpcException` no es un tipo genérico, no se pueden detectar distintos tipos de error en bloques diferentes. Pero puede usar C#la característica de *filtros de excepciones* de para declarar bloques de `catch` independientes para diferentes códigos de estado, como se muestra en el ejemplo siguiente:

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
> Cuando proporcione metadatos adicionales para los errores, asegúrese de documentar las claves y los valores relevantes en la documentación de la API, o en los comentarios del archivo de `.proto`.

## <a name="grpc-richer-error-model"></a>modelo de error más completo de gRPC

Google ha desarrollado un [modelo de errores más completo](https://cloud.google.com/apis/design/errors#error_model) , como [FaultContract](xref:System.ServiceModel.FaultContractAttribute)de WCF, pero C# aún no se admite este modelo. Actualmente, solo está disponible para Go, Java, Python y C++.

>[!div class="step-by-step"]
>[Anterior](metadata.md)
>[Siguiente](ws-protocols.md)
