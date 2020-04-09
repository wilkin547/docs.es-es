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
# <a name="error-handling"></a>Control de errores

Windows Communication Foundation (WCF) usa <xref:System.ServiceModel.FaultException%601> y [FaultContract](xref:System.ServiceModel.FaultContractAttribute) para proporcionar información de error detallada, incluida la compatibilidad con el estándar de error SOAP.

Desafortunadamente, la versión actual de gRPC carece de la sofisticación que se encuentra con WCF, y solo tiene un control de errores integrado limitado basado en códigos de estado y metadatos simples. La siguiente tabla es una guía rápida de los códigos de estado más utilizados:

| status code | Problema |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | El método no ha sido escrito. |
| `GRPC_STATUS_UNAVAILABLE` | Problema con todo el servicio. |
| `GRPC_STATUS_UNKNOWN` | Respuesta no válida. |
| `GRPC_STATUS_INTERNAL` | Problema con la codificación/decodificación. |
| `GRPC_STATUS_UNAUTHENTICATED` | Error de autenticación. |
| `GRPC_STATUS_PERMISSION_DENIED` | Error de autorización. |
| `GRPC_STATUS_CANCELLED` | La llamada fue cancelada, normalmente por la persona que llamó. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>Generar errores en ASP.NET Core gRPC

Un servicio gRPC de ASP.NET Core puede `RpcException`enviar una respuesta de error lanzando un , que puede ser capturado por el cliente como si estuviera en el mismo proceso. El `RpcException` debe incluir un código de estado y una descripción, y opcionalmente puede incluir metadatos y un mensaje de excepción más largo. Los metadatos se pueden usar para enviar `FaultContract` datos auxiliares, de forma similar a cómo los objetos pueden transportar datos adicionales para errores WCF.

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

## <a name="catch-errors-in-grpc-clients"></a>Detectar errores en clientes gRPC

Al igual que <xref:System.ServiceModel.FaultException%601> los clientes WCF pueden `RpcException` detectar errores, un cliente gRPC puede detectar un para controlar los errores. Dado `RpcException` que no es un tipo genérico, no puede detectar diferentes tipos de error en bloques diferentes. Pero puede utilizar la característica de filtros `catch` de *excepción* de C's para declarar bloques independientes para diferentes códigos de estado, como se muestra en el ejemplo siguiente:

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
> Cuando proporcione metadatos adicionales para errores, asegúrese de documentar las claves y valores `.proto` relevantes en la documentación de la API o en los comentarios del archivo.

## <a name="grpc-richer-error-model"></a>modelo de error gRPC más rico

Google ha desarrollado un modelo de [error más enriquecido](https://cloud.google.com/apis/design/errors#error_model) que se parece más a [FaultContract](xref:System.ServiceModel.FaultContractAttribute)de WCF, pero este modelo aún no se admite en C. Actualmente, solo está disponible para Go, Java, Python y C++.

>[!div class="step-by-step"]
>[Anterior](metadata.md)
>[Siguiente](ws-protocols.md)
