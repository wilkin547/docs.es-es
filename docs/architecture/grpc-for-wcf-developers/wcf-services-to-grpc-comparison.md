---
title: Comparación de WCF con gRPC-gRPC para desarrolladores de WCF
description: Comparación de los marcos WCF y gRPC para compilar aplicaciones distribuidas.
ms.date: 09/02/2019
ms.openlocfilehash: 4f54db76c9512b770b4dd993496d95437dd89753
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503336"
---
# <a name="comparing-wcf-to-grpc"></a>Comparar WCF con gRPC

En el capítulo anterior se ha dado una buena mirada a protobuf y cómo gRPC controla los mensajes. Antes de trabajar en una conversión detallada de Windows Communication Foundation (WCF) a gRPC, es importante saber cómo se controlan las características disponibles en WCF en gRPC y qué soluciones puede usar cuando no hay ningún equivalente de gRPC. En particular, en este capítulo se tratarán los siguientes temas:

- Operaciones y métodos
- Enlaces y transportes
- Tipos RPC
- Metadatos
- Control de errores
- Protocolos WS-\*

## <a name="grpc-example"></a>ejemplo de gRPC

Al crear un nuevo proyecto ASP.NET Core 3,0 gRPC desde Visual Studio 2019 o desde la línea de comandos, se genera el equivalente gRPC de "Hola mundo". Consta de un archivo `greeter.proto` que define el servicio y sus mensajes, y un archivo `GreeterService.cs` con una implementación del servicio.

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

En este capítulo se hará referencia a este código de ejemplo al explicar los distintos conceptos y características de gRPC.

>[!div class="step-by-step"]
>[Anterior](protobuf-maps.md)
>[Siguiente](wcf-endpoints-grpc-methods.md)
