---
title: gRPC
description: Obtenga información sobre gRPC, su rol en aplicaciones nativas de la nube y cómo difiere de la comunicación HTTP RESTful.
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 01dd4c934f0b39041ea377691067edf4dbe20378
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895568"
---
# <a name="grpc"></a>gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Hasta ahora en este libro nos hemos centrado en la comunicación [basada en REST](https://docs.microsoft.com/azure/architecture/best-practices/api-design) . Hemos visto que REST es un estilo arquitectónico flexible que define las operaciones basadas en CRUD en recursos de entidad. Los clientes interactúan con los recursos a través de HTTP con un modelo de comunicación de solicitud-respuesta. Aunque REST está ampliamente implementado, una tecnología de comunicación más reciente, gRPC, ha obtenido un gran impulso de la comunidad nativa en la nube.

## <a name="what-is-grpc"></a>¿Qué es gRPC?

gRPC es un marco de trabajo moderno y de alto rendimiento que evoluciona el protocolo de [llamada a procedimiento remoto (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) de edad antiguo. En el nivel de aplicación, gRPC simplifica la mensajería entre los clientes y los servicios back-end. Desde Google, gRPC es código abierto y forma parte del ecosistema de [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) de las ofertas nativas de la nube. CNCF considera gRPC un proyecto en el que se está [incubando](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc). La incubación significa que los usuarios finales usan la tecnología de las aplicaciones de producción y el proyecto tiene un número correcto de colaboradores.

Una aplicación cliente gRPC típica expondrá una función local y en proceso que implementa una operación empresarial. En segundo plano, esa función local invoca a otra función en un equipo remoto. Lo que parece ser una llamada local se convierte esencialmente en una llamada fuera de proceso transparente a un servicio remoto. La fontanería de RPC abstrae la comunicación de red punto a punto, la serialización y la ejecución entre equipos.

En aplicaciones nativas en la nube, los desarrolladores suelen trabajar en lenguajes de programación, marcos y tecnologías. Esta *interoperabilidad* complica los contratos de mensajes y la fontanería necesaria para la comunicación entre plataformas.  gRPC proporciona una "capa horizontal uniforme" que abstrae estas preocupaciones. Los desarrolladores codifican en su plataforma nativa centrada en la funcionalidad empresarial, mientras que gRPC controla la fontanería de la comunicación.

gRPC ofrece compatibilidad completa en las pilas de desarrollo más populares, como Java, JavaScript, C#, Go, SWIFT y NodeJS.

## <a name="grpc-benefits"></a>Ventajas de gRPC

gRPC usa HTTP/2 para su Protocolo de transporte. Aunque es compatible con HTTP 1,1, las características de HTTP/2 tienen muchas capacidades avanzadas:

- Un protocolo binario para el transporte de datos, a diferencia de HTTP 1,1, que envía los datos como texto sin cifrar.
- Compatibilidad con multiplexación para enviar varias solicitudes paralelas a través de la misma conexión: HTTP 1,1 limita el procesamiento a un mensaje de solicitud/respuesta a la vez.
- Comunicación dúplex completa bidireccional para enviar solicitudes de cliente y respuestas de servidor simultáneamente.
- Streaming integrado que habilita las solicitudes y respuestas para transmitir conjuntos de datos grandes de forma asincrónica.

gRPC es ligero y de alto rendimiento. Puede ser hasta 8X más rápido que la serialización de JSON con mensajes 60-80% más pequeños. En el lenguaje de Microsoft [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) , el rendimiento de gRPC supera la velocidad y la eficacia de los [enlaces de NetTCP](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)altamente optimizados. A diferencia de NetTCP, que favorece la pila de Microsoft, gRPC es multiplataforma.

## <a name="protocol-buffers"></a>Búferes de protocolo

gRPC adopta una tecnología de código abierto denominada [búferes de protocolo](https://developers.google.com/protocol-buffers/docs/overview). Proporcionan un formato de serialización neutro y de alta eficacia de la plataforma para serializar los mensajes estructurados que los servicios envían entre sí. Con un lenguaje de definición de interfaz (IDL) multiplataforma, los desarrolladores definen un contrato de servicio para cada microservicio. El contrato, implementado como un archivo basado `.proto` en texto, describe los métodos, las entradas y las salidas de cada servicio. Se puede usar el mismo archivo de contrato para clientes y servicios de gRPC creados en distintas plataformas de desarrollo.

Mediante el uso del archivo proto, el compilador protobuf, `protoc`, genera código de cliente y servicio para la plataforma de destino. El código incluye los componentes siguientes:

- Objetos fuertemente tipados, compartidos por el cliente y el servicio, que representan las operaciones de servicio y los elementos de datos de un mensaje.
- Una clase base fuertemente tipada con la infraestructura de red necesaria que el servicio gRPC remoto puede heredar y extender.
- Código auxiliar de cliente que contiene la fontanería necesaria para invocar el servicio gRPC remoto.

En tiempo de ejecución, cada mensaje se serializa como una representación de protobuf estándar y se intercambia entre el cliente y el servicio remoto. A diferencia de JSON o XML, los mensajes protobuf se serializan como bytes binarios compilados.

El libro [gRPC para desarrolladores de WCF](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/), disponible en el sitio de la arquitectura de Microsoft, proporciona una cobertura detallada de los búferes de GRPC y protocolo.

## <a name="grpc-support-in-net"></a>compatibilidad con gRPC en .NET

gRPC está integrado en el SDK de .NET Core 3,0 y versiones posteriores. Las siguientes herramientas lo admiten:

- Visual Studio 2019, versión 16,3 o posterior, con la carga de trabajo de desarrollo web instalada.
- Visual Studio Code
- la CLI de dotnet

El SDK incluye herramientas para el enrutamiento de puntos de conexión, IoC integrado y registro. El servidor Web Kestrel de código abierto admite conexiones HTTP/2. En la figura 4-20 se muestra una plantilla de Visual Studio 2019 que scaffolding un proyecto de esqueleto para un servicio de gRPC. Tenga en cuenta que .NET Core es totalmente compatible con Windows, Linux y macOS.

![Compatibilidad con gRPC en Visual Studio 2019](./media/visual-studio-2019-grpc-template.png)

**Figura 4-20**. compatibilidad con gRPC en Visual Studio 2019
  
En la figura 4-21 se muestra el esqueleto del servicio gRPC generado a partir de la técnica scaffolding integrada incluida en Visual Studio 2019.  

![proyecto gRPC en Visual Studio 2019](./media/grpc-project.png  )

**Figura 4-21**. proyecto gRPC en Visual Studio 2019

En la ilustración anterior, tenga en cuenta el archivo de descripción de proto y el código de servicio. Como verá en breve, Visual Studio genera una configuración adicional en la clase de inicio y en el archivo de proyecto subyacente.

## <a name="grpc-usage"></a>uso de gRPC

Favorecer gRPC para los siguientes escenarios:

- Comunicación de microservicios de back-end sincrónica a microservicios donde se requiere una respuesta inmediata para continuar el procesamiento.
- Entornos polyglot que necesitan admitir plataformas de programación mixtas.
- Baja latencia y comunicación de alto rendimiento donde el rendimiento es crítico.
- Comunicación en tiempo real de punto a punto: gRPC puede enviar mensajes en tiempo real sin sondeo y tiene una excelente compatibilidad para el streaming bidireccional.
- Entornos con restricción de red: los mensajes gRPC binarios siempre son más pequeños que un mensaje JSON basado en texto equivalente.

En el momento en que se redactó este documento, gRPC se usa principalmente con los servicios back-end. La mayoría de los exploradores modernos no pueden proporcionar el nivel de control HTTP/2 necesario para admitir un cliente de gRPC de front-end. Dicho esto, hay una [iniciativa temprana](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) que permite la comunicación de gRPC desde aplicaciones basadas en explorador creadas con tecnologías webassembly de JavaScript o increíbles. [GRPC-web para .net](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) permite que una aplicación ASP.net Core gRPC admita características de gRPC en aplicaciones de explorador:

- Clientes generados por código fuertemente tipados
- Mensajes protobuf de Compact
- Streaming de servidor

## <a name="grpc-implementation"></a>implementación de gRPC

La arquitectura de referencia de microservicios, [eShop en contenedores](https://github.com/dotnet-architecture/eShopOnContainers), de Microsoft, muestra cómo implementar gRPC Services en aplicaciones de .net Core. En la figura 4-22 se presenta la arquitectura de back-end.

![Arquitectura de back-end para eShop en contenedores](./media/eshop-with-aggregators.png)

**Figura 4-22**. Arquitectura de back-end para eShop en contenedores

En la ilustración anterior, observe cómo eShop adopta el [back-end para el patrón de Front](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) -ends (BFF) exponiendo varias puertas de enlace de API. En este capítulo se describe el patrón BFF. Preste mucha atención al microservicio del agregador (en gris) que se encuentra entre la puerta de enlace de API de la compra web y los microservicios de compra de back-end. El agregador recibe una única solicitud de un cliente, la envía a varios microservicios, agrega los resultados y los devuelve al cliente que realiza la solicitud. Estas operaciones suelen requerir la comunicación sincrónica como para generar una respuesta inmediata. En eShop, las llamadas de back-end del agregador se realizan mediante gRPC como se muestra en la figura 4-23.

![gRPC en eShop en contenedores](./media/grpc-implementation.png)

**Figura 4-23**. gRPC en eShop en contenedores

la comunicación de gRPC requiere componentes de cliente y de servidor. En la ilustración anterior, observe cómo el agregador de compras implementa un cliente de gRPC. El cliente realiza llamadas sincrónicas de gRPC (en rojo) a microservicios de back-end, cada una de las cuales implementa un servidor de gRPC. Tanto el cliente como el servidor aprovechan las ventajas de la estructura gRPC integrada desde el SDK de .NET Core. El *código auxiliar* del lado cliente proporciona la fontanería para invocar llamadas gRPC remotas. Los componentes del lado servidor proporcionan mecanismos gRPC que las clases de servicio personalizadas pueden heredar y consumir.

Los microservicios que exponen una API de RESTful y la comunicación de gRPC requieren varios puntos de conexión para administrar el tráfico. Abriría un punto de conexión que escucha el tráfico HTTP para las llamadas RESTful y otro para llamadas gRPC. El punto de conexión de gRPC debe configurarse para el protocolo HTTP/2 que se requiere para la comunicación de gRPC.

Aunque nos esforzamos por desacoplar los microservicios con patrones de comunicación asincrónica, algunas operaciones requieren llamadas directas. gRPC debe ser la opción principal para la comunicación sincrónica directa entre microservicios. Su Protocolo de comunicación de alto rendimiento, basado en HTTP/2 y los búferes de protocolo, lo convierten en una opción perfecta.

## <a name="looking-ahead"></a>Mirar hacia arriba

En el futuro, gRPC continuará ganando tracción para sistemas nativos en la nube. Las ventajas de rendimiento y la facilidad de desarrollo son atractivas. Sin embargo, es probable que REST esté aproximadamente durante mucho tiempo. Excel es para las API expuestas públicamente y por motivos de compatibilidad con versiones anteriores.

>[!div class="step-by-step"]
>[Anterior](service-to-service-communication.md)
>[Siguiente](service-mesh-communication-infrastructure.md)
