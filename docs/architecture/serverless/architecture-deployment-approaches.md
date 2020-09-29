---
title: 'Enfoques de implementación de arquitectura: aplicaciones sin servidor'
description: Una guía para las distintas formas en que se implementan las arquitecturas empresariales en la nube, con una comparación entre IaaS, PaaS, contenedores y aplicaciones sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7e91412600e8e4e5a0dca2a454f1cb0680c881b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173346"
---
# <a name="architecture-deployment-approaches"></a>Enfoques para la implementación de arquitecturas

Independientemente del enfoque de arquitectura utilizado para diseñar una aplicación empresarial, la implementación de esas aplicaciones pueden variar. Las empresas hospedan aplicaciones en todo, desde hardware físico hasta funciones sin servidor.

## <a name="n-tier-applications"></a>Aplicaciones de n niveles

El [modelo arquitectónico de n niveles](/azure/architecture/guide/architecture-styles/n-tier) es una arquitectura madura y simplemente hace referencia a las aplicaciones que separan diferentes capas lógicas en niveles físicos independientes. La arquitectura de n niveles es una implementación física de una arquitectura de n capas. La implementación más común de esta arquitectura incluye:

- Un nivel de presentación, por ejemplo, una aplicación web.
- Un nivel de acceso a datos o API, como una API REST.
- Una capa de datos, como una base de datos SQL.

![Arquitectura de n niveles](./media/n-tier-architecture.png)

Las soluciones de n niveles tienen las características siguientes:

- Los proyectos suelen estar alineados con los niveles.
- Las pruebas se pueden abordar de manera diferente según el nivel.
- Los niveles proporcionan capas de abstracción; por ejemplo, el nivel de presentación normalmente ignora los detalles de implementación de la capa de datos.
- Por lo general, los niveles solo interactúan con los niveles adyacentes.
- Las versiones suelen administrarse en el nivel de proyecto. Un cambio sencillo de API puede requerir una versión nueva de todo un nivel intermedio.

Este enfoque ofrece varias ventajas, las que incluyen:

- Aislamiento de la base de datos (por lo general, el front-end no tiene acceso directo al back-end de la base de datos).
- Reutilización de la API (por ejemplo, los clientes de aplicaciones web, aplicaciones de escritorio y aplicaciones móviles pueden reutilizar las mismas API).
- Capacidad de escalar horizontalmente niveles independientes entre sí.
- Refactorización del aislamiento: un nivel se puede refactorizar sin afectar a otros niveles.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Entorno local e infraestructura como servicio (IaaS)

El enfoque tradicional para el hospedaje de aplicaciones requiere la compra de hardware y la administración de todas las instalaciones de software, incluido el sistema operativo. Originalmente, esto implicaba centros de datos y hardware físico costosos. Los desafíos que implica el hardware físico operativo son muchos, entre los que se incluyen:

- La necesidad de comprar en exceso "por si acaso" o para escenarios de demanda máxima.
- Protección del acceso físico al hardware.
- Responsabilidad por el error de hardware (por ejemplo, un error de disco).
- Refrigeración.
- Configuración de enrutadores y equilibradores de carga.
- Redundancia energética.
- Protección del acceso a software.

![Enfoque de IaaS](./media/iaas-approach.png)

La virtualización de hardware, a través de "máquinas virtuales", permite la infraestructura como servicio (IaaS). Las máquinas host se particionan de manera eficaz para proporcionar recursos a instancias con asignaciones para su propia memoria, CPU y almacenamiento. El equipo aprovisiona las máquinas virtuales necesarias y configura las redes asociadas y el acceso al almacenamiento.

