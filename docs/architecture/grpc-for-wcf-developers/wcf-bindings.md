---
title: Enlaces y transportes de WCF-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo se comparan los distintos enlaces y transportes de WCF con gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 34321395ddd7059ac7e3c268e313a03251662911
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841322"
---
# <a name="wcf-bindings-and-transports"></a>Enlaces y transportes de WCF

WCF tiene muchos *enlaces* integrados diferentes que especifican diferentes protocolos de red, formatos de conexión y otros detalles de la implementación. gRPC eficazmente tiene un solo protocolo de red y un formato de conexión (técnicamente, el formato de conexión se *puede* personalizar, pero esto está fuera del ámbito de este libro). Es probable que descubra que gRPC ofrece la mejor solución en la mayoría de los casos. A continuación se muestra una breve explicación sobre los enlaces de WCF más relevantes y cómo se comparan con su equivalente en gRPC.

## <a name="nettcp"></a>NetTCP

El enlace NetTCP de WCF permite conexiones persistentes, mensajes pequeños y mensajería bidireccional, pero solo funciona entre clientes y servidores .NET. gRPC permite la misma funcionalidad, pero se admite en varios lenguajes de programación y plataformas. gRPC tiene muchas de las características del enlace NetTCP de WCF, aunque no siempre se implementa de la misma manera. Por ejemplo, en WCF, el cifrado se controla a través de la configuración y se controla en el marco. En gRPC, el cifrado se consigue en el nivel de conexión mediante HTTP/2 a través de TLS.

## <a name="http"></a>HTTP

BasicHttpBinding de WCF suele basarse en texto, usar SOAP como formato de conexión y es lento en comparación con el enlace NetTCP. Normalmente se usa para proporcionar interoperabilidad entre plataformas o conexión a través de la infraestructura de Internet. El equivalente en gRPC: dado que usa HTTP/2 como la capa de transporte subyacente con el formato de conexión protobuf binaria para los mensajes, puede ofrecer un rendimiento de nivel de servicio de NetTCP, pero con una interoperabilidad completa multiplataforma con todos los lenguajes y marcos de programación modernos.

## <a name="named-pipes"></a>Canalizaciones con nombre

WCF proporcionó un enlace de canalizaciones con nombre para la comunicación entre procesos en el mismo equipo físico. La primera versión de ASP.NET Core gRPC no admite las canalizaciones con nombre. Agregar compatibilidad de cliente y servidor para canalizaciones con nombre (y sockets de dominio de UNIX) es un objetivo para una versión futura.

## <a name="msmq"></a>MSMQ

MSMQ es una cola de mensajes de Windows propietaria. El enlace de WCF a MSMQ habilita las solicitudes "desencadenar y olvidar" de los clientes que se pueden procesar en cualquier momento en el futuro. gRPC no proporciona de forma nativa ninguna funcionalidad de cola de mensajes. La mejor alternativa sería usar directamente un sistema de mensajería como Azure Service Bus, RabbitMQ o Kafka. Esto podría implementarse con el cliente que coloca los mensajes directamente en la cola o un servicio de streaming de cliente gRPC que pone en cola los mensajes.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (también conocido como ReST de WCF), con los atributos `WebGet` y `WebInvoke`, le permite desarrollar API de ReSTful que podrían hablar de JSON a la vez que era menos común que ahora. Por lo tanto, si tiene una API de RESTful creada con el REST de WCF, considere la posibilidad de migrarla a una aplicación de API Web MVC de ASP.NET Core normal, que proporcionaría una funcionalidad equivalente, en lugar de convertirla en gRPC.

>[!div class="step-by-step"]
>[Anterior](wcf-endpoints-grpc-methods.md)
>[Siguiente](rpc-types.md)
