---
title: Enlaces y transportes de WCF - gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo los diferentes enlaces y transportes de WCF se comparan con gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147729"
---
# <a name="wcf-bindings-and-transports"></a>Enlaces y transportes de WCF

Windows Communication Foundation (WCF) tiene *enlaces integrados* que especifican diferentes protocolos de red, formatos de cable y otros detalles de implementación. gRPC tiene efectivamente un solo protocolo de red y un formato de cable. (Técnicamente *puede* personalizar el formato de cable, pero eso está fuera del alcance de este libro.) Es probable que descubra que gRPC ofrece la mejor solución en la mayoría de los casos.

Lo que sigue es una breve discusión sobre los enlaces WCF más relevantes y cómo se comparan con sus equivalentes en gRPC.

## <a name="nettcp"></a>NetTCP

Enlace NetTCP de WCF permite conexiones persistentes, mensajes pequeños y mensajería bidireccional. Pero solo funciona entre servidores y clientes de .NET. gRPC permite la misma funcionalidad, pero es compatible con múltiples lenguajes de programación y plataformas.

gRPC tiene muchas características del enlace NetTCP de WCF, pero no siempre se implementan de la misma manera. Por ejemplo, en WCF, el cifrado se controla a través de la configuración y se controla en el marco de trabajo. En gRPC, el cifrado se logra en el nivel de conexión a través de HTTP/2 a través de TLS.

## <a name="http"></a>HTTP

El enlace WCF denominado BasicHttpBinding suele basarse en texto y usa SOAP como formato de cable. Es lento en comparación con el enlace NetTCP. Por lo general, se utiliza para proporcionar interoperabilidad multiplataforma o conexión a través de infraestructura de Internet.

El equivalente en gRPC utiliza HTTP/2 como capa de transporte subyacente con el formato de cable Protobuf binario para los mensajes. Por lo tanto, puede ofrecer rendimiento en el nivel de servicio NetTCP y una interoperabilidad multiplataforma completa con todos los lenguajes y marcos de programación modernos.

## <a name="named-pipes"></a>Canalizaciones con nombre

WCF proporciona un enlace de *canalizaciones con nombre* para la comunicación entre procesos en el mismo equipo físico. La primera versión de ASP.NET Core gRPC no admite canalizaciones con nombre. Agregar compatibilidad con el cliente y el servidor para canalizaciones con nombre (y sockets de dominio Unix) es un objetivo para una versión futura.

## <a name="msmq"></a>MSMQ

MSMQ es una cola de mensajes de Windows propietaria. El enlace de WCF a MSMQ habilita las solicitudes de "fuego y olvido" de los clientes que se pueden procesar en cualquier momento en el futuro. gRPC no proporciona de forma nativa ninguna funcionalidad de cola de mensajes.

La mejor alternativa es usar directamente un sistema de mensajería como Azure Service Bus, RabbitMQ o Kafka. Puede implementar esto con el cliente colocando mensajes directamente en la cola o un servicio de streaming de cliente gRPC que pone en cola los mensajes.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (también conocido como REST `WebGet` `WebInvoke` de WCF), con los atributos y, le permitió desarrollar API RESTful que podrían hablar JSON en un momento en que esto era menos común. Si tiene una API RESTful compilada con REST de WCF, considere la posibilidad de migrarla a una aplicación de API web Mvc de ASP.NET normal. Esta migración proporcionaría la misma funcionalidad que una conversión a gRPC.

>[!div class="step-by-step"]
>[Anterior](wcf-endpoints-grpc-methods.md)
>[Siguiente](rpc-types.md)
