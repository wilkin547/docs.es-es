---
title: Orquestar microservicios y multicontainer aplicaciones de alta escalabilidad y disponibilidad
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 3a505e10b2a37032a7ccfefdf4a6f4bb64d65486
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Orquestar microservicios y multicontainer aplicaciones de alta escalabilidad y disponibilidad

La utilización de orquestadores para aplicaciones listas para producción es fundamental si la aplicación se basa en microservicios o simplemente está dividida entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicios, cada microservicio posee su modelo y sus datos para que sea autónomo desde un punto de vista del desarrollo y la implementación. Pero incluso si tiene una aplicación más tradicional que se compone de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una aplicación de negocio individual que deben implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de escalar y administrar; por lo tanto, sea absolutamente necesario organizador si desea tener una aplicación multicontainer para entornos de producción y escalable.

Figura 4-6 muestra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![](./media/image6.png)

Figura 4-6: un clúster de contenedores

Parece un enfoque lógico. Pero, ¿cómo se manipule el equilibrio de carga, enrutamiento y orquestar estas aplicaciones compuestas?

La interfaz de línea de comandos (CLI) de Docker satisface las necesidades de la administración de un contenedor en un host, pero no cumple las expectativas en cuanto a la administración de varios contenedores de implementada en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, necesita una plataforma de administración que automáticamente inicie contenedores, suspender, o apagarlos cuando sea necesario y lo ideal es que también controlan cómo tener acceso a recursos como la red y almacenamiento de datos.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas muy simples y pasar a aplicaciones empresariales más grandes con microservicios, debe cambiar a orquestación y plataformas de agrupación en clústeres.

Desde una arquitectura y desarrollo de punto de vista, si es la empresa de gran tamaño, creación, basado en microservicios, aplicaciones, es importante comprender las siguientes plataformas y productos que admiten escenarios avanzados:

-   **Clústeres y orchestrators** cuando necesite escalar-out las aplicaciones a través de varios hosts de Docker, como con una aplicación basada en microservicios grande, es fundamental para poder administrar todos los hosts como un solo clúster por la abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y los orquestadores. Ejemplos de orchestrators son Docker Swarm, Mesosphere DC/OS, Kubernetes (las tres primeras disponibles a través del servicio de contenedor de Azure) y Azure Service Fabric.

-   **Los programadores** *programación* significa tener la capacidad para que un administrador iniciar contenedores en un clúster para que también proporcionan una interfaz de usuario. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, para establecer las restricciones proporcionadas por el usuario, a los contenedores de equilibrar la carga eficazmente entre nodos o hosts y para ser robustas frente a errores al proporcionar alto disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen ofrecer ambos conjuntos de funciones. Tabla 4-1 muestra la plataforma más importante y opciones de software que tiene para clústeres y programadores. Por lo general, estos clústeres se ofrecen en nubes públicas como Azure.

Tabla 4-1: plataformas de Software para el contenedor de agrupación en clústeres, la orquestación y la programación

