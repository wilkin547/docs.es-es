---
title: Dapr a 20 000 pies
description: Información general de alto nivel sobre qué es DAPR, qué hace y cómo funciona.
author: robvet
ms.date: 02/07/2021
ms.openlocfilehash: c6157d29274df73f6ea1fef44b8e5cd5d0239471
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401902"
---
# <a name="dapr-at-20000-feet"></a>Dapr a 20 000 pies

En el capítulo 1, analizamos la apelación de las aplicaciones de microservicios distribuidas. Pero también señalamos que aumentan drásticamente la complejidad de la arquitectura y la operativa. Con eso en mente, la pregunta se convierte en, ¿cómo puede "tener su tarta" y "comer también?". Es decir, ¿cómo puede aprovechar la agilidad de la arquitectura distribuida y minimizar la complejidad?

DAPR, o *aplicación distribuida en tiempo de ejecución*, es una nueva forma de crear aplicaciones distribuidas modernas.

Lo que comenzó como prototipo ha evolucionado a un proyecto de código abierto con una gran capacidad de éxito. Su patrocinador, Microsoft, ha colaborado estrechamente con los clientes y la comunidad de código abierto para diseñar y compilar DAPR. El proyecto DAPR reúne a los desarrolladores de todos los conocimientos para resolver algunos de los desafíos más difíciles de desarrollar aplicaciones distribuidas.

Este libro examina DAPR desde el punto de vista de un desarrollador de .NET. En este capítulo, creará un conocimiento conceptual de DAPR y cómo funciona. Más adelante, presentamos instrucciones prácticas y prácticas sobre cómo puede usar DAPR en sus aplicaciones.

Imagine volar en un inyector de 20.000 metros. Examine la ventana y vea el panorama siguiente desde una perspectiva ancha. Vamos a hacer lo mismo para DAPR. Visualice la DAPR en 20.000 pies. ¿Qué se verá?

## <a name="dapr-and-the-problem-it-solves"></a>DAPR y el problema que soluciona

DAPR aborda un gran desafío inherente a las modernas aplicaciones distribuidas: **complejidad**.

A través de una arquitectura de componentes conectables, DAPR simplifica considerablemente la fontanería detrás de las aplicaciones distribuidas. Proporciona un **pegado dinámico** que enlaza la aplicación con las funcionalidades de infraestructura del tiempo de ejecución de DAPR. Por ejemplo, puede que la aplicación requiera un almacén de estado. Podría escribir código personalizado para Redis Cache de destino e insertarlo en el servicio en tiempo de ejecución. Sin embargo, DAPR simplifica su experiencia al proporcionar una funcionalidad de caché distribuida de forma rápida. El servicio invoca un bloque de **creación** de DAPR que se enlaza dinámicamente con Redis cache **componente** a través de una **configuración** de DAPR. Con este modelo, el servicio delega la llamada a DAPR, que llama a Redis en su nombre. El servicio no tiene ningún SDK, biblioteca o referencia directa a Redis. Puede codificar con la API de administración de estado de DAPR comunes, no con Redis Cache API.

En la figura 2-1 se muestra DAPR de 20.000 pies.

![DAPR en 20.000 pies, ](./media/dapr-at-20000-feet/dapr-high-level.png)
 **figura 2-1**. DAPR a 20.000 pies.

En la fila superior de la ilustración, observe cómo DAPR proporciona SDK específicos del lenguaje para plataformas de desarrollo populares. DAPR v 1,0 incluye compatibilidad con Go, Node.js, Python, .NET, Java y JavaScript. Este libro se centra en el SDK de .NET de DAPR, que también proporciona compatibilidad directa para la integración de ASP.NET Core.

Aunque los SDK específicos del lenguaje mejoran la experiencia del desarrollador, DAPR es independiente de la plataforma. En segundo plano, el modelo de programación de DAPR expone funcionalidades a través de los protocolos de comunicación HTTP/gRPC estándar. Cualquier plataforma de programación puede llamar a DAPR a través de sus API de gRPC y HTTP nativas.  

