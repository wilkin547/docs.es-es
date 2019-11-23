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
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="4b7e7-103">Comparar WCF con gRPC</span><span class="sxs-lookup"><span data-stu-id="4b7e7-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="4b7e7-104">En el capítulo anterior debería haber proporcionado un buen vistazo a protobuf y la forma en que gRPC controla los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4b7e7-104">The previous chapter should have given you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="4b7e7-105">Antes de trabajar a través de una conversión detallada de WCF a gRPC, es importante ver cómo se administra el intervalo de características actualmente disponible en WCF en gRPC y qué soluciones alternativas puede usar cuando no parece ser un equivalente de gRPC.</span><span class="sxs-lookup"><span data-stu-id="4b7e7-105">Before working through a detailed conversion from WCF to gRPC, it's important to look at how the range of features currently available in WCF are handled in gRPC and what workarounds you can use when there doesn't appear to be a gRPC equivalent.</span></span> <span data-ttu-id="4b7e7-106">En particular, en este capítulo se tratarán los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="4b7e7-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="4b7e7-107">Operaciones y métodos</span><span class="sxs-lookup"><span data-stu-id="4b7e7-107">Operations and methods</span></span>
- <span data-ttu-id="4b7e7-108">Enlaces y transportes</span><span class="sxs-lookup"><span data-stu-id="4b7e7-108">Bindings and transports</span></span>
- <span data-ttu-id="4b7e7-109">Tipos RPC</span><span class="sxs-lookup"><span data-stu-id="4b7e7-109">RPC types</span></span>
- <span data-ttu-id="4b7e7-110">Metadatos</span><span class="sxs-lookup"><span data-stu-id="4b7e7-110">Metadata</span></span>
- <span data-ttu-id="4b7e7-111">Control de errores</span><span class="sxs-lookup"><span data-stu-id="4b7e7-111">Error handling</span></span>
- <span data-ttu-id="4b7e7-112">Protocolos WS-\*</span><span class="sxs-lookup"><span data-stu-id="4b7e7-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="4b7e7-113">ejemplo de gRPC</span><span class="sxs-lookup"><span data-stu-id="4b7e7-113">gRPC example</span></span>

<span data-ttu-id="4b7e7-114">Al crear un nuevo proyecto ASP.NET Core 3,0 gRPC desde Visual Studio 2019 o desde la línea de comandos, se genera el equivalente gRPC de "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="4b7e7-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="4b7e7-115">Consta de un archivo `greeter.proto` que define el servicio y sus mensajes, y un archivo `GreeterService.cs` con una implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="4b7e7-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

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

<span data-ttu-id="4b7e7-116">En este capítulo se hará referencia a este código de ejemplo al explicar varios conceptos y características de gRPC.</span><span class="sxs-lookup"><span data-stu-id="4b7e7-116">This chapter will refer to this example code when explaining various concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4b7e7-117">[Anterior](protobuf-maps.md)
>[Siguiente](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="4b7e7-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
