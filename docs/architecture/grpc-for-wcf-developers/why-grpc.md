---
title: ¿Por qué se recomienda gRPC para desarrolladores de WCF-gRPC para desarrolladores de WCF?
description: Explicación de por qué gRPC es una buena opción para los desarrolladores de WCF que desean migrar a arquitecturas modernas y plataformas.
ms.date: 12/15/2020
ms.openlocfilehash: 058f85297610116e96c8580fcefb10ee6dfcf935
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97937979"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>¿Por qué se recomienda gRPC para los desarrolladores de WCF?

Antes de profundizar en el lenguaje y las técnicas de gRPC, merece la pena explicar por qué gRPC es la solución adecuada para los desarrolladores de Windows Communication Foundation (WCF) que desean migrar a .NET.

## <a name="similarity-to-wcf"></a>Similitud con WCF

Aunque la implementación y el enfoque son diferentes para gRPC, la experiencia de desarrollo y consumo de servicios con gRPC debe ser intuitiva para los desarrolladores de WCF. El objetivo subyacente es el mismo: hacer posible el código como si el cliente y el servidor estuvieran en la misma plataforma, sin necesidad de preocuparse por las funciones de red.

Ambas plataformas comparten el principio de declarar e implementar una interfaz, aunque el proceso para declarar esa interfaz es diferente. Y como verá en el capítulo 5, los distintos tipos de llamadas RPC que gRPC admite se asignan correctamente a los enlaces disponibles para los servicios WCF.

## <a name="benefits-of-grpc"></a>Ventajas de gRPC

gRPC se sitúa por encima de otras soluciones por los siguientes motivos.

### <a name="performance"></a>Rendimiento

El uso de HTTP/2 en lugar de HTTP/1.1 quita el requisito de los mensajes legibles y, en su lugar, utiliza el protocolo binario más pequeño y más rápido. Esto es más eficaz para que los equipos lo analicen. HTTP/2 también admite las solicitudes de multiplexación a través de una única conexión. Esta compatibilidad permite que las respuestas se envíen en cuanto estén listas sin necesidad de esperar en una cola. (En HTTP/1.1, este problema se conoce como bloqueo del encabezado de línea (HOL)). Necesita menos recursos al usar gRPC, lo que lo convierte en una buena solución para dispositivos móviles y en redes más lentas.

### <a name="interoperability"></a>Interoperabilidad

Hay herramientas y bibliotecas de gRPC para todos los lenguajes de programación y plataformas principales, como .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby y PHP. Gracias al uso de los búferes de protocolo formato de conexión binaria y la generación de código eficaz para cada plataforma, los desarrolladores pueden crear aplicaciones de rendimiento y, al mismo tiempo, disfrutar de compatibilidad completa entre plataformas.

### <a name="usability-and-productivity"></a>Facilidad de uso y productividad

gRPC es una solución completa de RPC. Funciona de forma coherente en varios lenguajes y plataformas. También proporciona excelentes herramientas, con gran parte del código reutilizable necesario generado automáticamente. Por tanto, se libera más tiempo del desarrollador para centrarse en la lógica de negocios.

### <a name="streaming"></a>Streaming

gRPC tiene un streaming bidireccional completo, que proporciona una funcionalidad similar a los servicios completos de WCF. La transmisión por secuencias de gRPC puede funcionar a través de conexiones de Internet normales, equilibradores de carga y mallas de servicio.

### <a name="deadlinetimeouts-and-cancellation"></a>Fecha límite o tiempos de expiración y cancelación

gRPC permite a los clientes especificar el tiempo máximo en que un RPC debe finalizar. Si se supera la fecha límite especificada, el servidor puede cancelar la operación independientemente del cliente. Las fechas límite y cancelaciones se pueden propagar a través de otras llamadas gRPC para ayudar a aplicar los límites de uso de recursos. Los clientes también pueden detener las operaciones cuando se supera una fecha límite, o antes, si es necesario (por ejemplo, debido a una interacción del usuario).

### <a name="security"></a>Seguridad

gRPC es implícitamente seguro cuando se usa HTTP/2 a través de una conexión cifrada de un extremo a otro de TLS. Compatibilidad con la autenticación de certificados de cliente (consulte el [capítulo 6](security.md)) aumenta aún más la seguridad y la confianza entre el cliente y el servidor.

>[!div class="step-by-step"]
>[Anterior](network-protocols.md)
>[Siguiente](protocol-buffers.md)
