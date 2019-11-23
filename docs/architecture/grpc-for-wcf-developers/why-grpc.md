---
title: ¿Por qué se recomienda gRPC para desarrolladores de WCF-gRPC para desarrolladores de WCF?
description: Explicación de por qué gRPC es una buena opción para los desarrolladores de WCF que desean migrar a arquitecturas modernas y plataformas.
ms.date: 09/02/2019
ms.openlocfilehash: da712e1ceee92f0a1a2661252dcda602f5dde9a0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966939"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a>Por qué se recomienda gRPC para desarrolladores de WCF

Antes de profundizar en el lenguaje y las técnicas de gRPC, merece la pena analizar por qué gRPC es la solución adecuada para los desarrolladores de WCF que desean migrar a .NET Core, dado que hay alternativas disponibles.

## <a name="similarity-to-wcf"></a>Similitud con WCF

Aunque su implementación y enfoque son diferentes, la experiencia real de desarrollo y consumo de servicios con gRPC debe ser muy intuitiva para los desarrolladores de WCF. El objetivo subyacente de hacer posible el código como si el cliente y el servidor estuvieran en la misma plataforma, sin necesidad de preocuparse por las funciones de red, es el mismo. Ambas plataformas comparten el principio de declarar e implementar una interfaz, aunque el proceso para declarar esa interfaz es diferente. Y como verá en el capítulo 5, los distintos tipos de llamadas RPC admitidas por gRPC se asignan de forma muy adecuada a los diferentes enlaces disponibles para los servicios WCF.

## <a name="benefits-of-grpc"></a>Ventajas de gRPC

Otras razones por las que gRPC está por encima de otras soluciones son:

### <a name="performance"></a>Rendimiento

Como ya se ha explicado, el uso de HTTP/2 en lugar de HTTP/1.1 quita el requisito de los mensajes legibles y, en su lugar, utiliza el protocolo binario más pequeño más rápido. Esto es más eficaz para que los equipos lo analicen. HTTP/2 también admite solicitudes de multiplexación a través de una única conexión que permite enviar respuestas en cuanto estén listas sin necesidad de esperar en una cola (un problema en HTTP/1.1 conocido como "bloqueo de línea de línea (HOL)"). Se necesitan menos recursos cuando se usa gRPC, lo que lo convierte en una buena solución para dispositivos móviles y en redes más lentas.

### <a name="interoperability"></a>Interoperabilidad

Hay herramientas y bibliotecas de gRPC para todos los lenguajes de programación y plataformas principales, como .NET, Java, Python C++, Go,, node. js, SWIFT, DART, Ruby y php. Gracias al uso de los búferes de protocolo formato de conexión binaria y la generación de código eficaz para cada plataforma, los desarrolladores pueden crear aplicaciones de rendimiento y, al mismo tiempo, disfrutar de compatibilidad completa entre plataformas.

### <a name="usability-and-productivity"></a>Facilidad de uso y productividad

gRPC es una solución completa de RPC. Funciona de forma coherente en varios lenguajes y plataformas, y proporciona herramientas excelentes, con gran parte del código reutilizable necesario generado automáticamente, por lo que se libera más tiempo del desarrollador para centrarse en la lógica empresarial.

### <a name="streaming"></a>Streaming

gRPC tiene un streaming bidireccional completo, que proporciona una funcionalidad muy similar a los servicios de dúplex completo de WCF. la transmisión por secuencias de gRPC puede funcionar a través de conexiones de Internet normales, equilibradores de carga y mallas de servicio.

### <a name="deadlinetimeouts-and-cancellation"></a>Fecha límite/tiempos de espera y cancelación

gRPC permite a los clientes especificar un tiempo máximo para que se complete una RPC. Si se supera la fecha límite especificada, el servidor puede cancelar la operación independientemente del cliente. Las fechas límite y cancelaciones se pueden propagar a través de otras llamadas gRPC para ayudar a aplicar los límites de uso de recursos. Los clientes también pueden anular las operaciones cuando se supera una fecha límite, o antes, si es necesario (por ejemplo, debido a una interacción del usuario).

### <a name="security"></a>Seguridad

gRPC es implícitamente seguro cuando se usa HTTP/2 a través de una conexión cifrada de un extremo a otro de TLS. Compatibilidad con la autenticación de certificados de cliente (consulte el capítulo 6) aumenta aún más la seguridad y la confianza entre el cliente y el servidor.

>[!div class="step-by-step"]
>[Anterior](network-protocols.md)
>[Siguiente](protocol-buffers.md)
