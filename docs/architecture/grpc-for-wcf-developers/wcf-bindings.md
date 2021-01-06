---
title: Enlaces y transportes de WCF-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo se comparan los distintos enlaces y transportes de WCF con gRPC.
ms.date: 12/15/2020
ms.openlocfilehash: 7a50e3e4468d86a6140066502a765818119642d4
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938512"
---
# <a name="wcf-bindings-and-transports"></a>Enlaces y transportes de WCF

Windows Communication Foundation (WCF) tiene *enlaces* integrados que especifican diferentes protocolos de red, formatos de conexión y otros detalles de la implementación. gRPC eficazmente tiene un solo protocolo de red y un formato de conexión. (Técnicamente, *puede* personalizar el formato de conexión, pero está fuera del ámbito de este libro). Es probable que descubra que gRPC ofrece la mejor solución en la mayoría de los casos.

A continuación se muestra una breve explicación sobre los enlaces de WCF más relevantes y cómo se comparan con sus equivalentes en gRPC.

## <a name="nettcp"></a>NetTCP

El enlace NetTCP de WCF permite conexiones persistentes, mensajes pequeños y mensajería bidireccional. Pero solo funciona entre clientes y servidores .NET. gRPC permite la misma funcionalidad, pero se admite en varios lenguajes de programación y plataformas.

gRPC tiene muchas características del enlace NetTCP de WCF, pero no siempre se implementan de la misma manera. Por ejemplo, en WCF, el cifrado se controla a través de la configuración y se controla en el marco. En gRPC, el cifrado se consigue en el nivel de conexión a través de HTTP/2 a través de TLS.

## <a name="http"></a>HTTP

El enlace de WCF denominado BasicHttpBinding suele estar basado en texto y usa SOAP como formato de conexión. Es lenta en comparación con el enlace NetTCP. Se usa para proporcionar interoperabilidad entre plataformas o conexión a través de la infraestructura de Internet.

El equivalente en gRPC usa HTTP/2 como la capa de transporte subyacente con el formato de conexión protobuf binaria para los mensajes. Por lo tanto, puede ofrecer rendimiento en el nivel de servicio de NetTCP y una interoperabilidad completa entre plataformas con todos los lenguajes y marcos de programación modernos.

## <a name="named-pipes"></a>Canalizaciones con nombre

WCF proporcionó un enlace de *canalizaciones con nombre* para la comunicación entre procesos en el mismo equipo físico. La primera versión de ASP.NET Core gRPC no admite canalizaciones con nombre. Agregar compatibilidad de cliente y servidor para canalizaciones con nombre (y sockets de dominio de UNIX) es un objetivo para una versión futura.

## <a name="msmq"></a>MSMQ

MSMQ es una cola de mensajes de Windows propietaria. El enlace de WCF a MSMQ habilita las solicitudes "desencadenar y olvidar" de los clientes que podrían procesarse en cualquier momento en el futuro. gRPC no proporciona de forma nativa ninguna funcionalidad de cola de mensajes.

La mejor alternativa es usar directamente un sistema de mensajería como Azure Service Bus, RabbitMQ o Kafka. Puede implementar esta funcionalidad con el cliente que coloca los mensajes directamente en la cola o un servicio de streaming de cliente gRPC que pone en cola los mensajes.

## <a name="webhttpbinding"></a>WebHttpBinding

WebHttpBinding (también conocido como REST de WCF), con `WebGet` los `WebInvoke` atributos y, le permite desarrollar API de RESTful que podrían hablar de JSON a la vez cuando este comportamiento era menos frecuente. Si tiene una API de RESTful creada con el REST de WCF, considere la posibilidad de migrarla a una aplicación de API Web MVC normal ASP.NET Core. Esta migración proporcionaría la misma funcionalidad que la conversión a gRPC.

>[!div class="step-by-step"]
>[Anterior](wcf-endpoints-grpc-methods.md)
>[Siguiente](rpc-types.md)
