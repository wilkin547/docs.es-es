---
title: 'Enfoques de implementación de arquitectura: aplicaciones sin servidor'
description: Una guía para las distintas formas en que se implementan las arquitecturas empresariales en la nube, con comparación entre IaaS, PaaS, contenedores y sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8a1203ea2fc7089223c03b3a3e02fd3303610272
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577638"
---
# <a name="architecture-deployment-approaches"></a>Enfoques para la implementación de arquitecturas

Independientemente del enfoque de arquitectura utilizado para diseñar una aplicación empresarial, la implementación o la implementación de esas aplicaciones pueden variar. Las empresas hospedan aplicaciones en todo, desde hardware físico hasta funciones sin servidor.

## <a name="n-tier-applications"></a>Aplicaciones de N niveles

El [patrón de arquitectura de N niveles](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) es una arquitectura madura y simplemente hace referencia a las aplicaciones que separan diferentes capas lógicas en niveles físicos independientes. La arquitectura de n niveles es una implementación física de arquitectura de N capas. La implementación más común de esta arquitectura incluye:

* Un nivel de presentación, por ejemplo, una aplicación Web.
* Una API o un nivel de acceso a datos, como una API de REST.
* Una capa de datos, como una base de datos SQL.

![Arquitectura de N niveles](./media/n-tier-architecture.png)

Las soluciones de N niveles tienen las siguientes características:

* Los proyectos suelen estar alineados con los niveles.
* Las pruebas se pueden abordar de manera diferente según el nivel.
* Los niveles proporcionan capas de abstracción; por ejemplo, el nivel de presentación normalmente ignora los detalles de implementación de la capa de datos.
* Normalmente, las capas solo interactúan con capas adyacentes.
* Las versiones suelen administrarse en el proyecto y, por tanto, en el nivel. Un cambio de API simple puede requerir una nueva versión de todo el nivel intermedio.

Este enfoque proporciona varias ventajas, entre las que se incluyen:

* Aislamiento de la base de datos (a menudo, el front-end no tiene acceso directo al back-end de la base de datos).
* La reutilización de la API (por ejemplo, los clientes de aplicaciones Web, de escritorio y móviles pueden volver a usar las mismas API).
* Capacidad de escalar horizontalmente niveles independientes entre sí.
* Aislamiento de refactorización: un nivel puede refactorizarse sin afectar a otros niveles.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Local e infraestructura como servicio (IaaS)

El enfoque tradicional para el hospedaje de aplicaciones requiere la compra de hardware y la administración de todas las instalaciones de software, incluido el sistema operativo. Originalmente, esto implicaba centros de datos caros y hardware físico. Los desafíos que se incluyen en el hardware físico operativo son muchos, entre los que se incluyen:

* La necesidad de adquirir un exceso de escenarios de "Just-in-case" o de máxima demanda.
* Proteger el acceso físico al hardware.
* Responsabilidad del error de hardware (por ejemplo, un error de disco).
* Ventilación.
* Configuración de enrutadores y equilibradores de carga.
* Redundancia de energía.
* Protección del acceso a software.

![Enfoque de IaaS](./media/iaas-approach.png)

La virtualización de hardware, a través de "máquinas virtuales", permite la infraestructura como servicio (IaaS). Las máquinas host se particionan de manera eficaz para proporcionar recursos a instancias con asignaciones para su propia memoria, CPU y almacenamiento. El equipo aprovisiona las máquinas virtuales necesarias y configura las redes asociadas y el acceso al almacenamiento.

