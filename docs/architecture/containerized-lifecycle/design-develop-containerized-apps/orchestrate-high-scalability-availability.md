---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Las aplicaciones de producción real deben implementarse y administrarse con orquestadores que controlen el mantenimiento, la carga de trabajo y los ciclos de vida de todos los contenedores.
ms.date: 02/15/2019
ms.openlocfilehash: 459a445258a8d66834814f7b084fd969d005ff45
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374486"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad

La utilización de orquestadores para aplicaciones listas para producción es fundamental si la aplicación se basa en microservicios o está dividida entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicios, cada microservicio posee su modelo y sus datos para que sea autónomo desde un punto de vista del desarrollo y la implementación. Pero incluso si tiene una aplicación más tradicional que se compone de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una sola aplicación de negocio que deban implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de administrar y escalar horizontalmente; por lo tanto, un orquestador es indispensable si se quiere tener una aplicación de varios contenedores, escalable y lista para la producción.

La figura 4-6 ilustra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![Diagrama que muestra las aplicaciones de Docker en un clúster.](./media/orchestrate-high-scalability-availability/composed-docker-applications-cluster.png)

**Figura 4-6**. Un clúster de contenedores

Parece un enfoque lógico. Pero ¿cómo se está administrando el equilibrio de carga, el enrutamiento y la orquestación de estas aplicaciones compuestas?

La CLI de Docker satisface las necesidades de administración de un contenedor en un host, pero se queda corta a la hora de administrar varios contenedores implementados en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, se necesita una plataforma de administración que automáticamente inicie los contenedores, escale horizontalmente los contenedores con varias instancias por imagen, los suspenda o los cierre cuando sea necesario y, a ser posible, también controle su acceso a recursos como la red y el almacenamiento de datos.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas simples y pasar a aplicaciones empresariales más grandes con microservicios, debe cambiar a orquestación y plataformas de agrupación en clústeres.

Desde el punto de vista de la arquitectura y el desarrollo, si está compilando grandes aplicaciones empresariales basadas en microservicios, es importante familiarizarse con las siguientes plataformas y productos que admiten escenarios avanzados:

- **Clústeres y orquestadores**. Cuando se necesita escalar horizontalmente las aplicaciones a varios hosts de Docker, como con una aplicación grande basada en microservicios, es fundamental poder administrar todos los hosts como un solo clúster mediante la abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y los orquestadores. Azure Service Fabric y Kubernetes son ejemplos de orquestadores. Kubernetes está disponible en Azure a través de Azure Kubernetes Service.

- **Programadores**. *Programar* significa tener la capacidad de que un administrador inicie los contenedores de un clúster, por lo que los programadores también proporcionan una interfaz de usuario para hacerlo. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, establecer las restricciones definidas por el usuario, equilibrar eficazmente la carga de los contenedores entre los distintos nodos o hosts, ser resistente a los errores y proporcionar un alto grado de disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen ofrecer ambos conjuntos de funciones. En la sección siguiente se muestran las plataformas y las opciones de software más importantes disponibles para clústeres y programadores. Estos orquestadores generalmente se ofrecen en nubes públicas como Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Plataformas de software para agrupación en clústeres de contenedores, orquestación y programación

