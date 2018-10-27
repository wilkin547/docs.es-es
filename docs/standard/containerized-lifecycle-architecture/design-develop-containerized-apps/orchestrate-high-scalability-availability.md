---
title: Orquestación de microservicios y aplicaciones de varios contenedores de alta escalabilidad y disponibilidad
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 993f1d18637f39b6df4d876db8a0fe86e34391e3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192725"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Orquestación de microservicios y aplicaciones de varios contenedores de alta escalabilidad y disponibilidad

La utilización de orquestadores para aplicaciones listas para producción es fundamental si la aplicación se basa en microservicios o simplemente está dividida entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicios, cada microservicio posee su modelo y sus datos para que sea autónomo desde un punto de vista del desarrollo y la implementación. Pero incluso si tiene una aplicación más tradicional que consta de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una aplicación de negocio individual que deben implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de escalar horizontalmente y administrar; por lo tanto, un orquestador es indispensable si desea disponer de una aplicación de varios contenedores para entornos de producción y escalable.

Figura 4-6 ilustra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![](./media/image6.png)

Figura 4-6: un clúster de contenedores

Parece un enfoque lógico. Pero, ¿cómo maneja equilibrio de carga, enrutamiento y orquestar estas aplicaciones compuestas?

La interfaz de línea de comandos (CLI) de Docker satisface las necesidades de administración de un contenedor en un host, pero se queda corto en cuanto a administración de varios contenedores implementados en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, necesita una plataforma de administración que automáticamente inicie contenedores, suspender, o apagarlos cuando sea necesario y lo ideal es que también controlan cómo tener acceso a recursos como la red y almacenamiento de datos.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas muy simples y pasar a aplicaciones empresariales más grandes con microservicios, debe cambiar a orquestación y plataformas de agrupación en clústeres.

Desde una arquitectura y desarrollo de punto de vista, si son creación grande, enterprise, basada en microservicios, aplicaciones, es importante comprender las siguientes plataformas y productos que admiten escenarios avanzados:

-   **Clústeres y orquestadores** cuando necesite escalar-horizontal de aplicaciones en varios hosts de Docker, como con una aplicación grande basada en microservicios, es fundamental poder administrar todos los hosts como un solo clúster por abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y los orquestadores. Ejemplos de orquestadores son Docker Swarm, Mesosphere DC/OS, Kubernetes (los tres primeros disponibles a través de Azure Container Service) y Azure Service Fabric.

-   **Los programadores** *programación* significa tener la capacidad para que un administrador inicie los contenedores en un clúster para que también proporcionan una interfaz de usuario. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, para establecer las restricciones definidas por el usuario a los contenedores de equilibrio de carga eficazmente entre los nodos o hosts y ser resistente a errores proporcionando alto disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen ofrecer ambos conjuntos de funciones. Tabla 4-1 enumera las plataformas más importantes y opciones de software que tiene para clústeres y programadores. Por lo general, estos clústeres se ofrecen en nubes públicas como Azure.

Tabla 4-1: plataformas de Software para agrupación en clústeres de contenedor, orquestación y programación