Para obtener más información, consulte [arquitectura de referencia de N niveles de máquina virtual](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Aunque la virtualización y la infraestructura como servicio (IaaS) abordan muchos problemas, todavía deja mucha responsabilidad en manos del equipo de infraestructura. El equipo mantiene las versiones del sistema operativo, aplica las revisiones de seguridad e instala las dependencias de terceros en los equipos de destino. Las aplicaciones suelen comportarse de forma diferente en los equipos de producción en comparación con el entorno de prueba. Surgen problemas debido a diferentes versiones de dependencia y/o niveles de SKU de sistema operativo. Aunque muchas organizaciones implementan aplicaciones de N niveles en estos destinos, muchas compañías se benefician de la implementación en un modelo nativo más en la nube, como la [plataforma como servicio](#platform-as-a-service-paas). Las arquitecturas con microservicios son más desafiantes debido a los requisitos de escalado horizontal para la elasticidad y resistencia.

Para obtener más información, consulte [máquinas virtuales](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Plataforma como servicio (PaaS)

Plataforma como servicio (PaaS) ofrece soluciones configuradas que los desarrolladores pueden conectar directamente. PaaS es otro término para el hospedaje administrado. Elimina la necesidad de administrar el sistema operativo base, las revisiones de seguridad y, en muchos casos, las dependencias de terceros. Entre los ejemplos de plataformas se incluyen las aplicaciones Web, las bases de datos y los back-ends móviles.

PaaS aborda los desafíos comunes a IaaS. PaaS permite al desarrollador centrarse en el código o el esquema de la base de datos en lugar de cómo se implementa. Entre las ventajas de PaaS se incluyen:

* Pague por los modelos de uso que eliminan la sobrecarga de invertir en máquinas inactivas.
* Implementación directa y mejoras de DevOps, integración continua (CI) y entrega continua (CD).
* Actualizaciones automáticas, actualizaciones y revisiones de seguridad.
* Escalado horizontal y escalado vertical (escala elástica) del botón de presión.

La principal desventaja de PaaS solía ser el bloqueo del proveedor. Por ejemplo, algunos proveedores de PaaS solo admiten ASP.NET, node. js u otros lenguajes y plataformas específicos. Productos como Azure App Service han evolucionado para abordar varias plataformas y admiten una variedad de lenguajes y marcos para hospedar aplicaciones Web.

![Arquitectura de plataforma como servicio](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software como servicio (SaaS)

El software como servicio o SaaS se hospeda de forma centralizada y está disponible sin necesidad de instalación o aprovisionamiento local. A menudo, SaaS se hospeda en PaaS como plataforma para la implementación de software. SaaS proporciona servicios para ejecutar y conectarse con software existente. SaaS suele ser específica del sector y vertical. SaaS suele tener licencia y normalmente proporciona un modelo cliente/servidor. La mayoría de las ofertas de SaaS modernas usan aplicaciones basadas en web para el cliente. Las empresas suelen considerar SaaS como una solución empresarial a las ofertas de licencias. A menudo no se implementa como consideración de arquitectura para la escalabilidad y el mantenimiento de una aplicación. En realidad, la mayoría de las soluciones de SaaS se basan en IaaS, PaaS o back-ends sin servidor.

Obtenga más información sobre SaaS a través de una [aplicación de ejemplo](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Contenedores y funciones como servicio (FaaS)

Los contenedores son una solución interesante que habilita las ventajas similares a PaaS sin la sobrecarga de IaaS. Un contenedor es esencialmente un entorno de tiempo de ejecución que contiene los elementos esenciales necesarios para ejecutar una aplicación única. El kernel o la parte principal del sistema operativo host y los servicios como el almacenamiento se comparten entre un host. El kernel compartido permite que los contenedores sean ligeros (algunos son de mero megabytes de tamaño, en comparación con el tamaño de Gigabyte de las máquinas virtuales típicas). Con los hosts que ya se están ejecutando, los contenedores se pueden iniciar rápidamente, lo que facilita la alta disponibilidad. La capacidad de poner en marcha los contenedores rápidamente también proporciona capas adicionales de resistencia. Docker es una de las implementaciones más populares de contenedores.

Las ventajas de los contenedores incluyen:

* Ligeros y portátiles
* Independiente, por lo que no es necesario instalar dependencias
* Proporcionar un entorno coherente independientemente del host (se ejecuta exactamente igual en un equipo portátil que en un servidor en la nube)
* Se puede aprovisionar rápidamente para el escalado horizontal
* Se puede reiniciar rápidamente para recuperarse de un error

Un contenedor se ejecuta en un host de contenedor (que, a su vez, se puede ejecutar en un equipo sin sistema operativo o en una máquina virtual). Se pueden ejecutar varios contenedores o instancias de los mismos contenedores en un solo host. En el caso de una conmutación por error y resistencia verdaderas, los contenedores se deben escalar entre los hosts.

Para más información sobre los contenedores de Docker, consulte [¿Qué es Docker](../microservices/container-docker-introduction/docker-defined.md)?

La administración de contenedores en hosts normalmente requiere una herramienta de orquestación como Kubernetes. La configuración y administración de soluciones de orquestación puede Agregar sobrecarga y complejidad adicionales a los proyectos. Afortunadamente, muchos proveedores de nube proporcionan servicios de orquestación a través de soluciones PaaS para simplificar la administración de contenedores.

En la imagen siguiente se muestra una instalación de Kubernetes de ejemplo. Los nodos de la dirección de instalación se escalan horizontalmente y la conmutación por error. Ejecutan instancias de contenedor de Docker administradas por el servidor maestro. *Kubelet* es el cliente que retransmite comandos de Kubernetes a Docker.

![kubernetes](./media/kubernetes-example.png)

Para obtener más información acerca de la orquestación, consulte [Kubernetes en Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Funciones como servicio (FaaS) es un servicio de contenedor especializado similar a sin servidor. Una implementación específica de FaaS, denominada [OpenFaaS](https://github.com/openfaas/faas), se basa en contenedores para proporcionar funcionalidades sin servidor. OpenFaaS proporciona plantillas que empaquetan todas las dependencias de contenedor necesarias para ejecutar un fragmento de código. El uso de plantillas simplifica el proceso de implementación de código como una unidad funcional. OpenFaaS tiene como destino arquitecturas que ya incluyen contenedores y orquestadores, ya que puede usar la infraestructura existente. Aunque proporciona funcionalidad sin servidor, requiere específicamente el uso de Docker y un orquestador.

## <a name="serverless"></a>Sin servidor

Una arquitectura sin servidor proporciona una separación clara entre el código y su entorno de hospedaje. El código se implementa en una *función* invocada por un *desencadenador*. Una vez finalizada la función, es posible que se liberen todos los recursos necesarios. El desencadenador puede ser manual, un proceso con tiempo, una solicitud HTTP o una carga de archivos. El resultado del desencadenador es la ejecución del código. Aunque las plataformas sin servidor varían, la mayoría proporciona acceso a las API y enlaces predefinidos para simplificar tareas como la escritura en una base de datos o la puesta en cola de los resultados.

Sin servidor es una arquitectura que se basa en gran medida en abstraer el entorno de host para centrarse en el código. Puede considerarse como un *servidor menos*.

Las soluciones de contenedor proporcionan a los desarrolladores scripts de compilación existentes para publicar código en imágenes listas para usar sin servidor. Otras implementaciones usan soluciones PaaS existentes para proporcionar una arquitectura escalable.

La abstracción significa que el equipo de DevOps no tiene que aprovisionar o administrar servidores, ni contenedores específicos. La plataforma sin servidor hospeda código, como archivos ejecutables empaquetados o de script compilados con un SDK relacionado, y asigna los recursos necesarios para que el código se escale.

En la ilustración siguiente se diagraman cuatro componentes sin servidor. Una solicitud HTTP hace que se ejecute el código de la API de desprotección. La API de desprotección inserta código en una base de datos, y la instrucción INSERT desencadena otras funciones que se ejecutan para realizar tareas como la realización de tareas y el cumplimiento del orden.

![Implementación sin servidor](./media/serverless-implementation.png)

Entre las ventajas de sin servidor se incluyen:

* **Alta densidad.** Muchas instancias del mismo código sin servidor se pueden ejecutar en el mismo host en comparación con los contenedores o las máquinas virtuales. Las instancias se escalan en varios hosts de escalabilidad horizontal y resistencia.
* **Micro-facturación**. La mayoría de los proveedores sin servidor facturan en función de las ejecuciones sin servidor, lo que permite ahorrar costos masivos en ciertos escenarios.
* **Escalado instantáneo**. Sin servidor se puede escalar para que coincidan con las cargas de trabajo de forma automática y rápida.
* **Tiempo de comercialización más rápido** Los desarrolladores se centran en el código y se implementan directamente en la plataforma sin servidor. Los componentes se pueden liberar independientemente entre sí.

Sin servidor se suele describir en el contexto de compute, pero también se puede aplicar a los datos. Por ejemplo, [Azure SQL](https://docs.microsoft.com/azure/sql-database) y [Cosmos dB](https://docs.microsoft.com/azure/cosmos-db) proporcionan bases de datos en la nube que no requieren la configuración de clústeres o máquinas host. Este libro se centra en el proceso sin servidor.

## <a name="summary"></a>Resumen

Hay una amplia gama de opciones disponibles para la arquitectura, incluido un enfoque híbrido. Sin servidor simplifica el enfoque, la administración y el costo de las características de la aplicación a costa del control y la portabilidad. Sin embargo, muchas plataformas sin servidor exponen la configuración para ayudar a ajustar la solución. Una buena práctica de programación también puede conducir a un código más portátil y un bloqueo de plataforma sin servidor. En la tabla siguiente se muestran los enfoques de la arquitectura en paralelo. Elija sin servidor en función de las necesidades de escalado, independientemente de si desea administrar el tiempo de ejecución, y cómo puede dividir las cargas de trabajo en componentes pequeños. En el siguiente capítulo obtendrá información sobre posibles desafíos con sin servidor y otros puntos de decisión.

|         |IaaS     |PaaS     |Contenedor|Sin servidor|
|---------|---------|---------|---------|----------|
|**Escalar**|MEDIO       |Instancia |Aplicación      |Función  |
|**Abstrae**|Hardware|Plataforma|Host de SO|Tiempo de ejecución   |
|**Unidad** |MEDIO       |Proyecto  |Image    |Código      |
|**Duración**|Partir|Días a meses|Minutos a días|Milisegundos hasta minutos|
|**Resp**|Aplicaciones, dependencias, tiempo de ejecución y sistema operativo|Aplicaciones y dependencias|Aplicaciones, dependencias y tiempo de ejecución|Función

* La **escala** hace referencia a la unidad que se usa para escalar la aplicación
* Los **resúmenes** hacen referencia a la capa que la implementación abstrae.
* La **unidad** hace referencia al ámbito de lo que se implementa
* La **duración** hace referencia al tiempo de ejecución típico de una instancia específica
* La **responsabilidad** se refiere a la sobrecarga para compilar, implementar y mantener la aplicación

El siguiente capítulo se centrará en la arquitectura sin servidor, en los casos de uso y en los patrones de diseño.

## <a name="recommended-resources"></a>Recursos recomendados

* [Guía de arquitectura de aplicaciones de Azure](https://docs.microsoft.com/azure/architecture/guide/)
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
* [SQL de Azure](https://docs.microsoft.com/azure/sql-database)
* [Patrón de arquitectura de N niveles](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [Kubernetes en Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [Microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [Arquitectura de referencia de N niveles de máquina virtual](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [Máquinas virtuales](https://docs.microsoft.com/azure/virtual-machines/)
* [¿Qué es Docker?](../microservices/container-docker-introduction/docker-defined.md)
* [Aplicación SaaS de Wingtip tickets](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Anterior](architecture-approaches.md)
>[Siguiente](serverless-architecture.md)
