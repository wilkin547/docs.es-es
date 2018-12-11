---
title: Métodos de implementación de arquitectura - aplicaciones sin servidor
description: Una guía para arquitecturas de empresa de maneras diferentes están implementados en la nube, con la comparación entre IaaS, PaaS, contenedores y sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5477b8c4531780fdebf194e4f798564e59cd2953
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152674"
---
# <a name="architecture-deployment-approaches"></a>Métodos de implementación de arquitectura

Independientemente de la arquitectura puede variar el enfoque empleado para diseñar una aplicación empresarial, la implementación o la implementación de esas aplicaciones. Las empresas a hospedan aplicaciones en todo, desde el hardware físico a las funciones sin servidor.

## <a name="n-tier-applications"></a>aplicaciones de n niveles

El [patrón de arquitectura de N niveles](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) es una arquitectura madura y simplemente se refiere a las aplicaciones que separan los diferentes niveles lógicos en los niveles físicos independientes. Arquitectura de N niveles es una implementación física de la arquitectura de N capas. La implementación más común de esta arquitectura incluye:

* Un nivel de presentación, por ejemplo una aplicación web.
* Una API o datos de nivel de acceso, como una API de REST.
* Una capa de datos, como una base de datos SQL.

![Arquitectura de N niveles](./media/n-tier-architecture.png)

Soluciones de N niveles tienen las siguientes características:

* Normalmente se alinean los proyectos con niveles.
* Las pruebas pueden llevarse a cabo diferente por nivel.
* Niveles proporcionan niveles de abstracción, por ejemplo el nivel de presentación es normalmente que ignoran la persistencia de los detalles de implementación de la capa de datos.
* Normalmente, las capas solo interactúan capas adyacentes.
* Las versiones a menudo se administran en el proyecto y, por tanto, nivel, el nivel. Un simple cambio de API puede requerir una nueva versión de un nivel intermedio todo.

Este enfoque ofrece varias ventajas, incluyendo:

* Aislamiento de la base de datos (a menudo el front-end no tiene acceso directo al back-end de la base de datos).
* La reutilización de la API (por ejemplo, escritorio, móviles y clientes de la aplicación web, se pueden reutilizar las mismas API).
* Capacidad de escalar horizontalmente capas independientes entre sí.
* Aislamiento de refactorización: es posible que se va a refactorizar un solo nivel sin afectar a otros niveles.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>En el entorno local y la infraestructura como servicio (IaaS)

El enfoque tradicional para hospedar aplicaciones requiere comprar hardware y administrar todas las instalaciones de software, incluido el sistema operativo. Originalmente, esto implicaba centros de datos costosas y hardware físico. Los desafíos que vienen con la operación de hardware físico son numerosas, incluidos:

* La necesidad de comprar un exceso de "si acaso" o máxima de los escenarios a petición.
* Protección del acceso físico al hardware.
* Responsabilidad de un error de hardware (por ejemplo, error de disco).
* Refrigeración.
* Configuración de enrutadores y equilibradores de carga.
* Redundancia de alimentación.
* Protección del acceso de software.

![Enfoque de IaaS](./media/iaas-approach.png)

Virtualización de hardware, a través de "máquinas virtuales" permite la infraestructura como servicio (IaaS). Las máquinas host eficazmente tienen particiones para proporcionar recursos a las instancias con las asignaciones para su propia memoria, CPU y almacenamiento. El equipo aprovisiona las máquinas virtuales necesarias y configura las redes asociadas y el acceso al almacenamiento.

