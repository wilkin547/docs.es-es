---
title: 'Protocolos de red: gRPC para desarrolladores de WCF'
description: Información general de los protocolos de red gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 801d57c95aec748e5dcf667ca480775ff945b55c
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938564"
---
# <a name="network-protocols"></a>Protocolos de red

A diferencia de Windows Communication Foundation (WCF), gRPC usa HTTP/2 como base para sus redes. Este protocolo ofrece ventajas significativas con respecto a WCF y SOAP, que solo funcionan en HTTP/1.1. Para los desarrolladores que desean usar gRPC, dado que no hay ninguna alternativa a HTTP/2, parece ser el momento ideal para explorar HTTP/2 con más detalle e identificar las ventajas adicionales del uso de gRPC.

HTTP/2, publicado por Internet Engineering Task Force en 2015, se deriva del protocolo SPDY experimental, que ya estaba siendo usado por Google. Se diseñó específicamente para ser más eficaz, más rápido y más seguro que HTTP/1.1.

## <a name="key-features-of-http2"></a>Características clave de HTTP/2

Esta lista muestra algunas de las principales características y ventajas de HTTP/2:

### <a name="binary-protocol"></a>Protocolo binario

Los ciclos de solicitud/respuesta ya no necesitan comandos de texto. Esta actividad simplifica y acelera la implementación de comandos. En concreto, el análisis de los datos es más rápido y usa menos memoria, la latencia de red se reduce con mejoras obvias relacionadas con la velocidad y existe un mejor uso de los recursos de red.

### <a name="streams"></a>Secuencias

Las secuencias permiten crear conexiones de larga duración entre el remitente y el receptor, a través de la cual se pueden enviar varios mensajes o fotogramas de forma asincrónica. Varias secuencias pueden funcionar de forma independiente a través de una única conexión HTTP/2.

### <a name="request-multiplexing-over-a-single-tcp-connection"></a>Solicitar multiplexación a través de una única conexión TCP

Esta característica es una de las innovaciones más importantes de HTTP/2. Dado que permite varias solicitudes paralelas de datos, ahora es posible descargar archivos Web simultáneamente desde un único servidor. Los sitios web se cargan más rápido y se reduce la necesidad de optimización. Bloqueo del cabezal de línea (HOL), donde las respuestas que están preparadas deben esperar a ser enviadas hasta que se complete una solicitud anterior, también se mitiga (aunque el bloqueo de HOL todavía puede producirse en el nivel de transporte TCP).

### <a name="nettcp-like-performance-cross-platform"></a>Rendimiento similar a net. TCP, entre plataformas

Fundamentalmente, la combinación de gRPC y HTTP/2 ofrece a los desarrolladores al menos la velocidad y eficiencia equivalentes de los enlaces net. TCP para WCF, y en algunos casos, incluso mayor velocidad y eficacia. Sin embargo, a diferencia de net. TCP, gRPC sobre HTTP/2 no está restringido a las aplicaciones .NET.

>[!div class="step-by-step"]
>[Anterior](interface-definition-language.md)
>[Siguiente](why-grpc.md)