Los cuadros azules en el centro de la ilustración representan los bloques de creación de DAPR. Cada una de ellas expone una capacidad de aplicación distribuida que la aplicación puede consumir.

La fila inferior resalta la portabilidad de DAPR y los diversos entornos en los que se puede ejecutar.

## <a name="dapr-architecture"></a>Arquitectura de DAPR

Llegados a este punto, el inyector vuelve a activarse y retroceder por DAPR, en orden descendente, lo que le da una visión más detallada de cómo funciona DAPR.

### <a name="building-blocks"></a>Bloques de creación

Desde la nueva perspectiva, verá una vista más detallada de los bloques de **creación** de DAPR.

Un bloque de creación encapsula una funcionalidad de infraestructura distribuida. Puede tener acceso a la funcionalidad a través de las API HTTP o gRPC. En la figura 2-2 se muestran los bloques disponibles para DAPR v 1,0.

![Bloques de creación de DAPR](./media/dapr-at-20000-feet/building-blocks.png)

**Figura 2-2**. Bloques de creación de DAPR.

En la tabla siguiente se describen los servicios de infraestructura que proporciona cada bloque.

| Bloque de creación | Descripción |
|----------------|-------------|
| [Administración de estados](state-management.md) | Admitir información contextual para servicios con estado de larga ejecución. |
| [Invocación de servicio](service-invocation.md) | Invocar llamadas directas y seguras entre servicios mediante protocolos independientes de la plataforma y puntos de conexión conocidos. |
| [Publicar y suscribirse](publish-subscribe.md) | Implemente mensajería de pub/sub escalable y segura entre los servicios. |
| [Enlaces](bindings.md) | Desencadene código a partir de eventos generados por recursos externos con comunicación bidireccional. |
| [Observabilidad](observability.md) | Supervisar y medir llamadas de mensajes en servicios en red. |
| [Secretos](secrets.md) | Acceder de forma segura a los almacenes secretos externos. |
| Actores | Encapsular la lógica y los datos en objetos de actor reutilizables. |

Los bloques de creación abstraen la implementación de las capacidades de aplicación distribuida de los servicios. En la figura 2-3 se muestra esta interacción.

![Integración de DAPR Building Blocks](./media/dapr-at-20000-feet/building-blocks-integration.png)

**Figura 2-3**. DAPR integración de bloques de creación.

Los bloques de creación invocan los componentes de DAPR que proporcionan la implementación concreta para cada recurso. El código del servicio solo tiene en cuenta el bloque de creación. No tiene dependencias en SDK o bibliotecas externos: DAPR controla la fontanería por usted. Cada bloque de creación es independiente. Puede usar una, algunas o todas ellas en la aplicación. Como valor agregado, DAPR crea bloques integrados en los procedimientos recomendados del sector, incluida la observación completa.

En los próximos capítulos se proporciona una explicación detallada y ejemplos de código para cada bloque de creación de DAPR. En este momento, el inyector es aún más. Desde la nueva perspectiva, ahora tiene una visión más detallada de la capa de componentes de DAPR.

### <a name="components"></a>Componentes

Mientras que los bloques de creación exponen una API para invocar las capacidades de la aplicación distribuida, los componentes de DAPR proporcionan la implementación concreta para que se produzca.

Considere el componente de **almacén de estado** DAPR. Proporciona una manera uniforme de administrar el estado de las operaciones CRUD. Sin ningún cambio en el código del servicio, podría cambiar entre cualquiera de los siguientes componentes de estado de DAPR:

- AWS DynamoDB
- Aerospike
- Azure Blob Storage
- Azure CosmosDB
- Azure Table Storage
- Cassandra
- Cloud FireStore (modo de almacén de almacenamiento)
- CloudState
- Couchbase
- Etcd
- HashiCorp Consul
- Hazelcast
- Memcached
- MongoDB
- PostgreSQL
- Redis
- RethinkDB
- SQL Server
- Zookeeper