| Plataforma | Descripción |
|---|---|
| Docker Swarm<br/> ![Logotipo de docker Swarm](./media/image7.png) | Docker Swarm permite agrupar y programar los contenedores de Docker. Con Swarm se puede convertir un grupo de hosts de Docker en un único host virtual de Docker. Los clientes pueden realizar solicitudes de API para Swarm en la misma manera que lo hacen para hosts, lo que significa que Swarm facilita las aplicaciones escalen a varios hosts. <br /><br /> Docker Swarm es un producto de la empresa Docker. <br /><br /> Docker v1.12 o posterior puede ejecutar el modo nativo e integrado de Swarm. |
| Mesosphere DC/OS<br/>![Logotipo de mesosphere DC/OS](./media/image8.png) |  Mesosphere Enterprise DC/OS (basado en Apache Mesos) es una plataforma para entornos de producción que permite ejecutar contenedores y aplicaciones distribuidas. <br /><br /> DC/OS funciona mediante la abstracción de una colección de los recursos disponibles en el clúster y poniendo dichos recursos a disposición de los componentes creados sobre él. Marathon suele utilizarse como un programador integrado con DC/OS. |
| Google Kubernetes<br />![Logotipo de Google Kubernetes](./media/image9.png) | Kubernetes es un producto de código abierto cuya funcionalidad abarca desde la infraestructura de clúster y la programación de contenedores a las capacidades de orquestación. Con ella, puede automatizar la implementación, escalado y las operaciones de contenedores de aplicaciones a través de clústeres de hosts. <br /><br /> Kubernetes proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección. |
| Azure Service Fabric<br />![Logotipo de Azure Service Fabric](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) es una plataforma de microservicios de Microsoft para crear aplicaciones. Es un [orquestador](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) de servicios y crea clústeres de máquinas. De forma predeterminada, Service Fabric implementa y activa los servicios como procesos, pero Service Fabric puede implementar servicios en imágenes de contenedor de Docker. Más importante, puede mezclar servicios en procesos con servicios en contenedores en la misma aplicación. <br /><br /> A partir de mayo de 2017, la característica de Service Fabric que admite servicios de implementación como contenedores de Docker está en estado de vista previa. <br /><br /> Puede desarrollar servicios de Service Fabric en muchos sentidos, del uso de la [modelos de programación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) a la implementación [ejecutables invitados](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) , así como contenedores. Service Fabric admite modelos de aplicación preceptiva como [servicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>Uso de orquestadores de contenedor en Azure

Varios proveedores de nube ofrecen compatibilidad con contenedores de Docker y clústeres de Docker y compatibilidad con la orquestación, incluidos Azure, Amazon EC2 Container Service y Google Container Engine. Azure proporciona compatibilidad con orquestador y clúster a través de Azure Container Service, de Docker como se explica en la sección siguiente.

Otra opción consiste en usar a Azure Service Fabric, que también es compatible con Docker basado en contenedores de Windows y Linux. Service Fabric se ejecuta en Azure o cualquier otra nube, así como [local](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso de Azure Container Service

Un clúster de Docker agrupa varios hosts de Docker y los expone como un único host virtual de Docker, lo que permite implementar varios contenedores en el clúster. El clúster controlará todas las conexiones subyacentes de administración complejas como la escalabilidad y el mantenimiento. Figura 4-7 representa cómo se asigna un clúster de Docker para aplicaciones compuestas en Container Service.

Servicio de contenedor proporciona una forma de simplificar la creación, configuración y administración de un clúster de máquinas virtuales preconfiguradas para ejecutar aplicaciones en contenedores. Con una configuración optimizada de herramientas de orquestación y programación de código abierto populares, Container Service le permite usar habilidades existentes o dibujar en un gran Corpus creciente de expertos comunitarios para implementar y administrar basadas en contenedores aplicaciones en Azure.

Container Service optimiza la configuración de las populares herramientas de código abierto de agrupación en clústeres de Docker y tecnologías diseñadas especialmente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador, y Azure Container Service se encarga de todo lo demás.

Container Service utiliza imágenes de Docker para asegurarse de que los contenedores de su aplicación sean completamente portátiles. Es compatible con las plataformas de orquestación de código abierto como DC/OS, Kubernetes y Docker Swarm que prefiera para asegurarse de que estas aplicaciones pueden escalarse a miles o incluso a decenas de miles de contenedores.

Con Azure Container Service, puede aprovechar las características de nivel empresarial de Azure sin perder la portabilidad de aplicaciones, incluso en las capas de orquestación.

![](./media/image11.png)

Figura 4-7: agrupación en clústeres opciones en Azure Container Service

Como se muestra en la figura 4-8, el servicio de contenedor es simplemente la infraestructura proporcionada por Azure para implementar DC/OS, Kubernetes o Docker Swarm, pero no implementa ningún orquestador adicional. Por lo tanto, el servicio de contenedor es no un orquestador, como tal. es sólo una infraestructura que aprovecha los orquestadores de código abierto existentes para contenedores.

![](./media/image12.png)

Figura 4-8: Orquestadores en Container Service

Desde una perspectiva de uso, el objetivo de Container Service es proporcionar un entorno de hospedaje de contenedores mediante tecnologías y herramientas populares de código abierto. Para ello, expone los puntos de conexión de API estándar para el orquestador elegido. Mediante el uso de estos puntos de conexión, puede usar cualquier software que pueda comunicarse con esos puntos de conexión. Por ejemplo, en el caso del punto de conexión Docker Swarm, puede usar la CLI de Docker. Para DC/OS, puede utilizar la CLI de DC/OS.

### <a name="getting-started-with-container-service"></a>Introducción a Container Service

Para empezar a usar Container Service, implemente un clúster de Container Service desde el portal de Azure mediante una plantilla de Azure Resource Manager o la [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Las plantillas disponibles son [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) y [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Puede modificar las plantillas de inicio rápido para incluir la configuración de Azure adicional o avanzada.

**Obtener más información** para más información sobre cómo implementar un clúster de Container Service, en el sitio Web de Azure, lea [implementar un clúster de Azure Container Service](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

No hay cuotas para el software instalado de forma predeterminada como parte de ACS. Todas las opciones predeterminadas se implementan con el software de código abierto.

Servicio de contenedor está actualmente disponible para estándar A, D, DS, G y GS serie VM de Linux en Azure. Se le cobrará solo para las instancias de proceso que elija, así como los otros recursos de infraestructura subyacentes consumidos, como almacenamiento y redes. No hay cargos incrementales para servicio de contenedor propio.

### <a name="additional-resources"></a>Recursos adicionales

Estos son ubicaciones donde puede encontrar información adicional:

-   Introducción a soluciones de contenedor de servicio de hospedaje de contenedores de Docker:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Introducción a docker Swarm:  
    <https://docs.docker.com/swarm/overview/>

-   Información general de modo swarm:  
    <https://docs.docker.com/engine/swarm/>

-   Información general de mesosphere DC/OS:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (el sitio oficial):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Uso de Service Fabric

Service Fabric surgió de transición de Microsoft de ofrecer productos de "caja", que eran habitualmente monolíticos en estilos, para ofrecer servicios. La experiencia de crear y operar servicios grandes a escala, como Azure SQL Database, Azure Document DB, Azure Service Bus o Backend de Cortana, en forma de Service Fabric. La plataforma evolucionó con el tiempo, a medida que la adoptaron cada vez más servicios. Cabe destacar que Service Fabric tuvo que ejecutarse no solo en Azure sino también en implementaciones independientes de Windows Server.

El objetivo de Service Fabric es solucionar los problemas difíciles de generar y ejecutar un servicio y usar eficazmente los recursos de infraestructura para que los equipos puedan resolver problemas empresariales con un enfoque de microservicios.

Service Fabric proporciona dos áreas generales para ayudarlo a crear aplicaciones que usan un enfoque de microservicios:

-   Una plataforma que proporciona servicios de sistema para implementar, escalar, actualizar, detectar y reiniciar servicios erróneos, detectar la ubicación del servicio, administrar el estado y supervisar el mantenimiento. Aplique estos servicios del sistema proporcionan muchas de las características de microservicios descritas anteriormente.

-   Programar API, o marcos, para ayudarlo a crear aplicaciones como microservicios: [actores fiables y servicios de confianza](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Por supuesto, puede elegir cualquier código para generar el microservicio, pero estas API facilitan el trabajo y se integran con la plataforma a un nivel más profundo. De este modo, puede obtener información de mantenimiento y diagnóstico o puede sacar partido de la administración de estado confiable.

Para crear su servicio puede usar cualquier tecnología ya que Service Fabric no interviene en el proceso. Sin embargo, proporciona API de programación integradas que facilitan la creación de microservicios.

Figura 4-9 se muestra cómo puede crear y ejecutar microservicios en Service Fabric como procesos simples o como contenedores de Docker. También es posible mezclar microservicios basados en contenedores con microservicios basados en procesos en el mismo clúster de Service Fabric.

![](./media/image13.png)

Figura 4-9: implementación de microservicios como procesos o como contenedores en Azure Service Fabric

Los clústeres de Service Fabric basados en hosts de Linux y Windows pueden ejecutar contenedores de Docker Linux y Windows.

**Obtener más información** para obtener información actualizada sobre la compatibilidad con contenedores en Service Fabric, en el sitio Web de Azure, lea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric es un buen ejemplo de una plataforma con la que puede definir una arquitectura lógica diferente (microservicios empresariales o contextos delimitados) de la implementación física. Por ejemplo, si implementa [Reliable Services con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) en [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), que se describen en la sección siguiente, "[sin estado frente a microservicios con estado](#stateless-versus-stateful-microservices), "tiene un concepto de microservicio empresarial con varios servicios físicos.

Como se muestra en la figura 4-10 y pensar desde una perspectiva de microservicio lógico/empresarial, al implementar un servicio de Service Fabric con estado confiable, normalmente deberá implementar dos niveles de servicios. La primera es el servicio back-end con estado confiable, que administra varias particiones. El segundo es el servicio front-end, o el servicio de puerta de enlace, a cargo de la agregación de datos y el enrutamiento entre varias particiones o instancias de servicio con estado. Ese servicio de puerta de enlace también controla la comunicación del lado cliente con bucles de reintento acceder al servicio back-end usado junto con el Service Fabric [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Figura 4-10: microservicio de negocios con varios servicios con y sin estado en Service Fabric

En cualquier caso, al usar servicios de confianza con estado de Service Fabric, también dispone de un microservicio lógico o empresarial (contexto limitado) que normalmente se compone de varios servicios físicos. Cada uno de ellos, el servicio de puerta de enlace y el servicio de partición podría implementarse como servicios de ASP.NET Web API, tal como se muestra en la figura 4-10.

En Service Fabric, puede agrupar e implementar grupos de servicios como una [aplicación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), que es la unidad de empaquetado e implementación para el orquestador o clúster. Por lo tanto, la aplicación de Service Fabric podría asignarse a este empresarial autónomo y límite de microservicio lógico o contexto delimitado, también.

### <a name="service-fabric-and-containers"></a>Service Fabric y contenedores

Con respecto a los contenedores en Service Fabric, también puede implementar servicios en imágenes de contenedor dentro de un clúster de Service Fabric. Figura 4-11 se muestra que la mayor parte del tiempo, habrá un único contenedor por cada servicio.

![](./media/image15.png)

Figura 4-11: microservicio de negocios con varios servicios (contenedores) en Service Fabric

Sin embargo, los contenedores llamados "asociados" (dos contenedores que deben implementarse conjuntamente como parte de un servicio lógico) también son posibles en Service Fabric. Lo importante es que un microservicio empresarial sea el límite lógico alrededor de varios elementos cohesivos. En muchos casos, podría ser un único servicio con un único modelo de datos, pero en otros casos, es posible que tenga varios servicios físicos, también.

A partir de redactar este artículo (abril de 2017), en Service Fabric no se puede implementar servicios con estado confiables de SF en contenedores, puede implementar solo contenedores de invitado, servicios sin estado o servicios de actor en contenedores. Pero tenga en cuenta que puede mezclar servicios en procesos y servicios en contenedores en la misma aplicación de Service Fabric, como se muestra en la figura 4-12.

![](./media/image16.png)

Figura 4-12: microservicio de negocios asignada a una aplicación de Service Fabric con contenedores y servicios con estado

Soporte técnico también es diferente en función de si usa contenedores de Docker en Linux o contenedores de Windows. Compatibilidad con contenedores en Service Fabric se ampliará en las próximas versiones. Para noticias actualizadas sobre la compatibilidad con contenedores en Service Fabric, en el sitio Web de Azure, lea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservicios sin estado frente a microservicios con estado

Como se ha mencionado anteriormente, cada microservicio (contexto limitado lógico) debe tener su modelo de dominio (datos y lógica). En el caso de los microservicios sin estado, las bases de datos serán externas y se utilizarán opciones relacionales, como SQL Server u opciones de NoSQL, como MongoDB o Azure DocumentDB.

Pero los propios servicios también pueden ser con estado, lo que significa que los datos residen en el microservicio. Estos datos podrían existir no solo en el mismo servidor, pero dentro del proceso del microservicio, en la memoria y se conservan en las unidades y replicación en otros nodos. Figura 4-13 muestra los diferentes enfoques.

![](./media/image17.png)

Figura 4-13: sin estado frente a microservicios con estado

Un enfoque sin estado es perfectamente válido y es más fácil de implementar que los microservicios con estado porque el enfoque es similar a los patrones tradicionales y conocidos. Pero los microservicios sin estado imponen latencia entre el proceso y los orígenes de datos. También implican más piezas móviles cuando se intenta mejorar el rendimiento con memoria caché y colas adicionales. El resultado es que puede acabar con arquitecturas complejas que tienen demasiados niveles.

En cambio, [microservicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) pueden destacar en escenarios avanzados, porque no hay latencia entre los datos y la lógica del dominio. Back-end de juegos del muchos recursos de procesamiento de datos, las bases de datos como un servicio y otros escenarios de baja latencia se beneficiarán de servicios con estado, que proporcionan el estado local para un acceso más rápido.

Los servicios sin estado y los servicios con estado se complementan. Por ejemplo, un servicio con estado se pueden dividir en varias particiones. Para acceder a esas particiones, es posible que deba contar con un servicio sin estado que actúe como un servicio de puerta de enlace que sepa cómo dirigirse a cada partición en función de las claves de partición.

Los servicios con estado tienen diversos inconvenientes. Imponen un nivel de complejidad que les permite escalar horizontalmente. Las funciones que normalmente se implementarían mediante sistemas de bases de datos externas se debe abordar en tareas como la replicación de datos a través de microservicios con estado y la creación de particiones de datos. Sin embargo, esta es una de las áreas donde un orquestador como [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con su [reliable services con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede ayudar al máximo, por lo que simplifica el desarrollo y el ciclo de vida de con estado uso de microservicios la [API de Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Otros marcos de microservicio que permiten los servicios con estado, que admiten el patrón de actor y que mejoran la tolerancia a errores y la latencia entre la lógica y los datos empresariales son Microsoft [Orleans](https://github.com/dotnet/orleans), de Microsoft Research, y [ Akka.NET](https://getakka.net/). Actualmente, ambos marcos están mejorando su compatibilidad con Docker.

Tenga en cuenta que los contenedores de Docker son sin estado. Si quiere implementar un servicio con estado, debe contar con uno de los marcos prescriptivos y de nivel superior adicionales que se han indicado anteriormente. Sin embargo, cuando se redactó este documento, no se admiten los servicios con estado en Service Fabric como contenedores, solo como microservicios sin formato. Compatibilidad con Reliable services en contenedores estará disponible en próximas versiones de Service Fabric.


>[!div class="step-by-step"]
[Anterior](soa-applications.md)
[Siguiente](docker-apps-development-environment.md)
