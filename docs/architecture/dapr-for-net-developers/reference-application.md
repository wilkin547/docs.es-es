---
title: Introducción a la aplicación de referencia eShopOnDapr
description: Información general de la aplicación de referencia de eShopOnDapr y su historial.
author: amolenk
ms.date: 02/17/2021
ms.openlocfilehash: 8fd0ccade45f4f6609046e00d22ffd5693c4a529
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623894"
---
# <a name="dapr-reference-application"></a>Aplicación de referencia DAPR

Anteriormente en el libro, ha aprendido sobre las ventajas fundamentales de DAPR. Vio cómo DAPR puede ayudar a su equipo a construir aplicaciones distribuidas a la vez que reduce la complejidad de la arquitectura y las operaciones. A lo largo del proceso, ha tenido la oportunidad de crear algunas pequeñas aplicaciones de DAPR. Ahora es el momento de explorar una aplicación de microservicios de un extremo a otro que muestra los componentes y los bloques de creación de DAPR.

Pero, en primer lugar, un pequeño historial.

## <a name="eshop-on-containers"></a>eShop en contenedores

Hace varios años, Microsoft, en colaboración con expertos en la comunidad líderes, lanzó un libro de orientación conocido, titulado [microservicios de .net para aplicaciones .net en contenedor](https://dotnet.microsoft.com/download/e-book/microservices-architecture/pdf). En la figura 3-1 se muestra el libro:

![Diseño de aplicaciones .NET de microservicios en contenedores.](./media/reference-application/architecting-microservices-book.png)

**Figura 3-1**. Microservicios de .NET: arquitectura para aplicaciones .NET en contenedor.

El libro Dove en profundidad los principios, patrones y procedimientos recomendados para la creación de aplicaciones distribuidas. Incluye una aplicación de referencia de microservicios con todas las características que presentaba los conceptos arquitectónicos. Con derecho, [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers), la aplicación muestra un escaparate de comercio electrónico que vende distintos elementos de .net, como ropa y tazas de café.  Basado en .NET Core, la aplicación es multiplataforma y se puede ejecutar en contenedores de Linux o Windows. En la figura 3-2 se muestra la arquitectura de eShop original.

![arquitectura de la aplicación de referencia eShopOnContainers.](./media/reference-application/eshop-on-containers.png)

**Figura 3-2**. `ShopOnContainers`Aplicación de referencia original.

Como puede ver, eShopOnContainers incluye muchas partes móviles:

1. Tres clientes front-end diferentes.
1. Una puerta de enlace de aplicaciones para abstraer el back-end del front-end.
1. Varios microservicios principales de back-end.
1. Un componente de bus de eventos que habilita la mensajería asincrónica de pub/sub.

La aplicación de referencia eShopOnContainers se ha aceptado ampliamente en toda la comunidad de .NET y se ha usado para modelar muchas aplicaciones de microservicios comerciales de gran tamaño.

## <a name="eshop-on-dapr"></a>eShop en DAPR

Una versión alternativa de la aplicación de eShop acompaña a este libro. Se denomina [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr). La versión actualizada evoluciona la aplicación eShopOnContainers anterior mediante la integración de los componentes y los bloques de creación de DAPR. En la figura 3-3 se muestra la nueva arquitectura de solución simplificada:  

![arquitectura de la aplicación de referencia eShopOnDapr.](./media/reference-application/eshop-on-dapr.png)

**Figura 3-3**. arquitectura de la aplicación de referencia eShopOnDapr.

Como el enfoque de la aplicación de referencia eShopOnDapr está en DAPR, se ha actualizado la aplicación original. La arquitectura consta de:

1. Un front-end de aplicación de una [sola página](/archive/msdn-magazine/2013/november/asp-net-single-page-applications-build-modern-responsive-web-apps-with-asp-net) escrito en el conocido marco de spa de angular. Envía solicitudes de usuario a un microservicio de puerta de enlace de API.

1. La puerta de enlace de API abstrae los microservicios principales de back-end del cliente front-end. Se implementa mediante el [envío](https://www.envoyproxy.io/), un proxy de servicio de código abierto de alto rendimiento. El envío enruta las solicitudes entrantes a varios microservicios de back-end. La mayoría de las solicitudes son operaciones CRUD simples (por ejemplo, obtienen la lista de marcas del catálogo) y se controlan mediante una llamada directa a un microservicio de back-end.

1. Otras solicitudes son lógicamente más complejas y requieren que varios microservicios funcionen juntos. En estos casos, eShopOnDapr implementa un [microservicio de agregador](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) que organiza un flujo de trabajo a través de los microservicios necesarios para completar la operación.

1. El conjunto de microservicios principales de back-end incluye la funcionalidad necesaria para un almacén de comercio electrónico. Cada es independiente e independiente de los demás. A continuación de los patrones de descomposición de dominios ampliamente aceptados, cada microservicio aísla una *funcionalidad empresarial* específica:

   - El servicio de la cesta administra la experiencia de la cesta de la compra del cliente.
   - El servicio de catálogo administra los elementos de productos disponibles para la venta.
   - El servicio de identidad administra la autenticación y la identidad.
   - El servicio de ordenación controla todos los aspectos de colocación y administración de pedidos.
   - El servicio de pago reacciona el pago del cliente.

   Cada servicio tiene su propio almacenamiento persistente. Al cumplir los [procedimientos recomendados](../cloud-native/distributed-data.md#database-per-microservice-why)de microservicios, no hay ningún almacén de recursos compartido con el que interactúen todos los servicios.

   El diseño de cada microservicio se basa en sus requisitos individuales. Los servicios simples usan las operaciones CRUD básicas para tener acceso a sus almacenes de datos subyacentes. Advanced Services, como la ordenación, utilizan un enfoque de diseño Domain-Driven para administrar la complejidad empresarial. Si es necesario, los servicios se pueden crear a través de diferentes pilas de tecnología, como .NET Core, Java, Go, NodeJS, etc.

1. Por último, el bus de eventos encapsula los componentes de publicación/suscripción de DAPR. Permite la mensajería asincrónica de publicación/suscripción a través de microservicios. Los desarrolladores pueden conectar cualquier agente de mensajes compatible con DAPR.

### <a name="application-of-dapr-building-blocks"></a>Aplicación de los bloques de creación de DAPR

El código base eShopOnDapr es más optimizado que el código base eShopOnContainers. Los bloques de creación de DAPR reemplazan una gran cantidad de código de Fontane propenso a errores.

En la figura 3-4 se muestra la integración de DAPR en la aplicación de referencia de eShop.

![arquitectura de la aplicación de referencia eShopOnDapr](./media/reference-application/eshop-on-dapr-buildingblocks.png)

**Figura 3-4**. Integración de DAPR en eShopOnDapr.

En la ilustración anterior, puede ver qué servicios usan los bloques de creación de DAPR.

1. La aplicación eShopOnContainers original muestra los conceptos y patrones de DDD en el servicio de pedidos. En el eShopOnDapr actualizado, el servicio de pedidos utiliza el *bloque de creación del actor* como una implementación alternativa. El modelo de acceso basado en turnos de los actores facilita la implementación de un proceso de ordenación con estado con compatibilidad para la cancelación.
1. El servicio de pedidos envía correos electrónicos de confirmación de pedido mediante el [bloque de creación de enlaces](bindings.md).
1. Los servicios back-end se comunican de forma asincrónica mediante el [bloque de creación de publicación & suscripción](publish-subscribe.md).
1. La administración de secretos se realiza mediante el [bloque de creación de secretos](secrets.md).
1. La puerta de enlace de API y los servicios del agregador de web Shopping usan el [bloque de creación de invocación de servicio](service-invocation.md) para invocar métodos en los servicios back-end.
1. El servicio de cesta utiliza el [bloque de creación de administración de estado](state-management.md) para almacenar el estado de la cesta de la compra del cliente.

### <a name="benefits-of-applying-dapr-to-eshop"></a>Ventajas de aplicar DAPR a eShop

En general, el uso de los bloques de creación de DAPR agrega posibilidades de observación y flexibilidad a la aplicación:

1. Observación: mediante el uso de los bloques de creación de DAPR, se obtiene un seguimiento distribuido enriquecido para ambas llamadas entre los servicios y los componentes de DAPR sin tener que escribir ningún código. En eShopOnContainers, se usa una gran cantidad de registro personalizado para proporcionar información.
1. Flexibilidad: ahora puede *intercambiar* la infraestructura cambiando simplemente un archivo de configuración de componentes. No es necesario realizar ningún cambio en el código.

Estos son algunos ejemplos de las ventajas que ofrecen los bloques de creación específicos:

- **Invocación de servicio**
  - Gracias a la compatibilidad de DAPR con [mTLS](https://blog.cloudflare.com/introducing-tls-client-auth/), los servicios se comunican ahora a través de canales cifrados.
  - Cuando se producen errores transitorios, se reintentan automáticamente las llamadas de servicio.
  - La detección automática de servicios reduce la cantidad de configuración necesaria para que los servicios se encuentren entre sí.

- **Publicar/suscribir**
  - eShopOnContainer incluía una gran cantidad de código personalizado para admitir Azure Service Bus y RabbitMQ. Los desarrolladores usaban Azure Service Bus para producción y RabbitMQ para el desarrollo y las pruebas locales. `IEventBus`Se creó una capa de abstracción para permitir el intercambio entre estos agentes de mensajes. Este nivel consta de aproximadamente *700 líneas de código propenso a errores*. La implementación actualizada con DAPR requiere solo *35 líneas de código*. Este es el **5%** de las líneas de código originales. Lo que es más importante, la implementación es sencilla y fácil de comprender.
  - eShopOnDapr usa la integración enriquecida ASP.NET Core de DAPR para usar pub/sub. Agregue `Topic` atributos a métodos de controlador de ASP.net Core para suscribirse a los mensajes. Por lo tanto, no es necesario escribir un bucle de controlador de mensajes independiente para cada agente de mensajes.
  - Los mensajes enrutados al servicio como llamadas HTTP permiten el uso de ASP.NET Core middleware para agregar funcionalidad, sin introducir nuevos conceptos o SDK para aprender.

- **Enlaces**
  - La solución eShopOnContainers contenía un elemento de *tareas pendientes* para enviar por correo electrónico una confirmación de pedido al cliente. El pensamiento era implementar una API de correo electrónico de terceros como SendGrid. Con DAPR, la implementación de notificaciones por correo electrónico era tan fácil como configurar un enlace de recursos. No hubo necesidad de aprender API o SDK externos.

> [!NOTE]
> El bloque de creación de actores no se trata en la primera versión de este libro. En la actualización 1,1 se incluirá un amplio capítulo sobre el bloque de creación del actor y su integración con eShopOnDapr.

## <a name="summary"></a>Resumen

En este capítulo, se le presentará la aplicación de referencia eShopOnDapr. Es una evolución de la popular aplicación de referencia de microservicios de eShopOnContainers. eShopOnDapr reemplaza una gran cantidad de funcionalidad personalizada con los componentes y los bloques de creación de DAPR, lo que simplifica drásticamente las complejidades necesarias para compilar una aplicación de microservicios.

### <a name="references"></a>Referencias

- [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)

- [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)

- [Microservicios de .NET para aplicaciones .NET en contenedor](https://dotnet.microsoft.com/download/e-book/microservices-architecture/pdf)

- [Diseño de aplicaciones de Cloud-Native .NET para Azure](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)

> [!div class="step-by-step"]
> [Anterior](getting-started.md)
> [Siguiente](state-management.md)
