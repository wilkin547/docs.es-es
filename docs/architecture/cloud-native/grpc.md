---
title: gRPC
description: Obtenga información sobre gRPC, su rol en aplicaciones nativas de la nube y cómo difiere de la comunicación HTTP RESTful.
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 28a07ad5ec105d3fc5b65e4cf0ac0cd85eb16627
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524212"
---
# <a name="grpc"></a>gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Hasta ahora en este libro, nos hemos centrado en la comunicación [basada en REST.](https://docs.microsoft.com/azure/architecture/best-practices/api-design) Hemos visto que REST es un estilo arquitectónico flexible que define las operaciones basadas en CRUD con los recursos de entidad. Los clientes interactúan con los recursos a través de HTTP con un modelo de comunicación de solicitud/respuesta. Aunque REST está ampliamente implementado, una tecnología de comunicación más reciente, gRPC, ha ganado un gran impulso en toda la comunidad nativa de la nube.

## <a name="what-is-grpc"></a>¿Qué es gRPC?

gRPC es un marco moderno de alto rendimiento que evoluciona el antiguo protocolo de llamada a [procedimiento remoto (RPC).](https://en.wikipedia.org/wiki/Remote_procedure_call) En el nivel de aplicación, gRPC optimiza la mensajería entre clientes y servicios back-end. Originario de Google, gRPC es de código abierto y forma parte del ecosistema de Cloud [Native Computing Foundation (CNCF)](https://www.cncf.io/) de ofertas nativas de la nube. CNCF considera gRPC un proyecto de [incubación.](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc) Incubar significa que los usuarios finales están utilizando la tecnología en aplicaciones de producción, y el proyecto tiene un número saludable de contribuyentes.

Una aplicación cliente gRPC típica expondrá una función local en proceso que implementa una operación empresarial. Debajo de las cubiertas, esa función local invoca otra función en un equipo remoto. Lo que parece ser una llamada local se convierte esencialmente en una llamada transparente fuera de proceso a un servicio remoto. La plomería RPC abstrae la comunicación de red punto a punto, la serialización y la ejecución entre equipos.

En las aplicaciones nativas de la nube, los desarrolladores a menudo trabajan en lenguajes de programación, marcos y tecnologías. Esta *interoperabilidad* complica los contratos de mensajes y la fontanería necesaria para la comunicación multiplataforma.  gRPC proporciona una "capa horizontal uniforme" que abstrae estas preocupaciones. Los desarrolladores codifican en su plataforma nativa centrada en la funcionalidad empresarial, mientras que gRPC se encarga de las tuberías de comunicación.

gRPC ofrece soporte integral en las pilas de desarrollo más populares, incluyendo Java, JavaScript, C, Go, Swift y NodeJS.

## <a name="grpc-benefits"></a>Beneficios de gRPC

gRPC utiliza HTTP/2 para su protocolo de transporte. Aunque es compatible con HTTP 1.1, HTTP/2 cuenta con muchas capacidades avanzadas:

- Un protocolo binario para el transporte de datos, a diferencia de HTTP 1.1, que envía datos como texto no cifrado.
- Compatibilidad con multiplexación para enviar varias solicitudes paralelas a través de la misma conexión: HTTP 1.1 limita el procesamiento a un mensaje de solicitud/respuesta a la vez.
- Comunicación bidireccional dúplex completo para enviar solicitudes de cliente y respuestas de servidor simultáneamente.
- El streaming integrado permite solicitudes y respuestas para transmitir de forma asincrónica grandes conjuntos de datos.

gRPC es ligero y altamente rendimiento. Puede ser hasta 8 veces más rápido que la serialización JSON con mensajes 60-80% más pequeños. En el lenguaje de Microsoft [Windows Communication Foundation (WCF),](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) el rendimiento de gRPC supera la velocidad y la eficiencia de los [enlaces NetTCP altamente optimizados.](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8) A diferencia de NetTCP, que favorece la pila de Microsoft, gRPC es multiplataforma.

## <a name="protocol-buffers"></a>Búferes de protocolo

gRPC adopta una tecnología de código abierto llamada [Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview). Proporcionan un formato de serialización altamente eficiente y neutral para la plataforma para serializar mensajes estructurados que los servicios se envían entre sí. Mediante un lenguaje de definición de interfaz (IDL) multiplataforma, los desarrolladores definen un contrato de servicio para cada microservicio. El contrato, implementado como un `.proto` archivo basado en texto, describe los métodos, entradas y salidas para cada servicio. El mismo archivo de contrato se puede utilizar para clientes y servicios gRPC basados en diferentes plataformas de desarrollo.

Mediante el archivo proto, el `protoc`compilador Protobuf, , genera código de cliente y de servicio para la plataforma de destino. El código incluye los siguientes componentes:

- Objetos fuertemente tipados, compartidos por el cliente y el servicio, que representan las operaciones de servicio y los elementos de datos de un mensaje.
- Una clase base fuertemente tipada con la tubería de red necesaria que el servicio gRPC remoto puede heredar y extender.
- Un código auxiliar de cliente que contiene la fontanería necesaria para invocar el servicio gRPC remoto.

En tiempo de ejecución, cada mensaje se serializa como una representación Protobuf estándar e intercambia entre el cliente y el servicio remoto. A diferencia de JSON o XML, los mensajes Protobuf se serializan como bytes binarios compilados.

El libro, [gRPC para desarrolladores de WCF,](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)disponible en el sitio de arquitectura de Microsoft, proporciona una cobertura detallada de gRPC y búferes de protocolo.

## <a name="grpc-support-in-net"></a>Compatibilidad con gRPC en .NET

gRPC está integrado en el SDK de .NET Core 3.0 o posterior. Las siguientes herramientas lo admiten:

- Visual Studio 2019, versión 16.3 o posterior, con la carga de trabajo de desarrollo web instalada.
- Visual Studio Code
- el DOTnet CLI

El SDK incluye herramientas para el enrutamiento de puntos de conexión, IoC integrado y registro. El servidor web Kestrel de código abierto admite conexiones HTTP/2. En la figura 4-20 se muestra una plantilla de Visual Studio 2019 que aplica scaffolding a un proyecto de esqueleto para un servicio gRPC. Observe cómo .NET Core es totalmente compatible con Windows, Linux y macOS.

![Compatibilidad con gRPC en Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Figura 4-20**. Compatibilidad con gRPC en Visual Studio 2019
  
En la figura 4-21 se muestra el servicio gRPC de esqueleto generado a partir del andamiaje integrado incluido en Visual Studio 2019.  

![proyecto gRPC en Visual Studio 2019](./media/grpc-project.png  )

**Figura 4-21**. proyecto gRPC en Visual Studio 2019

En la figura anterior, tenga en cuenta el archivo de descripción proto y el código de servicio. Como verá en breve, Visual Studio genera una configuración adicional tanto en la clase Startup como en el archivo de proyecto subyacente.

## <a name="grpc-usage"></a>uso de gRPC

Favorecer gRPC para los siguientes escenarios:

- Comunicación sincrónica de microservicio a microservicio de back-end donde se requiere una respuesta inmediata para continuar el procesamiento.
- Entornos políglotas que necesitan admitir plataformas de programación mixtas.
- Baja latencia y comunicación de alto rendimiento donde el rendimiento es crítico.
- Comunicación punto a punto en tiempo real: gRPC puede enviar mensajes en tiempo real sin sondeo y tiene un excelente soporte para streaming bidireccional.
- Entornos restringidos en red: los mensajes gRPC binarios siempre son más pequeños que un mensaje JSON basado en texto equivalente.

En ese momento, de esta escritura, gRPC se utiliza principalmente con servicios back-end. La mayoría de los navegadores modernos no pueden proporcionar el nivel de control HTTP/2 necesario para admitir un cliente gRPC front-end. Dicho esto, hay una [iniciativa temprana](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) que permite la comunicación gRPC desde aplicaciones basadas en navegador creadas con tecnologías JavaScript o Blazor WebAssembly. [GRPC-Web para .NET](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) permite que una aplicación gRPC de ASP.NET Core admita las características de gRPC en las aplicaciones del explorador:

- Clientes generados por código fuertemente tipados
- Mensajes compactos de Protobuf
- Transmisión de servidores

## <a name="grpc-implementation"></a>implementación de gRPC

La arquitectura de referencia de microservicios, [eShop on Containers](https://github.com/dotnet-architecture/eShopOnContainers), de Microsoft, muestra cómo implementar servicios gRPC en aplicaciones de .NET Core. La Figura 4-22 presenta la arquitectura de back-end.

![Arquitectura de back-end para eShop en contenedores](./media/eshop-with-aggregators.png)

**Figura 4-22**. Arquitectura de back-end para eShop en contenedores

En la figura anterior, observe cómo eShop adopta el [patrón backend for Frontends](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) (BFF) exponiendo varias puertas de enlace de API. Hemos discutido el patrón BFF anteriormente en este capítulo. Preste mucha atención al microservicio de Agregador (en gris) que se encuentra entre la puerta de enlace de API de Web-Shopping y los microservicios de Shopping de back-end. El agregador recibe una única solicitud de un cliente, la distribuye a varios microservicios, agrega los resultados y los devuelve al cliente solicitante. Estas operaciones normalmente requieren comunicación sincrónica para producir una respuesta inmediata. En eShop, las llamadas de back-end desde el agregador se realizan mediante gRPC como se muestra en la figura 4-23.

![gRPC en eShop en contenedores](./media/grpc-implementation.png)

**Figura 4-23**. gRPC en eShop en contenedores

La comunicación gRPC requiere componentes de cliente y servidor. En la figura anterior, observe cómo el agregador de compras implementa un cliente gRPC. El cliente realiza llamadas gRPC sincrónicas (en rojo) a microservicios de back-end, cada uno de los cuales implementa un servidor gRPC. Tanto el cliente como el servidor aprovechan la plomería gRPC integrada desde el SDK de .NET Core 3.0. Los *stubs* del lado cliente proporcionan la plomería para invocar llamadas gRPC remotas. Los componentes del lado del servidor proporcionan la plomería gRPC que las clases de servicio personalizadas pueden heredar y consumir.

Los microservicios que exponen una API RESTful y una comunicación gRPC requieren varios puntos de conexión para administrar el tráfico. Abriría un punto de conexión que escuche el tráfico HTTP para las llamadas RESTful y otro para las llamadas gRPC. El punto final gRPC se debe configurar para el protocolo HTTP/2 que se requiere para la comunicación gRPC.

Aunque nos esforzamos por desacoplar microservicios con patrones de comunicación asincrónicos, algunas operaciones requieren llamadas directas. gRPC debe ser la opción principal para la comunicación sincrónica directa entre microservicios. Su protocolo de comunicación de alto rendimiento, basado en HTTP/2 y búferes de protocolo, lo convierten en una opción perfecta.

## <a name="looking-ahead"></a>Mirando hacia el futuro

De cara al futuro, gRPC seguirá ganando tracción para los sistemas nativos de la nube. Los beneficios de rendimiento y la facilidad de desarrollo son convincentes. Sin embargo, es probable que REST esté por aquí durante mucho tiempo. Se destaca por las API expuestas públicamente y por razones de compatibilidad con versiones anteriores.

>[!div class="step-by-step"]
>[Anterior](service-to-service-communication.md)
>[Siguiente](service-mesh-communication-infrastructure.md)