| Plataforma | Descripción |
|---|---|
| Docker Swarm<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Conjunto de docker ofrece la capacidad en el clúster y programar los contenedores de Docker. Con Swarm se puede convertir un grupo de hosts de Docker en un único host virtual de Docker. Los clientes pueden hacer solicitudes de API para el conjunto de la misma manera que lo hacen a los hosts, lo que significa que conjunto facilita las aplicaciones escalar a varios hosts. <br /><br /> Docker Swarm es un producto de la empresa Docker. <br /><br /> Docker v1.12 o posterior puede ejecutar el modo nativo e integrado de Swarm. |
| Mesosphere DC/OS<br/>![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image8.png) |  Mesosphere Enterprise DC/OS (basado en Apache Mesos) es una plataforma para entornos de producción que permite ejecutar contenedores y aplicaciones distribuidas. <br /><br /> DC/OS funciona mediante la abstracción de una colección de los recursos disponibles en el clúster y poniendo dichos recursos a disposición de los componentes creados sobre él. Marathon suele utilizarse como un programador integrado con DC/OS. |
| Google Kubernetes<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes es un producto de código abierto cuya funcionalidad abarca desde la infraestructura de clúster y la programación de contenedores a las capacidades de orquestación. Con él, puede automatizar la implementación, ajuste de escala y las operaciones de contenedores de aplicaciones a través de clústeres de hosts. <br /><br /> Kubernetes proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección. |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) es una plataforma de microservicios de Microsoft para crear aplicaciones. Es un [orquestador](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) de servicios y crea clústeres de máquinas. De forma predeterminada, Service Fabric implementa y activa los servicios como procesos, pero Service Fabric puede implementar servicios en las imágenes de contenedor de Docker. Más importante, puede mezclar servicios en procesos con los servicios de los contenedores en la misma aplicación. <br /><br /> A partir de mayo de 2017, la característica de Service Fabric que admita servicios de implementación como contenedores de Docker está en estado de vista previa. <br /><br /> Puede desarrollar servicios de Service Fabric en muchos sentidos, del uso de la [modelos de programación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) hasta la implementación [invitado ejecutables](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) , así como contenedores. Service Fabric admite modelos de aplicación preceptiva como [servicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>Uso de orchestrators basada en el contenedor de Azure

Varios proveedores de nube que ofrecen compatibilidad con contenedores de Docker más clústeres de Docker y soporte de orquestación, que incluye Azure, el servicio de contenedor de Amazon EC2 y motor de contenedor de Google. Azure proporciona a Docker soporte de clúster y orchestrator a través del servicio de contenedor de Azure, como se explica en la sección siguiente.

Otra opción consiste en utilizar a Azure Service Fabric, que también es compatible con Docker en función de los contenedores de Windows y Linux. Tejido de servicio se ejecuta en Azure o cualquier otra en la nube como [local](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso de Azure Container Service

Un clúster de Docker agrupa varios hosts de Docker y los expone como un único host virtual de Docker, lo que permite implementar varios contenedores en el clúster. El clúster controlará todas las conexiones subyacentes de administración complejas como la escalabilidad y el mantenimiento. Figura 4-7 representa cómo se asigna un clúster de Docker para aplicaciones compuestos al servicio de contenedor.

Servicio de contenedor proporciona una manera de simplificar la creación, configuración y administración de un clúster de máquinas virtuales que están preconfigurados para ejecutar aplicaciones en contenedores. Utilizar una configuración optimizada de herramientas de programación y la orquestación de código abierto populares, contenedor de servicio ofrece la capacidad de utilizar sus conocimientos existentes o dibujar en un cuerpo elevado y creciente de especialización de la Comunidad para implementar y administrar en función de contenedor aplicaciones de Azure.

Servicio de contenedor optimiza la configuración de populares tecnologías y herramientas de código abierto de agrupación en clústeres de Docker específicamente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador, y Azure Container Service se encarga de todo lo demás.

Servicio de contenedor usa imágenes de Docker para asegurarse de que los contenedores de la aplicación sean totalmente portables. Es compatible con la elección de plataformas de orquestación de código abierto como controlador de dominio/OS, Kubernetes y Docker Swarm para asegurarse de que estas aplicaciones pueden escalar hasta miles o incluso decenas de miles de contenedores.

Con el servicio de contenedor de Azure, puede sacar partido de las características de nivel empresarial de Azure manteniendo la portabilidad de aplicación, incluidos en las capas de la orquestación.

![](./media/image11.png)

Figura 4-7: agrupación en clústeres opciones en el servicio de contenedor de Azure

Como se muestra en la figura 4-8, servicio de contenedor es simplemente la infraestructura proporcionada por Azure para implementar el controlador de dominio/OS, Kubernetes o Docker Swarm, pero no implementa ningún orchestrator adicional. Por lo tanto, el servicio de contenedor es no organizador, como tal; es solo una infraestructura que aprovecha las ventajas de existentes orchestrators de código abierto para contenedores.

![](./media/image12.png)

Figura 4-8: Orchestrators en el servicio de contenedor.

Desde una perspectiva de uso, el objetivo de servicio de contenedor es proporcionar un entorno de hospedaje de contenedor mediante el uso de tecnologías y herramientas de código abierto populares. Para ello, expone los puntos de conexión de API estándar para el orquestador elegido. Mediante el uso de estos puntos de conexión, puede usar cualquier software que se puede comunicar con los puntos de conexión. Por ejemplo, en el caso extremo de Docker Swarm, puede utilizar la CLI de Docker. Para DC/OS, puede utilizar la CLI de DC/OS.

### <a name="getting-started-with-container-service"></a>Introducción a servicio de contenedor.

Para empezar a usar el servicio de contenedor, implementar un clúster de servicio de contenedor desde el portal de Azure mediante una plantilla de Azure Resource Manager o la [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Las plantillas disponibles son [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) y [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Puede modificar las plantillas de inicio rápido para incluir la configuración de Azure adicional o avanzado.

**Obtener más información** para más información acerca de cómo implementar un clúster de servicio de contenedor, en el sitio Web de Azure, vea [implementar un clúster de servicio de contenedor de Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

No hay cuotas para el software instalado de forma predeterminada como parte de ACS. Todas las opciones predeterminadas se implementan con el software de código abierto.

Servicio de contenedor está actualmente disponible para un estándar, D, DS, G y GS serie Linux VM en Azure. Se le cobra solo para las instancias de proceso que elija, así como los otros subyacente recursos de infraestructura utilizados, por ejemplo, red y almacenamiento. No hay ningún cargo incremental para servicio de contenedor propio.

### <a name="additional-resources"></a>Recursos adicionales

A continuación se indican las ubicaciones donde puede encontrar información adicional:

-   Introducción al contenedor de Docker hospedar soluciones con el servicio de contenedor:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Información general del conjunto de docker:  
    <https://docs.docker.com/swarm/overview/>

-   Información general del modo de conjunto:  
    <https://docs.docker.com/engine/swarm/>

-   Información general de DC/OS mesosphere:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (el sitio oficial):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Uso de Service Fabric.

Service Fabric procedan de transición de Microsoft de entrega de productos "cuadro", que son normalmente monolíticos en estilo, en la entrega de servicios. La experiencia de creación y utilización de servicios de gran tamaño a escala, como la base de datos de SQL Azure, base de datos de documentos de Azure, Service Bus de Azure o back-end de Cortana, en forma de Service Fabric. La plataforma evolucionó con el tiempo, a medida que la adoptaron cada vez más servicios. Cabe destacar que Service Fabric tuvo que ejecutarse no solo en Azure sino también en implementaciones independientes de Windows Server.

El objetivo de Service Fabric es solucionar los problemas difíciles de generar y ejecutar un servicio y utilización de recursos de infraestructura eficaz para que los equipos pueden resolver problemas empresariales con un enfoque de microservicios.

Service Fabric proporciona dos áreas generales para ayudarlo a crear aplicaciones que usan un enfoque de microservicios:

-   Una plataforma que proporciona servicios de sistema para implementar, escalar, actualizar, detectar y reiniciar servicios erróneos, detectar la ubicación del servicio, administrar el estado y supervisar el mantenimiento. Aplique estos servicios del sistema proporcionan muchas de las características de microservicios que se ha descrito anteriormente.

-   Programar API, o marcos, para ayudarlo a crear aplicaciones como microservicios: [actores fiables y servicios de confianza](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Por supuesto, puede elegir cualquier código para generar el microservicio, pero estas API facilitan el trabajo y se integran con la plataforma a un nivel más profundo. De este modo, puede obtener información de mantenimiento y diagnóstico o puede sacar partido de la administración de estado confiable.

Para crear su servicio puede usar cualquier tecnología ya que Service Fabric no interviene en el proceso. Sin embargo, proporciona API de programación integradas que facilitan la creación de microservicios.

Figura 4-9 se muestra cómo puede crear y ejecutar microservicios en Service Fabric como procesos simples o como contenedores de Docker. También es posible mezclar microservicios basados en contenedores con microservicios basados en procesos en el mismo clúster de Service Fabric.

![](./media/image13.png)

Figura 4-9: implementar microservicios como procesos o como contenedores en Azure Service Fabric

Clústeres de Service Fabric basados en hosts de Linux y Windows pueden ejecutar contenedores de Docker Linux y Windows.

**Obtener más información** para obtener información actualizada sobre la compatibilidad con contenedores de Service Fabric, en el sitio Web de Azure, lea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric es un buen ejemplo de una plataforma con el que puede definir una arquitectura lógica diferente (microservicios de negocios o contextos limitado) de la implementación física. Por ejemplo, si implementa [Reliable Services con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) en [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), que se introducen en la siguiente sección, "[Stateless frente a microservicios con estado](#stateless-versus-stateful-microservices), "tiene un concepto de microservicio empresarial con varios servicios físicos.

Como se muestra en la figura 4-10 y pensar desde una perspectiva de lógica de negocios/microservicio, al implementar un servicio confiable de servicio de Fabric con estado, normalmente debe implementar dos niveles de servicios. El primero es el servicio back-end con estado confiable, que administra varias particiones. El segundo es el servicio front-end, o servicio de puerta de enlace, que se encarga del enrutamiento y de la agregación de datos en varias particiones o instancias de servicio con estado. Ese servicio de puerta de enlace también controla la comunicación de cliente con bucles vuelva a intentar obtener acceso al servicio de back-end que se usa junto con el tejido de servicio [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Figura 4-10: Business microservicio con varios servicios con estado y sin estado de Service Fabric

En cualquier caso, al usar servicios de confianza con estado de Service Fabric, también dispone de un microservicio lógico o empresarial (contexto limitado) que normalmente se compone de varios servicios físicos. Cada uno de ellos, el servicio de puerta de enlace y el servicio de partición podría implementarse como servicios de ASP.NET Web API, como se muestra en la figura 4-10.

En Service Fabric, puede agrupar e implementar grupos de servicios como una [aplicación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), que es la unidad de empaquetado e implementación para el orquestador o clúster. Por lo tanto, la aplicación de servicio de Fabric podría asignarse a este independientes y el límite de microservicio lógico o el contexto limitado, también.

### <a name="service-fabric-and-containers"></a>Service Fabric y contenedores

Con respecto a los contenedores de Service Fabric, también puede implementar servicios en las imágenes de contenedor dentro de un clúster de Service Fabric. Figura 4-11 muestra que la mayor parte del tiempo, habrá un único contenedor por cada servicio.

![](./media/image15.png)

Figura 4-11: Business microservicio con varios servicios (contenedores) en Service Fabric

Sin embargo, los contenedores llamados "asociado" (dos contenedores que deben implementarse conjuntamente como parte de un servicio lógicos) también son posibles en Service Fabric. Lo importante es que un microservicio empresarial sea el límite lógico alrededor de varios elementos cohesivos. En muchos casos, puede que sea un único servicio con un único modelo de datos, pero en otros casos es posible que tenga varios servicios físicos, también.

A partir de esta escritura (abril de 2017), en Service Fabric no se puede implementar servicios con estado confiables de SF en contenedores, puede implementar solo los contenedores de invitado, servicios sin estado o los servicios de actor en contenedores. Pero tenga en cuenta que se pueden mezclar servicios de procesos y servicios en contenedores en la misma aplicación de Service Fabric, tal como se muestra en la figura 4-12.

![](./media/image16.png)

Figura 4-12: Business microservicio asignada a una aplicación de Service Fabric con contenedores y servicios con estado

Soporte técnico también es diferente en función de si usas contenedores de Docker en contenedores de Windows o Linux. Compatibilidad con contenedores de Service Fabric se ampliará en las próximas versiones. Para noticias actualizadas sobre la compatibilidad de contenedor en el tejido de servicio, en el sitio Web de Azure, lea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservicios sin estado frente a microservicios con estado

Como se ha mencionado anteriormente, cada microservicio (contexto limitado lógico) debe tener su modelo de dominio (datos y lógica). En el caso de microservicios sin estado, las bases de datos será externos, que emplean opciones relacional como SQL Server u opciones de NoSQL como MongoDB o documentos de Azure.

Pero los propios servicios también pueden ser con estado, lo que significa que los datos se encuentran en la microservicio. Estos datos podrían existir no solo en el mismo servidor, pero dentro del proceso de microservicio, en la memoria y se conservan en unidades y replican en otros nodos. Figura 4-13 muestra los distintos enfoques.

![](./media/image17.png)

Figura 4-13: sin estado frente a microservicios con estado

Un enfoque sin estado es perfectamente válido y es más fácil de implementar que microservicios con estado dado el enfoque es similar a patrones tradicionales y conocidos. Pero los microservicios sin estado imponen latencia entre el proceso y los orígenes de datos. También implican más piezas móviles cuando se intenta mejorar el rendimiento con memoria caché y colas adicionales. El resultado es que puede acabar con arquitecturas complejas que tienen demasiados niveles.

En cambio, [microservicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede excel en escenarios avanzados porque no hay ninguna latencia entre la lógica del dominio y los datos. Back-end de juegos del muchos recursos de datos de procesamiento, las bases de datos como un servicio y otros escenarios de baja latencia beneficiarán de servicios con estado, que proporcionan el estado local para un acceso más rápido.

Los servicios sin estado y los servicios con estado se complementan. Por ejemplo, un servicio con estado puede dividirse en varias particiones. Para acceder a esas particiones, es posible que deba contar con un servicio sin estado que actúe como un servicio de puerta de enlace que sepa cómo dirigirse a cada partición en función de las claves de partición.

Los servicios con estado tienen diversos inconvenientes. Que imponen un nivel de complejidad que les permite escalar horizontalmente. Las funciones que normalmente se implementarían mediante sistemas de bases de datos externas se debe abordar en tareas como la replicación de datos a través de microservicios con estado y la creación de particiones de datos. Sin embargo, esta es una de las áreas donde como organizador [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con su [servicios confiables con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede ayudar a la mayoría, ya que simplifica el desarrollo y el ciclo de vida de stateful uso de microservicios la [confiable de servicios de API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Otros marcos de microservicio que permiten los servicios con estado, que admiten el patrón de actor y que mejoran la tolerancia a errores y la latencia entre la lógica y los datos empresariales son Microsoft [Orleans](https://github.com/dotnet/orleans), de Microsoft Research, y [ Akka.NET](https://getakka.net/). Actualmente, ambos marcos están mejorando su compatibilidad con Docker.

Tenga en cuenta que los contenedores de Docker son sin estado. Si quiere implementar un servicio con estado, debe contar con uno de los marcos prescriptivos y de nivel superior adicionales que se han indicado anteriormente. Sin embargo, cuando se redactó este documento, los servicios con estado de Service Fabric no se admiten como contenedores, únicamente como microservicios sin formato. Compatibilidad con los servicios de confianza en contenedores estará disponible en las próximas versiones de Service Fabric.


>[!div class="step-by-step"]
[Anterior] (soa-applications.md) [siguiente] (docker-aplicaciones-desarrollo-environment.md)
