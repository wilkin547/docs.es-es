---
title: REST y gRPC
description: Obtenga información sobre gRPC, su rol en aplicaciones nativas de la nube y cómo difiere de HTTP REST
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: f5725106b251a7e62ef74ea36a63c663e5db36de
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781067"
---
# <a name="rest-and-grpc"></a>REST y gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Hasta ahora en este libro nos hemos centrado en la comunicación [basada en REST](https://docs.microsoft.com/azure/architecture/best-practices/api-design) . REST es un estilo arquitectónico que promueve la interoperabilidad entre sistemas de equipos distribuidos. Usa un modelo de solicitud/respuesta en el que cada respuesta del servidor se refiere a una solicitud del cliente. Aunque es muy popular, REST no es una opción perfecta para cada problema. Una tecnología de comunicación más reciente, titulada gRPC, se obtiene rápidamente y se convierte en el mundo nativo de la nube.

## <a name="grpc"></a>gRPC

gRPC es una comunicación de código abierto que se origina en Google. Se basa en el modelo de [llamada a procedimiento remoto (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) , popular en informática distribuida. Después de este modelo, un programa cliente local expone un método en proceso para ejecutar una operación. En segundo plano, esa llamada se invoca en un microservicio fuera de proceso a través de una red distribuida. El desarrollador codifica la operación como una llamada a procedimiento local. La plataforma subyacente abstrae la comunicación de red punto a punto, la serialización y la ejecución.

gRPC es un marco de RPC moderno que es ligero y de alto rendimiento. Utiliza HTTP/2 para su Protocolo de transporte. Aunque es compatible con HTTP 1,1, las características de HTTP/2 tienen muchas capacidades avanzadas:

- Aunque HTTP 1,1 envía datos como texto sin cifrar, HTTP/2 es un protocolo binario. Analiza los datos más rápidamente con menos memoria, reduce la latencia de red con las mejoras relacionadas con la velocidad y administra los recursos de red de forma más eficaz.
- Aunque HTTP 1,1 está limitado a procesar una solicitud/respuesta de ida y vuelta a la vez, HTTP/2 admite la multiplexación o varias solicitudes paralelas a través de la misma conexión.
- HTTP/2 admite la comunicación dúplex completo o bidireccional, donde tanto el cliente como el servidor pueden comunicarse al mismo tiempo. El cliente puede cargar datos de solicitud al mismo tiempo que el servidor envía datos de respuesta.
- El streaming está integrado en HTTP/2, lo que significa que las solicitudes y respuestas pueden transmitir de forma asincrónica conjuntos de datos grandes.
- La combinación de gRPC y HTTP/2 aumenta considerablemente el rendimiento. En el lenguaje de [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) , el rendimiento de gRPC cumple y supera la velocidad y eficacia de los [enlaces de NetTCP](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8). Sin embargo, a diferencia de NetTCP, gRPC no está restringido a los lenguajes de Microsoft como C# o Visual Basic.

gRPC se admite en las plataformas más populares, como Java C#,, Golang y NodeJS.

## <a name="protocol-buffers"></a>Búferes de protocolo

gRPC adopta otra tecnología de código abierto denominada [búferes de protocolo](https://developers.google.com/protocol-buffers/docs/overview) o mensajes protobuf para enviar y recibir datos. De forma similar a un [contrato de datos de WCF](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-data-contracts), protobuf serializa los datos estructurados de lectura y escritura de los sistemas. Reduce la sobrecarga en la que incurren en formatos de lenguaje natural, como XML o JSON.

Muchas técnicas de serialización de objetos reflejan en la estructura de objetos de datos en tiempo de ejecución. Protobuf requiere que defina la estructura por adelantado con un lenguaje independiente de la plataforma (lenguaje de búfer de protocolo). Cada definición se almacena en un archivo ". proto". Después, mediante el compilador protobuf, "Proton", se genera código de cliente y servidor para cualquiera de las plataformas admitidas. El código generado está optimizado para la serialización o deserialización rápida de los datos. En tiempo de ejecución, cada mensaje se encapsula en el contrato de servicios fuertemente tipado y se serializa en una representación protobuf estándar.

## <a name="grpc-support-in-net"></a>compatibilidad con gRPC en .NET

El marco de Microsoft .NET Core 3,0 incluye herramientas y compatibilidad nativa con gRPC. En la figura 4-20 se muestra la plantilla de Visual Studio 2019 que scaffolding un proyecto de esqueleto de gRPC para un servicio de gRPC. Tenga en cuenta que .NET Core es compatible con las plataformas Windows, Linux y macOS.

![Compatibilidad con gRPC en Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Figura 4-20**. compatibilidad con gRPC en Visual Studio 2019

.NET Core 3,0 integra ininterrumpidamente gRPC en su marco, incluido el enrutamiento del punto de conexión, la compatibilidad de IoC integrada y el registro. El servidor Web Kestrel de código abierto es totalmente compatible con las conexiones HTTP/2.

En la figura 4-21 se muestra la estructura de un servicio gRPC en Visual Studio 2019. Tenga en cuenta que la estructura de carpetas incluye carpetas para los archivos proto y el código de servicio.

![proyecto gRPC en Visual Studio 2019](./media/grpc-project.png  )

**Figura 4-21**. proyecto gRPC en Visual Studio 2019

## <a name="grpc-usage"></a>Uso de gRPC

gRPC es adecuado para los escenarios siguientes:

- Baja latencia y comunicación de alto rendimiento. gRPC es ideal para microservicios ligeros en los que la eficacia es crítica.
- Comunicación en tiempo real punto a punto. gRPC tiene una excelente compatibilidad para el streaming bidireccional. gRPC Services puede enviar mensajes en tiempo real sin sondeos.
- Entornos de Polyglot: las herramientas de gRPC admiten los lenguajes de desarrollo más populares, lo que lo convierte en una buena opción para entornos de varios idiomas.
- Entornos con restricción de red: los mensajes gRPC se serializan con protobuf, un formato de mensaje ligero. Un mensaje de gRPC siempre es más pequeño que un mensaje JSON equivalente.

En el momento de redactar este libro, la mayoría de los exploradores tienen compatibilidad limitada para gRPC. gRPC usa intensamente características HTTP/2 y ningún explorador proporciona el nivel de control requerido a través de solicitudes web para admitir un cliente de gRPC. gRPC se usa normalmente para microservicios internos para la comunicación de microservicios. En la figura 4-22 se muestra un patrón de uso sencillo pero común.

![Patrones de uso de gRPC](./media/grpc-usage.png)

**Figura 4-22**. patrones de uso de gRPC

Tenga en cuenta en la figura anterior cómo se invoca el tráfico front-end con HTTP mientras que el microservicio de back-end a microservicio usa gRPC.

En el futuro, gRPC podría desempeñar un papel importante en Dethroning la dominante de REST para sistemas nativos en la nube. Los beneficios de rendimiento y la facilidad de desarrollo son demasiado buenos para pasarlos. Sin embargo, no hay ningún error, el resto permanecerá en un período de tiempo prolongado. Sigue siendo Excel para las API expuestas públicamente y por motivos de compatibilidad con versiones anteriores.

>[!div class="step-by-step"]
>[Anterior](service-to-service-communication.md)
>[Siguiente](service-mesh-communication-infrastructure.md)
