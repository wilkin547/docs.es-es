---
title: Por qué recomendamos gRPC para desarrolladores de WCF - gRPC para desarrolladores de WCF
description: Una explicación de por qué gRPC es una buena opción para los desarrolladores de WCF que desean migrar a arquitecturas y plataformas modernas.
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147651"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a>¿Por qué se recomienda gRPC para los desarrolladores de WCF?

Antes de profundizar en el lenguaje y las técnicas de gRPC, vale la pena analizar por qué gRPC es la solución adecuada para los desarrolladores de Windows Communication Foundation (WCF) que desean migrar a .NET Core.

## <a name="similarity-to-wcf"></a>Similitud con WCF

Aunque la implementación y el enfoque son diferentes para gRPC, la experiencia de desarrollar y consumir servicios con gRPC debe ser intuitiva para los desarrolladores de WCF. El objetivo subyacente es el mismo: hacer posible codificar como si el cliente y el servidor estuvieran en la misma plataforma, sin tener que preocuparse por las redes.

Ambas plataformas comparten el principio de declarar y luego implementar una interfaz, aunque el proceso para declarar esa interfaz es diferente. Y como verá en el capítulo 5, los diferentes tipos de llamadas RPC que gRPC admite se asignan bien a los enlaces disponibles para los servicios WCF.

## <a name="benefits-of-grpc"></a>Beneficios de gRPC

gRPC se encuentra por encima de otras soluciones por las siguientes razones.

### <a name="performance"></a>Rendimiento

El uso de HTTP/2 en lugar de HTTP/1.1 elimina el requisito de mensajes legibles por humanos y, en su lugar, utiliza el protocolo binario más pequeño y más rápido. Esto es más eficaz para que los equipos analicen. HTTP/2 también admite solicitudes de multiplexación a través de una sola conexión. Esta compatibilidad permite que las respuestas se envíen tan pronto como estén listas sin necesidad de esperar en una cola. (En HTTP/1.1, este problema se conoce como "bloqueo de cabeza de línea (HOL).") Necesita menos recursos al usar gRPC, lo que lo convierte en una buena solución para dispositivos móviles y a través de redes más lentas.

### <a name="interoperability"></a>Interoperabilidad

Hay herramientas y bibliotecas gRPC para todos los principales lenguajes de programación y plataformas, incluyendo .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby y PHP. Gracias al formato de cable binario Protocol Buffers y a la generación de código eficiente para cada plataforma, los desarrolladores pueden crear aplicaciones eficaces mientras disfrutan de soporte multiplataforma completo.

### <a name="usability-and-productivity"></a>Facilidad de uso y productividad

gRPC es una solución RPC integral. Funciona constantemente en varios idiomas y plataformas. También proporciona excelentes herramientas, con gran parte del código reutilizable necesario generado automáticamente. Por lo tanto, se libera más tiempo para desarrolladores para centrarse en la lógica empresarial.

### <a name="streaming"></a>Streaming

gRPC tiene streaming bidireccional completo, que proporciona una funcionalidad similar a los servicios dúplex completos de WCF. La transmisión por secuencias gRPC puede operar a través de conexiones a Internet regulares, equilibradores de carga y mallas de servicio.

### <a name="deadlinetimeouts-and-cancellation"></a>Plazos y cancelación

gRPC permite a los clientes especificar un tiempo máximo para que un RPC finalice. Si se supera la fecha límite especificada, el servidor puede cancelar la operación independientemente del cliente. Los plazos y las cancelaciones se pueden propagar a través de otras llamadas gRPC para ayudar a aplicar los límites de uso de recursos. Los clientes también pueden detener las operaciones cuando se supera una fecha límite, o antes si es necesario (por ejemplo, debido a una interacción del usuario).

### <a name="security"></a>Seguridad

gRPC es implícitamente seguro cuando se utiliza HTTP/2 a través de una conexión cifrada de extremo a extremo TLS. La compatibilidad con la autenticación de certificados de cliente (consulte el [capítulo 6](security.md)) aumenta aún más la seguridad y la confianza entre el cliente y el servidor.

>[!div class="step-by-step"]
>[Anterior](network-protocols.md)
>[Siguiente](protocol-buffers.md)
