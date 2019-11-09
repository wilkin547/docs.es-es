---
title: 'Control de errores: gRPC para desarrolladores de WCF'
description: PENDIENTE DE REDACTAR
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 91f5789d8ed0f01f3ce2f3f9a6c6ccf14f245290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73842006"
---
# <a name="error-handling"></a>Control de errores

WCF usa `FaultException<T>` y `FaultContract` para proporcionar información de error detallada, incluida la compatibilidad con el estándar de error de SOAP.

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

## <a name="raising-errors-in-aspnet-core-grpc"></a>Generar errores en ASP.NET Core gRPC

Un servicio ASP.NET Core gRPC puede enviar una respuesta de error iniciando una `RpcException`, que puede ser detectada por el cliente como si estuviera en el mismo proceso. El `RpcException` debe incluir un código de estado y una descripción, y puede incluir opcionalmente metadatos y un mensaje de excepción más largo. Los metadatos se pueden usar para enviar datos compatibles, de forma similar a cómo `FaultContract` objetos podrían contener datos adicionales para errores de WCF.

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

## <a name="catching-errors-in-grpc-clients"></a>Detección de errores en clientes de gRPC

Al igual que los clientes de WCF pueden detectar errores de <xref:System.ServiceModel.FaultException%601>, un cliente de gRPC puede detectar un `RpcException` para controlar los errores. Dado que `RpcException` no es un tipo genérico, no puede detectar distintos tipos de error en bloques diferentes, pero C#puede usar la característica de *filtros de excepciones* de para declarar bloques de `catch` independientes para códigos de estado diferentes, como se muestra en el ejemplo siguiente:

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

## <a name="grpc-richer-error-model"></a>Modelo de error más completo de gRPC

En el futuro, Google ha desarrollado un [modelo de errores más completo](https://cloud.google.com/apis/design/errors#error_model) que es más parecido a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)de WCF, pero C# todavía no se admite en. Actualmente, solo está disponible para Go, Java, Python y C++, pero se espera que C# el soporte técnico de sea el próximo año.

>[!div class="step-by-step"]
>[Anterior](metadata.md)
>[Siguiente](ws-protocols.md)
