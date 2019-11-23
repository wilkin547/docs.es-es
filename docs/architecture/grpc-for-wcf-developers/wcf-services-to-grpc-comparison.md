---
title: Comparación de WCF con gRPC-gRPC para desarrolladores de WCF
description: Comparación de los marcos WCF y gRPC para compilar aplicaciones distribuidas.
ms.date: 09/02/2019
ms.openlocfilehash: 312492dcce4bdef61feff0bf924c6df287b9c676
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966953"
---
# <a name="comparing-wcf-to-grpc"></a>Comparar WCF con gRPC

En el capítulo anterior debería haber proporcionado un buen vistazo a protobuf y la forma en que gRPC controla los mensajes. Antes de trabajar a través de una conversión detallada de WCF a gRPC, es importante ver cómo se administra el intervalo de características actualmente disponible en WCF en gRPC y qué soluciones alternativas puede usar cuando no parece ser un equivalente de gRPC. En particular, en este capítulo se tratarán los siguientes temas:

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

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
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

En este capítulo se hará referencia a este código de ejemplo al explicar varios conceptos y características de gRPC.

>[!div class="step-by-step"]
>[Anterior](protobuf-maps.md)
>[Siguiente](wcf-endpoints-grpc-methods.md)