Para obtener más información, consulte [máquina virtual de arquitectura de referencia de N niveles](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Aunque la virtualización y la infraestructura como servicio (IaaS) solucionar muchos problemas, le deja mucho responsabilidad en manos del equipo de infraestructura. El equipo mantiene versiones de sistema operativo, aplica a las revisiones de seguridad e instala las dependencias de terceros en los equipos de destino. Las aplicaciones a menudo comportan de manera diferente en los equipos de producción en comparación con el entorno de prueba. Surgen problemas debido a las versiones de dependencias diferentes o niveles de SKU del sistema operativo. Aunque muchas organizaciones implementan aplicaciones de N niveles en estos destinos, muchas empresas beneficiarán de la implementación en un modelo nativo en la nube más como [plataforma como servicio](#platform-as-a-service-paas). Arquitecturas de microservicios son más difíciles debido a los requisitos de escalabilidad horizontal para la elasticidad y la resistencia.

Para obtener más información, consulte [máquinas virtuales](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Plataforma como servicio (PaaS)

Plataforma como servicio (PaaS) ofrece configura soluciones que los desarrolladores pueden conectar directamente en. PaaS es otro término para hospedaje administrado. Elimina la necesidad de administrar el sistema operativo base, revisiones de seguridad y en muchos casos, las dependencias de terceros. Ejemplos de las plataformas, aplicaciones web, bases de datos, y el back-end móviles.

PaaS aborda los desafíos comunes a IaaS. PaaS permite al desarrollador centrarse en el esquema de base de datos o código en lugar de cómo se obtiene implementado. Ventajas de PaaS incluyen:

* Pague por usar modelos que eliminan la sobrecarga de invertir en máquinas inactivas.
* Dirigir la implementación y DevOps mejorado, integración continua (CI) y las canalizaciones de entrega continua (CD).
* Las actualizaciones automáticas, actualizaciones y revisiones de seguridad.
* Botón de comando escalado horizontal y escalado vertical (escala elástica).

La principal desventaja de PaaS tradicionalmente ha sido bloqueo del proveedor. Por ejemplo, algunos proveedores de PaaS solo admiten ASP.NET, Node.js, u otros idiomas específicos y plataformas. Productos como Azure App Service han evolucionado para abordar varias plataformas y admite una variedad de lenguajes y marcos de trabajo para hospedar aplicaciones web.

![Plataforma como una arquitectura de servicio](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software como servicio (SaaS)

Software como servicio o SaaS está centralmente hospedado y disponible sin ninguna instalación local o aprovisionamiento. SaaS se hospeda en PaaS a menudo como una plataforma para la implementación de software. SaaS proporciona servicios para ejecutar y conectarse con el software existente. SaaS es a menudo vertical específico y del sector. SaaS es a menudo la licencia y normalmente proporciona un modelo cliente/servidor. Ofertas de SaaS más modernas usar aplicaciones basadas en web para el cliente. Las empresas suelen considere la posibilidad de SaaS como una solución empresarial para ofertas de licencias. A menudo no se implementan como consideración de arquitectura para escalabilidad y facilidad de mantenimiento de una aplicación. De hecho, la mayoría de las soluciones de SaaS se basa en IaaS, PaaS o sin servidor back-end.

Obtener más información acerca de SaaS a través de un [aplicación de ejemplo](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Los contenedores y las funciones como servicio (FaaS)

Los contenedores son una solución interesante que permite a las ventajas de PaaS como sin la sobrecarga de IaaS. Un contenedor es básicamente un tiempo de ejecución que contiene las funciones esenciales necesarias para ejecutar una aplicación única. La parte del núcleo o core del sistema operativo host y servicios, como el almacenamiento se comparten entre un host. El núcleo compartido permite que los contenedores sean ligeros (algunos son mero megabytes de tamaño, en comparación con el tamaño de gigabyte de típico de las máquinas virtuales). Con los hosts que ya está ejecutando, los contenedores pueden iniciarse rápidamente, facilita la alta disponibilidad. La capacidad de poner en marcha rápidamente los contenedores también proporciona capas adicionales de resistencia. Docker es una de las implementaciones de contenedores más populares.

Ventajas de los contenedores incluyen:

* Ligero y portátil
* Independientes por lo que no es necesario instalar las dependencias
* Proporcionar un entorno coherente con independencia del host (se ejecuta exactamente el mismo en un equipo portátil como en un servidor en la nube)
* Se pueden aprovisionar rápidamente para escalar horizontalmente
* Se puede reiniciar rápidamente para recuperarse de errores

Un contenedor se ejecuta en un host de contenedor (que a su vez puede ejecutar en una máquina sin sistema operativo o una máquina virtual). Pueden ejecutar varios contenedores o las instancias de los mismos contenedores en un solo host. Para true conmutación por error y la resistencia, se deben escalar contenedores a través de hosts.

Para obtener más información acerca de los contenedores de Docker, consulte [¿qué es Docker](../microservices-architecture/container-docker-introduction/docker-defined.md)?

Administración de contenedores a través de hosts normalmente requiere una herramienta de orquestación como Kubernetes. Configurar y administrar soluciones de orquestación pueden agregar una sobrecarga adicional y la complejidad a proyectos. Afortunadamente, muchos proveedores de nube proporcionan servicios de orquestación a través de las soluciones de PaaS para simplificar la administración de contenedores.

La siguiente imagen muestra un ejemplo de instalación de Kubernetes. La dirección para los nodos en la instalación de escalado horizontal y conmutación por error. Docker se ejecutan de instancias de contenedor que se administran mediante el servidor maestro. El *kubelet* es el cliente que retransmite los comandos de Kubernetes para Docker.

![Kubernetes](./media/kubernetes-example.png)

Para obtener más información acerca de la orquestación, consulte [Kubernetes en Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Funciones como servicio (FaaS) es un servicio de contenedor especializado que es similar a sin servidor. Una implementación específica de FaaS, llamado [OpenFaaS](https://github.com/openfaas/faas), se ubica sobre contenedores para proporcionar funcionalidades sin servidor. OpenFaaS proporciona plantillas que todas las dependencias de contenedor necesarias para ejecutar un fragmento de código del paquete. Uso de plantillas simplifica el proceso de implementación de código como una unidad funcional. OpenFaaS tiene como destino arquitecturas que ya incluyen los contenedores y los orquestadores puesto que puede utilizar la infraestructura existente. Aunque proporciona funcionalidad sin servidor, específicamente, deberá usar Docker y un orquestador.

## <a name="serverless"></a>Sin servidor

Una arquitectura sin servidor proporciona una separación clara entre el código y su entorno de hospedaje. Implementar código en un *función* que invoca un *desencadenador*. Después de que salga de esa función, se pueden liberar todos los recursos necesarios. El desencadenador podría ser una carga de archivos, una solicitud HTTP, un proceso programado o manual. El resultado del desencadenador es la ejecución de código. Aunque las plataformas sin servidor varían, más proporcionan acceso a las API y los enlaces predefinidos para simplificar tareas como escribir en los resultados de una base de datos o puesta en cola.

Sin servidor es una arquitectura que se basa principalmente en abstraer el entorno de host para centrarse en el código. Se puede considerar como *menos server*.

Soluciones de contenedor proporcionan existentes de los desarrolladores crear scripts para publicar código en las imágenes sin servidor listo. Otras implementaciones utilizan soluciones de PaaS existentes para proporcionar una arquitectura escalable.

La abstracción significa que el equipo de DevOps no tiene que aprovisionar ni administrar servidores, ni tampoco determinados contenedores. El código de hosts de plataforma sin servidor, como scripts o ejecutables empaquetados creadas con un SDK relacionado y asigna los recursos necesarios escalar el código.

La siguiente ilustración muestra cuatro componentes sin servidor. Hace que una solicitud HTTP para ejecutar el código de la API de desprotección. La API de desprotección se inserta código en una base de datos, y muchas otras funciones para ejecutar para realizar tareas como tareas informáticas y realizar el pedido desencadena la inserción.

![Implementación sin servidor](./media/serverless-implementation.png)

Las ventajas de sin servidor incluyen:

* **Alta densidad.** Pueden ejecutar varias instancias del mismo código sin servidor en el mismo host en comparación con los contenedores o máquinas virtuales. La escala de las instancias en varios escalada de hosts y resistencia.
* **Facturación de Micro**. Lista de proveedores sin servidor más según las ejecuciones sin servidor, habilitar grandes ahorros en determinados escenarios.
* **Escala instantánea**. Puede escalar sin servidor para que coincida con las cargas de trabajo de forma rápida y automática.
* **Un tiempo más rápido al mercado** a los desarrolladores centrarse en el código e implementar directamente a la plataforma sin servidor. Los componentes pueden liberarse por separado.

Sin servidor se analiza con más frecuencia en el contexto de proceso, pero también puede aplicar a los datos. Por ejemplo, [SQL Azure](https://docs.microsoft.com/azure/sql-database) y [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) ofrecen las bases de datos en la nube que no requieren configurar equipos host o clústeres. Este libro se centra en el proceso sin servidor.

## <a name="summary"></a>Resumen

Hay una amplia gama de opciones disponibles para la arquitectura, incluidos un enfoque híbrido. Sin servidor simplifica el enfoque, la administración y el costo de características de la aplicación a costa de control y portabilidad. Sin embargo, muchas plataformas sin servidor exponer la configuración para ayudar a ajustar la solución. También pueden provocar buenas prácticas de programación a código más portable y menos en el bloqueo de plataforma sin servidor. La siguiente tabla muestra los enfoques de arquitectura en paralelo. Elija sin servidor en función de la escala de las necesidades, o si no desea administrar el tiempo de ejecución y también cómo puede interrumpir las cargas de trabajo en componentes pequeños. Conocerá los desafíos potenciales con sin servidor y otros puntos de decisión en el capítulo siguiente.

|         |IaaS     |PaaS     |Contenedor|Sin servidor|
|---------|---------|---------|---------|----------|
|**Escalar**|MÁQUINA VIRTUAL       |Instancia |Aplicación      |Función  |
|**Abstrae**|Hardware|Plataforma|Sistema operativo Host|Tiempo de ejecución   |
|**Unidad** |MÁQUINA VIRTUAL       |Proyecto  |Imagen    |Código      |
|**Duración**|meses|Días o meses|Minutos en días|Milisegundos en minutos|
|**responsabilidad**|Las aplicaciones, las dependencias, en tiempo de ejecución y del sistema operativo|Las aplicaciones y dependencias|En tiempo de ejecución, dependencias y las aplicaciones|Función

* **Escala** hace referencia a la unidad que se usa para escalar la aplicación
* **Abstrae** hace referencia a la capa que abstrae la implementación
* **Unidad** hace referencia al ámbito de lo que se implementa
* **Duración** se refiere al tiempo de ejecución típico de una instancia específica
* **Responsabilidad** hace referencia a la sobrecarga que supone compilar, implementar y mantener la aplicación

El siguiente capítulo centrarse en la arquitectura sin servidor, casos de uso y patrones de diseño.

## <a name="recommended-resources"></a>Recursos recomendados

* [Guía de arquitectura de aplicación de Azure](https://docs.microsoft.com/azure/architecture/guide/)
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
* [SQL Azure](https://docs.microsoft.com/azure/sql-database)
* [Patrón de arquitectura de N niveles](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [Kubernetes en Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [Microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [Arquitectura de referencia de N niveles de máquina virtual](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [Máquinas virtuales](https://docs.microsoft.com/azure/virtual-machines/)
* [¿Qué es Docker?](../microservices-architecture/container-docker-introduction/docker-defined.md)
* [Aplicación de SaaS de vales de Wingtip](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Anterior](architecture-approaches.md)
>[Siguiente](serverless-architecture.md)