Cada componente proporciona la implementación necesaria a través de una interfaz de administración de Estado común:

```go
 type Store interface {
   Init(metadata Metadata) error
   Delete(req *DeleteRequest) error
   BulkDelete(req []DeleteRequest) error
   Get(req *GetRequest) (*GetResponse, error)
   Set(req *SetRequest) error
   BulkSet(req []SetRequest) error
}
```

> [!TIP]
> El tiempo de ejecución de DAPR así como todos los componentes de DAPR se han escrito en el lenguaje Golang o go. Go es un lenguaje popular en la comunidad de código abierto y se da fe del compromiso multiplataforma de DAPR.

Quizás empiece por Azure Redis Cache como almacén de estado. Especifíquelo con la siguiente configuración:

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Component
 metadata:
   name: statestore
   namespace: default
 spec:
   type: state.redis
   version: v1
   metadata:
   - name: redisHost
     value: <HOST>
   - name: redisPassword
     value: <PASSWORD>
   - name: enableTLS
     value: <bool> # Optional. Allowed: true, false.
   - name: failover
     value: <bool> # Optional. Allowed: true, false.
 ```

En la sección de **Especificaciones** , configure DAPR para usar el Redis cache para la administración de Estados. La sección también contiene metadatos específicos del componente. En este caso, puede usarlo para configurar opciones de Redis adicionales.

En un momento posterior, la aplicación está lista para ir a producción. En el entorno de producción, puede que desee cambiar la administración de estado a Azure Table Storage. Azure Table Storage ofrece funcionalidades de administración de estado que son asequibles y muy duraderas.

En el momento de redactar este documento, DAPR proporciona los siguientes tipos de componentes:

| Componente | Descripción |
|-----------|-------------|
| [Detección de servicios](https://github.com/dapr/components-contrib/tree/master/nameresolution) | Lo usa el bloque de creación de invocación de servicio para integrarse con el entorno de hospedaje para proporcionar la detección de servicio a servicio. |
| [State](https://github.com/dapr/components-contrib/tree/master/state) | Proporciona una interfaz uniforme para interactuar con una amplia variedad de implementaciones del almacén de estado. |
| [Pub/sub](https://github.com/dapr/components-contrib/tree/master/pubsub) | Proporciona una interfaz uniforme para interactuar con una amplia variedad de implementaciones del bus de mensajes. |
| [Enlaces](https://github.com/dapr/components-contrib/tree/master/bindings) | Proporciona una interfaz uniforme para desencadenar eventos de aplicación de sistemas externos e invocar sistemas externos con cargas de datos opcionales. |
| [Middleware](https://github.com/dapr/components-contrib/tree/master/middleware) | Permite que el middleware personalizado se conecte a la canalización de procesamiento de solicitudes e invoque acciones adicionales en una solicitud o respuesta. |
| [Almacenes secretos](https://github.com/dapr/components-contrib/tree/master/secretstores) | Proporciona una interfaz uniforme para interactuar con almacenes secretos externos, incluidos servicios de nube, perimetrales, comerciales y de código abierto. |
| [Exportadores de seguimiento](https://github.com/dapr/components-contrib/tree/master/exporters) | Proporciona una interfaz uniforme para abrir contenedores de telemetría. |

A medida que el chorro completa su marcha sobre DAPR, se vuelve a buscar una vez más y puede ver cómo se conecta a la vez.

### <a name="sidecar-architecture"></a>Arquitectura de sidecar

DAPR expone los componentes y los bloques de creación a través de una [arquitectura de sidecar](/azure/architecture/patterns/sidecar). Un sidecar permite que DAPR se ejecute en un proceso de memoria independiente o en un contenedor independiente junto con el servicio. Los sidecares proporcionan aislamiento y encapsulación, ya que no forman parte del servicio, pero se conectan a él. Esta separación permite que cada uno tenga su propio entorno en tiempo de ejecución y se compile en distintas plataformas de programación. En la figura 2-4 se muestra un patrón sidecar.

![Arquitectura de sidecar](./media/dapr-at-20000-feet/sidecar-generic.png)

**Figura 2-4**. Arquitectura sidecar.

Este patrón se denomina Sidecar porque parece un sidecar acoplado a una motocicleta. En la ilustración anterior, observe cómo se adjunta el sidecar de DAPR al servicio para proporcionar capacidades de aplicación distribuida.

### <a name="hosting-environments"></a>Entornos de hospedaje

DAPR tiene compatibilidad multiplataforma y se puede ejecutar en muchos entornos diferentes. Estos entornos incluyen Kubernetes, un grupo de máquinas virtuales o entornos perimetrales como Azure IoT Edge.

Para el desarrollo local, la manera más fácil de empezar es usar el [modo autohospedado](https://docs.dapr.io/concepts/overview/#self-hosted). En el modo autohospedado, los microservicios y los sidecares de DAPR se ejecutan en procesos locales independientes sin un orquestador de contenedores como Kubernetes. Para obtener más información, consulte [descarga e instalación de la CLI de DAPR](https://docs.dapr.io/getting-started/install-dapr/).

En la figura 2-5 se muestra una aplicación y DAPR hospedados en dos procesos de memoria independientes que se comunican mediante HTTP o gRPC.

![Arquitectura sidecar autohospedada](./media/dapr-at-20000-feet/self-hosted-dapr-sidecar.png)

**Figura 2-5**. Sidecar autohospedado DAPR.

De forma predeterminada, DAPR instala contenedores de Docker para Redis y Zipkin para proporcionar una administración de estado y observación predeterminadas. Si no quiere instalar Docker en el equipo local, puede incluso [Ejecutar DAPR en modo autohospedado sin ningún contenedor de Docker](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/). Sin embargo, debe instalar componentes predeterminados como Redis para la administración de Estados y pub/sub manualmente.

DAPR también se ejecuta en [entornos en contenedor](https://docs.dapr.io/concepts/overview/#kubernetes-hosted), como Kubernetes. En la figura 2-6 se muestra la ejecución de DAPR en un contenedor independiente de automóviles junto con el contenedor de la aplicación en el mismo pod de Kubernetes.

![Arquitectura de sidecar hospedada en Kubernetes](./media/dapr-at-20000-feet/kubernetes-hosted-dapr-sidecar.png)

**Figura 2-6**. Sidecar de Kubernetes hospedado en DAPR.

## <a name="dapr-performance-considerations"></a>Consideraciones de rendimiento de DAPR

Como ha visto, DAPR expone una arquitectura sidecar para desacoplar la aplicación de las funcionalidades de la aplicación distribuida. La invocación de una operación DAPR requiere al menos una llamada de red fuera de proceso. En la figura 2-7 se presenta un ejemplo de un patrón de tráfico de DAPR.

![Patrones de tráfico de DAPR](./media/dapr-at-20000-feet/dapr-traffic-patterns.png)

**Figura 2-7**. Patrones de tráfico de DAPR.

En la ilustración anterior, es posible que se produzca una pregunta sobre la latencia y la sobrecarga que se producen para cada llamada.  

El equipo de DAPR ha invertido en gran medida en el rendimiento. Una enorme cantidad de esfuerzo de Ingeniería ha ido a hacer que DAPR sea eficaz. Las llamadas entre DAPR sidecar siempre se realizan con gRPC, que ofrece alto rendimiento y cargas binarias pequeñas. En la mayoría de los casos, la sobrecarga adicional debe ser sub-milisegundo.

Para aumentar el rendimiento, los desarrolladores pueden llamar a los bloques de creación de DAPR con gRPC.

gRPC es un marco de trabajo moderno y de alto rendimiento que evoluciona el protocolo de [llamada a procedimiento remoto (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) de edad antiguo. gRPC usa HTTP/2 para su Protocolo de transporte, que proporciona mejoras de rendimiento significativas en el servicio RESTFul de HTTP, entre las que se incluyen:

- Compatibilidad con multiplexación para enviar varias solicitudes paralelas a través de la misma conexión: HTTP 1,1 limita el procesamiento a un mensaje de solicitud/respuesta a la vez.
- Comunicación dúplex completa bidireccional para enviar solicitudes de cliente y respuestas de servidor simultáneamente.
- Streaming integrado que habilita las solicitudes y respuestas para transmitir conjuntos de datos grandes de forma asincrónica.

## <a name="dapr-and-service-meshes"></a>DAPR y mallas de servicio

La malla de servicio es otra tecnología que evoluciona rápidamente para aplicaciones distribuidas.

Una malla de servicio es un nivel de infraestructura configurable con capacidades integradas para controlar la comunicación de servicio a servicio, la resistencia, el equilibrio de carga y la captura de telemetría. Traslada la responsabilidad de estos aspectos fuera de los servicios y a la capa de la malla de servicio. Al igual que DAPR, una malla de servicio también sigue una arquitectura de sidecar.

En la figura 2-8 se muestra una aplicación que implementa la tecnología de malla de servicio.

![Malla de servicio](./media/dapr-at-20000-feet/service-mesh-with-side-car.png)

**Figura 2-8**. Malla de servicio con un coche lateral.

En la ilustración anterior se muestra cómo interceptan los mensajes un proxy que se ejecuta junto con cada servicio. Cada proxy se puede configurar con reglas de tráfico específicas del servicio. Comprende los mensajes y los puede enrutar a través de los servicios y del mundo exterior.

Por lo tanto, la pregunta se convierte en "¿DAPR una malla de servicio?".

Aunque ambos usan una arquitectura de sidecar, cada tecnología tiene un propósito diferente. DAPR proporciona características de aplicaciones distribuidas. Una malla de servicio proporciona una capa de infraestructura de red dedicada.

Como cada uno de ellos funciona en un nivel diferente, ambos pueden funcionar juntos en la misma aplicación. Por ejemplo, una malla de servicio podría proporcionar comunicación de red entre los servicios. DAPR podría proporcionar servicios de aplicación como administración de estado o servicios de actor.

En la figura 2-9 se muestra una aplicación que implementa la tecnología de DAPR y de malla de servicio.

![DAPR y la malla de servicio juntas](./media/dapr-at-20000-feet/dapr-and-service-mesh.png)

**Figura 2-9**. DAPR y la malla de servicio juntas.

En el libro [Learning DAPR](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1), authors Haishi Bai y Yaron Schneider, se trata la integración de DAPR y la malla de servicio.

## <a name="summary"></a>Resumen

En este capítulo se ha presentado la DAPR, un tiempo de ejecución de una aplicación distribuida.

DAPR es un proyecto de código abierto patrocinado por Microsoft con estrecha colaboración de los clientes y de la comunidad de código abierto.

En esencia, DAPR ayuda a reducir la complejidad inherente de las aplicaciones de microservicios distribuidas. Se basa en un concepto de API de bloques de creación. Los bloques de creación de DAPR exponen funcionalidades comunes de aplicaciones distribuidas, como la administración de Estados, la invocación de servicio a servicio y la mensajería pub/sub. Los componentes de DAPR se encuentran por debajo de los bloques de creación y proporcionan la implementación concreta para cada funcionalidad. Las aplicaciones se enlazan a varios componentes a través de archivos de configuración.

En los capítulos siguientes, presentamos instrucciones prácticas sobre cómo usar DAPR en sus aplicaciones.

### <a name="references"></a>Referencias

- [Documentación de DAPR](https://dapr.io/)
- [Aprendizaje de DAPR](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1)
- [Microservicios de .NET: arquitectura para aplicaciones .NET en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)
- [Diseño de aplicaciones de Cloud-Native .NET para Azure](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)

> [!div class="step-by-step"]
> [Anterior](the-world-is-distributed.md)
> [Siguiente](getting-started.md)