| Plataforma | Comentarios |
|:---:|:---|
| **Kubernetes** <br/> ![Una imagen del logotipo de Kubernetes.](./media/orchestrate-high-scalability-availability/kubernetes-container-orchestration-system-logo.png) | [*Kubernetes*](https://kubernetes.io/) es un producto de código abierto cuya funcionalidad abarca desde la infraestructura de clúster y la programación de contenedores a las capacidades de orquestación. Permite automatizar la implementación, la escala y las operaciones de contenedores de aplicaciones en varios clústeres de hosts. <br/> <br/> *Kubernetes* proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección. <br/> <br/> *Kubernetes* está más desarrollado en Linux que en Windows. |
| **Azure Kubernetes Service (AKS)** <br/> ![Una imagen del logotipo de Azure Kubernetes Service](./media/orchestrate-high-scalability-availability/azure-kubernetes-service-logo.png). | [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/) es un servicio de orquestación de contenedores de Kubernetes administrado en Azure que simplifica la administración, implementación y operaciones del clúster de Kubernetes. |
| **Azure Service Fabric** <br/> ![Imagen del logotipo de Azure Service Fabric.](./media/orchestrate-high-scalability-availability/azure-service-fabric-logo.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) es una plataforma de microservicios de Microsoft para crear aplicaciones. Es un [orquestador](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) de servicios y crea clústeres de máquinas. Service Fabric puede implementar servicios como contenedores o procesos estándar. Puede incluso combinar servicios en procesos con servicios en contenedores dentro de la misma aplicación y el mismo clúster. <br/> <br/> Los clústeres de *Service Fabric* pueden implementarse en Azure, de forma local o en cualquier nube. Con todo, la implementación se simplifica en Azure con un enfoque administrado. <br/> <br/> *Service Fabric* proporciona [modelos de programación de Service Fabric](https://azure.microsoft.com/documentation/articles/service-fabric-choose-framework/) prescriptivos adicionales y opcionales como [servicios con estado](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-services-introduction/) y [Reliable Actors](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-actors-introduction/). <br/> <br/> *Service Fabric* está más desarrollado en Windows (con años de evolución en Windows) que en Linux. <br/> <br/> Tanto los contenedores de Linux como los de Windows son compatibles con Service Fabric desde 2017. |
| **Azure Service Fabric Mesh** <br/> ![Imagen del logotipo de Azure Service Fabric Mesh.](./media/orchestrate-high-scalability-availability/azure-service-fabric-mesh-logo.png) | [*Azure Service Fabric Mesh*](https://docs.microsoft.com/azure/service-fabric-mesh/service-fabric-mesh-overview) ofrece el mismo nivel de fiabilidad, rendimiento crítico y escala que Service Fabric, pero también proporciona una plataforma totalmente administrada y sin servidor. No es necesario administrar un clúster, las máquinas virtuales, el almacenamiento o la configuración de red. Puede centrarse en el desarrollo de la aplicación. <br/> <br/> *Service Fabric Mesh* admite contenedores de Windows y Linux, lo que permite desarrollar con cualquier lenguaje de programación y marco de trabajo que elija.

## <a name="using-container-based-orchestrators-in-azure"></a>Uso de orquestadores basados en contenedor en Azure

Existen varios proveedores de nube que ofrecen compatibilidad con contenedores de Docker más compatibilidad con la orquestación y los clústeres de Docker, como Azure, Amazon EC2 Container Service y Google Container Engine. Azure proporciona compatibilidad con el orquestador y el clúster de Docker a través de Azure Kubernetes Service (AKS), Azure Service Fabric y Azure Service Fabric Mesh.

## <a name="using-azure-kubernetes-service"></a>Uso de Azure Kubernetes Service

Un clúster de Kubernetes agrupa varios hosts de Docker y los expone como un único host virtual de Docker, lo que permite implementar varios contenedores en el clúster y escalar horizontalmente con cualquier número de instancias de contenedor. El clúster controlará toda la mecánica de administración compleja, como la escalabilidad, el estado, etc.

AKS proporciona una manera de simplificar la creación, la configuración y la administración de un clúster de máquinas virtuales en Azure que están preconfiguradas para ejecutar aplicaciones en contenedores. Al utilizar una configuración optimizada de herramientas de orquestación y programación de código abierto populares, AKS le permite usar sus habilidades existentes o aprovechar un gran corpus creciente de conocimientos de la comunidad para implementar y administrar aplicaciones basadas en contenedor en Microsoft Azure.

Azure Kubernetes Service optimiza la configuración de tecnologías y herramientas populares de código abierto de agrupación en clústeres de Docker específicamente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador, y AKS se encarga de todo lo demás.

![Diagrama que muestra una estructura de un clúster de Kubernetes.](./media/orchestrate-high-scalability-availability/kubernetes-cluster-simplified-structure.png)

**Figura 4-7**. Topología y estructura simplificada del clúster de Kubernetes

En la figura 4-7 se muestra la estructura de un clúster de Kubernetes, donde un nodo maestro (VM) controla la mayor parte de la coordinación del clúster y puede implementar contenedores en el resto de los nodos que se administran como un único grupo desde el punto de vista de la aplicación. Esto le permite escalar a miles o incluso a decenas de miles de contenedores.

## <a name="development-environment-for-kubernetes"></a>Entorno de desarrollo para Kubernetes

En el entorno de desarrollo, [Docker anunció en julio de 2018](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/) que Kubernetes también puede ejecutarse en un único equipo de desarrollo (Windows 10 o macOS). Basta con instalar [Docker Desktop](https://www.docker.com/community-edition). Puede implementar posteriormente en la nube (AKS) para obtener más pruebas de integración, como se muestra en la figura 4-8.

![Diagrama que muestra Kubernetes en una máquina de desarrollo y, luego, implementado en AKS.](./media/orchestrate-high-scalability-availability/kubernetes-development-environment.png)

**Figura 4-8**. Ejecución de Kubernetes en el equipo de desarrollo y la nube

## <a name="get-started-with-azure-kubernetes-service-aks"></a>Introducción a Azure Kubernetes Service (AKS)

Para empezar a usar AKS, implemente un clúster de AKS desde Azure Portal o mediante la CLI. Para obtener más información sobre la implementación de un clúster de Kubernetes en Azure, vea [Inicio rápido: Implementación de un clúster de Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

No hay cuotas para el software instalado de forma predeterminada como parte de AKS. Todas las opciones predeterminadas se implementan con el software de código abierto. AKS está disponible en varias máquinas virtuales en Azure. Se cobra únicamente por las instancias de proceso que se elijan, así como por los otros recursos subyacentes de la infraestructura que se utilicen como, por ejemplo, la red y el almacenamiento. No hay ningún cargo incremental para AKS.

Para obtener más información sobre la implementación en Kubernetes en función de `kubectl` y archivos `.yaml` originales, vea [Implementación en Azure Kubernetes Service (AKS)](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)).

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Implementación con gráficos de Helm en clústeres de Kubernetes

Al implementar una aplicación en un clúster de Kubernetes, puede usar la herramienta de CLI `kubectl.exe` original mediante archivos de implementación basados en el formato nativo (archivos `.yaml`), como ya se mencionó en la sección anterior. Pero, para aplicaciones de Kubernetes más complejas, como al implementar aplicaciones complejas basadas en microservicios, se recomienda usar [Helm](https://helm.sh/).

Los gráficos de Helm le ayudan a definir, establecer la versión, instalar, compartir, actualizar o revertir incluso la aplicación más compleja de Kubernetes.

Adicionalmente, el uso de Helm se recomienda porque otros entornos de Kubernetes en Azure, como [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces), también se basan en los gráficos de Helm.

La [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) mantiene Helm en colaboración con Microsoft, Google, Bitnami y la comunidad de colaboradores de Helm.

Para obtener más información sobre la implementación en gráficos de Helm y Kubernetes, vea la sección [Instalación de eShopOnContainers mediante Helm](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#install-eshoponcontainers-using-helm).

## <a name="use-azure-dev-spaces-for-you-kubernetes-application-lifecycle"></a>Uso de Azure Dev Spaces para el ciclo de vida de la aplicación de Kubernetes

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) proporciona una experiencia de desarrollo de Kubernetes rápida e iterativa para los equipos. Con una configuración de máquina de desarrollo mínima, puede ejecutar y depurar contenedores de forma iterativa directamente en Azure Kubernetes Service (AKS). Puede desarrollar en Windows, Mac o Linux mediante herramientas familiares como Visual Studio, Visual Studio Code o la línea de comandos.

Como ya se ha mencionado, Azure Dev Spaces usa gráficos de Helm al implementar aplicaciones basadas en contenedores.

Azure Dev Spaces ayuda a los equipos de desarrollo a ser más productivos en Kubernetes porque permite iterar con rapidez y depurar código directamente en un clúster de Kubernetes global en Azure simplemente mediante el uso de Visual Studio 2017 o Visual Studio Code. Ese clúster de Kubernetes en Azure es un clúster de Kubernetes administrado compartido, por lo que su equipo puede colaborar. Puede desarrollar código de forma aislada, después implementarlo en el clúster global y realizar pruebas de un extremo a otro con otros componentes sin tener que replicar ni simular dependencias.

Como se muestra en la figura 4-9, la característica distintiva de Azure Dev Spaces es la capacidad de crear "espacios" que se pueden ejecutar integrados con el resto de la implementación global en el clúster:

![Diagrama que muestra el uso de varios espacios en Azure Dev Spaces.](./media/orchestrate-high-scalability-availability/use-multiple-spaces-azure-dev.png)

**Figura 4-9**. Uso de varios espacios en Azure Dev Spaces

Azure Dev Spaces puede mezclar y combinar de forma transparente los microservicios de producción con la instancia de contenedor de desarrollo para facilitar las pruebas de nuevas versiones. Básicamente, puede configurar un espacio de desarrollo compartido en Azure. Así, cada programador se puede centrar exclusivamente en su parte de la aplicación y desarrollar de forma iterativa código previo a la confirmación en un espacio de desarrollo que ya contenga todos los demás servicios y recursos en la nube de los que sus escenarios dependen. Las dependencias siempre estarán actualizadas y los desarrolladores trabajarán de una manera que se asemeja bastante a un entorno de producción.

En Azure Dev Spaces existe el concepto de espacio, que permite trabajar de manera aislada y sin riesgo de romper el código de los miembros del equipo. Esta característica se basa en prefijos de dirección URL. Si usa un prefijo de espacio de desarrollo en la dirección URL para la solicitud de un contenedor, Azure Dev Spaces ejecutará una versión especial del contenedor que se implementa para ese espacio, si existe. En caso contrario, se ejecutará la versión global o consolidada.

Para obtener un ejemplo concreto, vea la [página wiki de eShopOnContainers en Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces).

Para obtener más información, vea [Desarrollo en equipo con Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Recursos adicionales

- **Guía de inicio rápido: Implementación de un clúster de Azure Kubernetes Service (AKS)**  \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Azure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes.** Sitio oficial. \
  <https://kubernetes.io/>

## <a name="using-azure-service-fabric"></a>Uso de Azure Service Fabric

Azure Service Fabric surgió de la transición que Microsoft realizó al dejar de ofrecer productos empaquetados, que normalmente tenían un estilo monolítico, para ofrecer servicios. La experiencia de crear y usar servicios de gran tamaño a escala, como Azure SQL Database, Azure Cosmos DB, Azure Service Bus o Backend de Cortana, definió el formato de Service Fabric. La plataforma evolucionó con el tiempo, a medida que la adoptaron cada vez más servicios. Cabe destacar que Service Fabric tuvo que ejecutarse no solo en Azure sino también en implementaciones independientes de Windows Server.

El objetivo de Service Fabric es solucionar los arduos problemas de compilar y ejecutar un servicio y usar recursos de infraestructura de forma eficaz, de manera que los equipos puedan resolver problemas empresariales con un enfoque de microservicios.

Service Fabric proporciona dos áreas generales para ayudarlo a crear aplicaciones que usan un enfoque de microservicios:

- Una plataforma que proporciona servicios de sistema para implementar, escalar, actualizar, detectar y reiniciar servicios erróneos, detectar la ubicación del servicio, administrar el estado y supervisar el mantenimiento. Estos servicios de sistema efectivamente habilitan muchas de las características de microservicios descritas anteriormente.

- Programar API, o marcos, para ayudarlo a crear aplicaciones como microservicios: [actores fiables y servicios de confianza](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Puede elegir cualquier código para generar el microservicio, pero estas API facilitan el trabajo y se integran con la plataforma a un nivel más profundo. De este modo, puede obtener información de mantenimiento y diagnóstico o puede sacar partido de la administración de estado confiable.

Para crear su servicio puede usar cualquier tecnología ya que Service Fabric no interviene en el proceso. Sin embargo, proporciona API de programación integradas que facilitan la creación de microservicios.

Como se muestra en la figura 4-10, puede crear y ejecutar microservicios en Service Fabric como procesos simples o como contenedores de Docker. También es posible mezclar microservicios basados en contenedores con microservicios basados en procesos en el mismo clúster de Service Fabric.

![Diagrama que muestra la comparación de clústeres de Azure Service Fabric.](./media/orchestrate-high-scalability-availability/azure-service-fabric-cluster-types.png)

**Figura 4-10**. Implementar microservicios como procesos o como contenedores en Azure Service Fabric

En la primera imagen, verá microservicios como procesos, donde cada nodo ejecuta un proceso para cada microservicio. En la segunda imagen, verá microservicios como contenedores, donde cada nodo ejecuta Docker con varios contenedores, un contenedor por microservicio. Los clústeres de Service Fabric basados en hosts de Linux y Windows pueden ejecutar contenedores de Docker Linux y Windows, respectivamente.

Para más información actualizada sobre la compatibilidad con contenedores en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric es un buen ejemplo de una plataforma en la que puede definir una arquitectura lógica diferente (microservicios empresariales o contextos limitados) de la implementación física. Por ejemplo, si implementa en [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) los [servicios de confianza con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction), que se describen más adelante en la sección [Microservicios sin estado frente a microservicios con estado](#stateless-versus-stateful-microservices), puede tener un concepto de microservicio empresarial con varios servicios físicos.

Como se muestra en la figura 4-10, y bajo una perspectiva de microservicio lógico o empresarial, al implementar un servicio de confianza con estado de Service Fabric, normalmente deberá implementar dos niveles de servicios. El primero es el servicio de confianza con estado back-end, que administra varias particiones (cada partición es un servicio con estado). El segundo es el servicio front-end, o servicio de puerta de enlace, que se encarga del enrutamiento y de la agregación de datos en varias particiones o instancias de servicio con estado. Este servicio de puerta de enlace también controla la comunicación del lado cliente con los bucles de reintento que acceden al servicio back-end. Se denomina servicio de puerta de enlace si implementa el servicio personalizado, pero alternativamente también puede usar el [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) estándar de Service Fabric.

![Diagrama que muestra varios servicios con estado en contenedores.](./media/orchestrate-high-scalability-availability/service-fabric-stateful-business-microservice.png)

**Figura 4-11**. Microservicio de negocio con varias instancias de servicio con estado y un front-end con puerta de enlace personalizado

En cualquier caso, al usar servicios de confianza con estado de Service Fabric, también dispone de un microservicio lógico o empresarial (contexto limitado) que se compone de varios servicios físicos. Cada uno de ellos, el servicio de puerta de enlace y el servicio de partición podrían implementarse como servicios ASP.NET Web API, como se muestra en la figura 4-11. Service Fabric está recomendado para admitir varios servicios de confianza con estado en contenedores.

En Service Fabric, puede agrupar e implementar grupos de servicios como una [aplicación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), que es la unidad de empaquetado e implementación para el orquestador o clúster. Por tanto, la aplicación de Service Fabric también podría asignarse a este límite de microservicio o contexto limitado lógico y empresarial autónomo, por lo que podría implementar estos servicios de forma autónoma.

### <a name="service-fabric-and-containers"></a>Service Fabric y contenedores

Con respecto a los contenedores de Service Fabric, también puede implementar servicios en las imágenes de contenedor dentro de un clúster de Service Fabric. Como se muestra en la figura 4-12, la mayoría de las veces solo habrá un contenedor por cada servicio.

![Diagrama que muestra un contenedor por servicio que alimenta una base de datos.](./media/orchestrate-high-scalability-availability/azure-service-fabric-business-microservice.png)

**Figura 4-12**. Microservicio empresarial con varios servicios (contenedores) en Service Fabric

Una aplicación de Service Fabric puede ejecutar varios contenedores que acceden a una base de datos externa y el conjunto completo sería el límite lógico de un microservicio empresarial. Pero los contenedores llamados "asociados" (dos contenedores que deben implementarse conjuntamente como parte de un servicio lógico) también son posibles en Service Fabric. Lo importante es que un microservicio empresarial sea el límite lógico alrededor de varios elementos cohesivos. En muchos casos, puede que sea un único servicio con un solo modelo de datos, pero en otros casos también es posible que tenga varios servicios físicos.

Tenga en cuenta que se pueden combinar servicios en procesos y servicios en contenedores en la misma aplicación de Service Fabric, como se muestra en la figura 4-13.

![Diagrama que muestra los servicios en procesos y en contenedores en la misma aplicación.](./media/orchestrate-high-scalability-availability/business-microservice-mapped-to-service-fabric-application.png)

**Figura 4-13**. Microservicio empresarial asignado a una aplicación de Service Fabric con contenedores y servicios con estado

Para más información sobre la compatibilidad de contenedor en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservicios sin estado frente a microservicios con estado

Como se ha mencionado anteriormente, cada microservicio (contexto limitado lógico) debe tener su modelo de dominio (datos y lógica). En el caso de los microservicios sin estado, las bases de datos serán externas y se usarán opciones relacionales, como SQL Server, u opciones de NoSQL, como MongoDB o Azure Cosmos DB.

Pero los propios servicios también pueden ser con estado en Service Fabric, lo que significa que los datos se encuentran en el microservicio. Estos datos pueden existir no solo en el mismo servidor, sino dentro del proceso del microservicio, en memoria, conservados en discos duros y replicados en otros nodos. En la figura 4-14 se muestran los distintos enfoques.

![Diagrama que muestra una comparación de un servicio sin estado y con estado.](./media/orchestrate-high-scalability-availability/stateless-vs-stateful-microservices.png)

**Figura 4-14**. Microservicios sin estado frente a microservicios con estado

En los servicios sin estado, el estado (persistencia, base de datos) se mantiene fuera del microservicio. En los servicios con estado, el estado se mantiene dentro del microservicio. Un enfoque sin estado es perfectamente válido y es más fácil de implementar que los microservicios con estado, ya que el enfoque es similar a los patrones tradicionales y conocidos. Pero los microservicios sin estado imponen latencia entre el proceso y los orígenes de datos. También implican más piezas móviles cuando se intenta mejorar el rendimiento con memoria caché y colas adicionales. El resultado es que puede acabar con arquitecturas complejas que tienen demasiados niveles.

Por el contrario, los [microservicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) pueden destacar en escenarios avanzados, ya que no hay latencia entre los datos y la lógica del dominio. El procesamiento intenso de datos, los back-ends de juegos, las bases de datos como servicio y otros escenarios con baja latencia se benefician de los servicios con estado, que habilitan el estado local para un acceso más rápido.

Los servicios sin estado y los servicios con estado se complementan. Por ejemplo, como puede ver en el diagrama de la derecha en la figura 4-14, un servicio con estado se puede dividir en varias particiones. Para acceder a esas particiones, es posible que deba contar con un servicio sin estado que actúe como un servicio de puerta de enlace que sepa cómo dirigirse a cada partición en función de las claves de partición.

Los servicios con estado tienen diversos inconvenientes. Imponen un alto nivel de complejidad en el escalado horizontal. Las funciones que normalmente se implementarían mediante sistemas de bases de datos externas se debe abordar en tareas como la replicación de datos a través de microservicios con estado y la creación de particiones de datos. Sin embargo, esta es una de las áreas en que un orquestador como [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con sus [servicios de confianza con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede ayudar al máximo, ya que simplifica el desarrollo y el ciclo de vida de los microservicios con estado mediante la [API de Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Otros marcos de microservicio que permiten los servicios con estado, admiten el patrón de actor y mejoran la tolerancia a errores y la latencia entre la lógica y los datos de negocios son Microsoft [Orleans](https://github.com/dotnet/orleans), de Microsoft Research, y [Akka.NET](https://getakka.net/). Actualmente, ambos marcos están mejorando su compatibilidad con Docker.

Recuerde que los contenedores de Docker son sin estado. Si quiere implementar un servicio con estado, debe contar con uno de los marcos prescriptivos y de nivel superior adicionales que se han indicado anteriormente.

## <a name="using-azure-service-fabric-mesh"></a>Uso de Azure Service Fabric Mesh

Azure Service Fabric Mesh es un servicio totalmente administrado que permite a los desarrolladores compilar e implementar aplicaciones críticas sin tener que administrar ninguna infraestructura. Utilice Service Fabric Mesh para compilar y ejecutar aplicaciones de microservicios seguras y distribuidas que se escalan a petición.

Como se muestra en la figura 4-15, las aplicaciones hospedadas en Service Fabric Mesh se ejecutan y escalan sin preocuparse por la infraestructura de la que dependen.

![Diagrama que muestra la implementación de un repositorio local en Service Fabric Mesh.](media/orchestrate-high-scalability-availability/deploy-microservice-containers-apps-service-fabric-mesh.png)

**Figura 4-15**. Implementación de una aplicación de microservicios/contenedores en Service Fabric Mesh

En segundo plano, Service Fabric Mesh consta de clústeres de miles de máquinas. Todas las operaciones de clúster se ocultan a los desarrolladores. Basta con cargar los contenedores y especificar los recursos necesarios, los requisitos de disponibilidad y los límites de recursos. Service Fabric Mesh asigna automáticamente la infraestructura solicitada por la implementación de la aplicación y también controla los errores de infraestructura, asegurándose de que las aplicaciones tienen una alta disponibilidad. Solo necesita preocuparse del estado y de la capacidad de respuesta de la aplicación, nunca de la infraestructura.

Para obtener más información, vea la [documentación de Service Fabric Mesh](https://docs.microsoft.com/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Elección de orquestadores en Azure

En la siguiente tabla se proporcionan instrucciones sobre qué orquestador se debe usar en función de las cargas de trabajo y el foco del sistema operativo.

![Imagen de una tabla que compara Kubernetes y Service Fabric.](media/orchestrate-high-scalability-availability/orchestrator-selection-azure-guidance.png)

**Figura 4-16**. Selección del orquestador en instrucciones de Azure

>[!div class="step-by-step"]
>[Anterior](soa-applications.md)
>[Siguiente](deploy-azure-kubernetes-service.md)