Para más información, consulte la sección sobre [arquitectura de referencia de n niveles de máquina virtual](/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Aunque la virtualización y la infraestructura como servicio (IaaS) abordan muchos problemas, todavía dejan mucha responsabilidad en manos del equipo de infraestructura. El equipo mantiene las versiones del sistema operativo, aplica las revisiones de seguridad e instala las dependencias de terceros en las máquinas de destino. Las aplicaciones suelen comportarse de manera distinta en las máquina de producción en comparación con el entorno de prueba. Surgen problemas debido a las distintas versiones de dependencia o niveles de SKU de sistema operativo. Aunque muchas organizaciones implementan aplicaciones de n niveles en estos destinos, muchas empresas se benefician de la implementación en un modelo nativo que está más en la nube, como [plataforma como servicio](#platform-as-a-service-paas). Las arquitecturas con microservicios son más desafiantes debido a los requisitos de escalado horizontal para la elasticidad y resistencia.

Para más información, consulte la documentación de [Virtual Machines](/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Plataforma como servicio (PaaS)

Plataforma como servicio (PaaS) ofrece soluciones configuradas que los desarrolladores pueden conectar directamente. PaaS es otro término para el hospedaje administrado. Elimina la necesidad de administrar el sistema operativo base, las revisiones de seguridad y, en muchos casos, las dependencias de terceros. Entre los ejemplos de plataformas se incluyen las aplicaciones web, las bases de datos y los back-ends móviles.

PaaS aborda los desafíos comunes a IaaS. PaaS permite que el desarrollador se centre en el código o el esquema de la base de datos en lugar de cómo se implementa. Entre las ventajas de PaaS se incluyen:

- Modelos de pago por uso que eliminan el recargo de invertir en máquinas inactivas.
- Implementación directa y mejoras de canalizaciones de integración continua (CI), entrega continua (CD) y DevOps.
- Revisiones de seguridad y actualizaciones automáticas.
- Escalado horizontal y escalado vertical (escala elástica) con botón de comando.

La desventaja principal de PaaS solía ser la dependencia del proveedor. Por ejemplo, algunos proveedores de PaaS solo admiten ASP.NET, Node.js u otros lenguajes y plataformas específicos. Productos como Azure App Service han evolucionado para abordar varias plataformas y admiten una variedad de lenguajes y marcos para hospedar aplicaciones web.

![Arquitectura de plataforma como servicio (PaaS)](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software como servicio (SaaS)

El software como servicio o SaaS se hospeda de manera centralizada y está disponible sin necesidad de aprovisionamiento o instalación local. A menudo, SaaS se hospeda en PaaS como plataforma para la implementación de software. SaaS proporciona servicios para ejecutar y conectarse con software existente. SaaS suele ser vertical y específica del sector. SaaS suele tener licencia y habitualmente proporciona un modelo cliente/servidor. La mayoría de las ofertas de SaaS modernas usan aplicaciones basadas en la Web para el cliente. Las empresas suelen considerar SaaS como una solución empresarial para las ofertas de licencias. Por lo general, no se implementa como consideración de arquitectura para la escalabilidad y el mantenimiento de una aplicación. En realidad, la mayoría de las soluciones de SaaS se basan en IaaS, PaaS o back-ends sin servidor.

Obtenga más información sobre SaaS mediante una [aplicación de ejemplo](/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Contenedores y funciones como servicio (FaaS)

Los contenedores son una solución interesante que permite obtener ventajas similares a las de PaaS sin la sobrecarga de IaaS. En esencia, un contenedor es un entorno de tiempo de ejecución que contiene los elementos fundamentales necesarios para ejecutar una aplicación única. El kernel o la parte principal del sistema operativo host y los servicios como el almacenamiento se comparten a través de un host. El kernel compartido permite que los contenedores sean ligeros (algunos son de solo algunos megabytes de tamaño, en comparación con los gigabytes de las máquinas virtuales típicas). Con los hosts que ya se están ejecutando, los contenedores se pueden iniciar rápidamente, lo que facilita la alta disponibilidad. La capacidad de poner en marcha rápidamente los contenedores también proporciona capas adicionales de resistencia. Docker es una de las implementaciones de contenedores más populares.

Las ventajas de los contenedores incluyen:

- Son ligeros y portátiles.
- Son independiente, por lo que no es necesario instalar dependencias.
- Proporcionan un entorno coherente independientemente del host (se ejecuta exactamente igual en un equipo portátil que en un servidor en la nube).
- Se pueden aprovisionar rápidamente para el escalado horizontal.
- Se pueden reiniciar rápidamente para recuperarse de un error.

Un contenedor se ejecuta en un host de contenedor (que, a su vez, se puede ejecutar en un equipo sin sistema operativo o en una máquina virtual). Se pueden ejecutar varios contenedores o instancias de los mismos contenedores en un solo host. En el caso de una conmutación por error y resistencia verdaderas, los contenedores se deben escalar entre los hosts.

Para más información sobre los contenedores de Docker, consulte [¿Qué es Docker?](../microservices/container-docker-introduction/docker-defined.md)

Por lo general, la administración de contenedores entre los hosts requiere una herramienta de orquestación como Kubernetes. La configuración y administración de las soluciones de orquestación puede agregar sobrecarga y complejidad adicionales a los proyectos. Afortunadamente, muchos proveedores de nube proporcionan servicios de orquestación a través de soluciones PaaS para simplificar la administración de contenedores.

En la imagen siguiente se muestra una instalación de Kubernetes de ejemplo. Los nodos de la instalación abordan la escalabilidad horizontal y la conmutación por error. Ejecutan instancias de contenedor de Docker administradas por el servidor maestro. *Kubelet* es el cliente que retransmite los comandos de Kubernetes a Docker.

![Kubernetes](./media/kubernetes-example.png)

Para más información sobre la orquestación, consulte [Kubernetes en Azure](/azure/aks/intro-kubernetes).

Funciones como servicio (FaaS) es un servicio de contenedor especializado similar a sin servidor. Una implementación específica de FaaS, denominada [OpenFaaS](https://github.com/openfaas/faas), se basa en contenedores para proporcionar funcionalidades sin servidor. OpenFaaS proporciona plantillas que empaquetan todas las dependencias de contenedor necesarias para ejecutar un fragmento de código. El uso de plantillas simplifica el proceso de implementación de código como una unidad funcional. OpenFaaS está destinado a arquitecturas que ya incluyen contenedores y orquestadores, porque puede usar la infraestructura existente. Aunque proporciona funcionalidad sin servidor, requiere específicamente el uso de Docker y un orquestador.

## <a name="serverless"></a>Sin servidor

Una arquitectura sin servidor proporciona una separación clara entre el código y su entorno de hospedaje. El código se implementa en una *función* que se invoca mediante un *desencadenador*. Una vez que finaliza la función, es posible que se liberen todos los recursos necesarios. El desencadenador puede ser manual, un proceso con tiempo, una solicitud HTTP o una carga de archivos. El resultado del desencadenador es la ejecución del código. Aunque las plataformas sin servidor varían, la mayoría proporciona acceso a las API y enlaces predefinidos para simplificar tareas como la escritura en una base de datos o la puesta en cola de los resultados.

Una arquitectura sin servidor es una arquitectura que se basa en gran medida en abstraer el entorno de host para centrarse en el código. Puede considerarse como de *menos servidor*.

Las soluciones de contenedor proporcionan a los desarrolladores scripts de compilación existentes para publicar código en imágenes listas para usar sin servidor. Otras implementaciones usan soluciones PaaS existentes para proporcionar una arquitectura escalable.

La abstracción significa que no es necesario que el equipo de DevOps aprovisione ni administre servidores ni contenedores específicos. La plataforma sin servidor hospeda código, como archivos ejecutables empaquetados o de script compilados con un SDK relacionado, y asigna los recursos necesarios para que el código se escale.

En la ilustración siguiente se diagraman cuatro componentes sin servidor. Una solicitud HTTP hace que se ejecute el código de Checkout API. Checkout API inserta código en una base de datos y la instrucción INSERT desencadena varias otras funciones que se ejecutan para realizar tareas como tareas informáticas y el cumplimiento del pedido.

![Implementación sin servidor](./media/serverless-implementation.png)

Entre las ventajas de la implementación sin servidor se incluyen:

- **Alta densidad.** Muchas instancias del mismo código sin servidor se pueden ejecutar en el mismo host en comparación con los contenedores o las máquinas virtuales. Las instancias se escalan en varios hosts de escala horizontal y resistencia.
- **Microfacturación.** La mayoría de los proveedores sin servidor facturan en función de las ejecuciones sin servidor, lo que permite ahorrar costos enormes en ciertos escenarios.
- **Escala instantánea.** La implementación sin servidor se puede escalar para que coincida con las cargas de trabajo de manera automática y rápida.
- **Tiempo de comercialización más rápido.** Los desarrolladores se centran en el código e implementan directamente en la plataforma sin servidor. Los componentes se pueden liberar independientemente entre sí.

Sin servidor se suele describir en el contexto de proceso, pero también se puede aplicar a los datos. Por ejemplo, [Azure SQL](/azure/sql-database) y [Cosmos DB](/azure/cosmos-db) proporcionan bases de datos en la nube que no requieren la configuración de clústeres o máquinas host. Este libro se centra en el proceso sin servidor.

## <a name="summary"></a>Resumen

Hay una amplia variedad de opciones disponibles para la arquitectura, incluido un enfoque híbrido. La implementación sin servidor simplifica el enfoque, la administración y el costo de las características de la aplicación a costa del control y la portabilidad. Sin embargo, muchas plataformas sin servidor exponen la configuración para ayudar a ajustar la solución. Una buena práctica de programación también puede conducir a un código más portátil y menos bloqueo de plataforma sin servidor. En la tabla siguiente se muestran los enfoques de la arquitectura en paralelo. Elija una implementación sin servidor en función de las necesidades de escalado, independientemente de si desea administrar el entorno de tiempo de ejecución y qué tan bien puede dividir las cargas de trabajo en componentes pequeños. En el capítulo siguiente obtendrá información sobre posibles desafíos con la implementación sin servidor y otros puntos de decisión.

|         |IaaS     |PaaS     |Contenedor|Sin servidor|
|---------|---------|---------|---------|----------|
|**Escalar**|máquina virtual       |Instancia |Aplicación      |Función  |
|**Abstracción**|Hardware|Plataforma|Host de SO|Tiempo de ejecución   |
|**Unidad** |máquina virtual       |Proyecto  |Imagen    |Código      |
|**Duración**|Meses|Días a meses|Minutos a días|Milisegundos a minutos|
|**Responsabilidad**|Aplicaciones, dependencias, entorno de tiempo de ejecución y sistema operativo|Aplicaciones y dependencias|Aplicaciones, dependencias y entorno de tiempo de ejecución|Función

- **Escala** se refiere a la unidad que se usa para escalar la aplicación
- **Abstracción** se refiere a la capa que la implementación abstrae
- **Unidad** se refiere al ámbito de la implementación
- **Duración** se refiere al entorno de tiempo de ejecución típico de una instancia específica
- **Responsabilidad** hace referencia a la sobrecarga para compilar, implementar y mantener la aplicación

El capítulo siguiente se centrará en la arquitectura sin servidor, los casos de uso y los modelos de diseño.

## <a name="recommended-resources"></a>Recursos recomendados

- [Guía de la arquitectura de aplicaciones en Azure](/azure/architecture/guide/)
- [Azure Cosmos DB](/azure/cosmos-db)
- [SQL de Azure](/azure/sql-database)
- [Estilo de arquitectura de n niveles](/azure/architecture/guide/architecture-styles/n-tier)
- [Kubernetes en Azure](/azure/aks/intro-kubernetes)
- [Microservicios](/azure/architecture/guide/architecture-styles/microservices)
- [Arquitectura de referencia de n niveles de máquina virtual](/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
- [Máquinas virtuales](/azure/virtual-machines/)
- [¿Qué es Docker?](../microservices/container-docker-introduction/docker-defined.md)
- [Aplicación SaaS Wingtip Tickets](/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Anterior](architecture-approaches.md)
>[Siguiente](serverless-architecture.md)
