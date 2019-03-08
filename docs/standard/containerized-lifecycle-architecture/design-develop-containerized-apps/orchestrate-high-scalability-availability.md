---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Las aplicaciones de producción real se tienen que se implementan y administran con orquestadores que controlan el estado, la carga de trabajo y ciclos de vida de todos los contenedores.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: b8c947ffc34b62204b6a370f1133111a3e2d3198
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679052"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad

Con orquestadores para aplicaciones de entornos de producción es fundamental si la aplicación basada en microservicios o dividir entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicios, cada microservicio posee su modelo y sus datos para que sea autónomo desde un punto de vista del desarrollo y la implementación. Pero incluso si tiene una aplicación más tradicional que se compone de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una sola aplicación de negocio que deban implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de administrar y escalar horizontalmente; por lo tanto, un orquestador es indispensable si se quiere tener una aplicación de varios contenedores, escalable y lista para la producción.

Figura 4-6 ilustra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![Aplicaciones compuestas de Docker en un clúster: use un contenedor para cada instancia de servicio. Los contenedores de Docker son "unidades de implementación" y un contenedor es una instancia de un Docker. Un host controla muchos contenedores](./media/image6.png)

**Figura 4-6**. Un clúster de contenedores

Parece un enfoque lógico. Pero, ¿cómo maneja equilibrio de carga, enrutamiento y orquestar estas aplicaciones compuestas?

La interfaz de línea de comandos (CLI) de Docker satisface las necesidades de administración de un contenedor en un host, pero se queda corto en cuanto a administración de varios contenedores implementados en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, se necesita una plataforma de administración que automáticamente inicie contenedores, escalar horizontalmente contenedores con varias instancias por imagen, suspenderlos o apagarlos cuando sea necesario y lo ideal es que también controlan cómo tener acceso a recursos, como la red y datos almacenamiento.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas simple y avance hacia las aplicaciones empresariales más grandes con microservicios, debe desactivar la orquestación y agrupación en clústeres de plataformas.

Desde una arquitectura y desarrollo de punto de vista, si le creación grande, enterprise, basada en microservicios, aplicaciones, es importante comprender las siguientes plataformas y productos que admiten escenarios avanzados:

- **Clústeres y orquestadores**. Cuando necesite escalar horizontalmente las aplicaciones en varios hosts de Docker, como con una aplicación grande basada en microservicios, es fundamental poder administrar todos los hosts como un solo clúster mediante la abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y los orquestadores. Azure Service Fabric y Kubernetes son ejemplos de orquestadores. Kubernetes está disponible en Azure a través de Azure Kubernetes Service.

- **Programadores**. *Programación* significa tener la capacidad para que un administrador inicie los contenedores en un clúster, por lo que los programadores también proporcionan una interfaz de usuario para hacerlo. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, establecer las restricciones definidas por el usuario, equilibrar eficazmente la carga de los contenedores entre los distintos nodos o hosts, ser resistente a los errores y proporcionar un alto grado de disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen ofrecer ambos conjuntos de funciones. La sección siguiente muestra la plataforma más importante y las opciones de software que tiene para clústeres y programadores. Estos orquestadores ampliamente se ofrecen en nubes públicas como Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Plataformas de software para agrupación en clústeres de contenedores, orquestación y programación

| Plataforma | Comentarios |
|:---:|:---|
| **Kubernetes** <br/> ![Logotipo de Kubernetes](./media/kubernetes-logo.png) | [*Kubernetes*](https://kubernetes.io/) es un producto de código abierto cuya funcionalidad abarca desde la infraestructura de clúster y la programación de contenedores a las capacidades de orquestación. Permite automatizar la implementación, la escala y las operaciones de contenedores de aplicaciones en varios clústeres de hosts. <br/> <br/> *Kubernetes* proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección. <br/> <br/> *Kubernetes* está más desarrollado en Linux que en Windows. |
| **Azure Kubernetes Service (AKS)** <br/> ![Logotipo de Azure Kubernetes Service](./media/aks-logo.png) | [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/) es un servicio administrado de orquestación de contenedores de Kubernetes en Azure que simplifica la administración, implementación y operaciones del clúster de Kubernetes. |
| **Azure Service Fabric** <br/> ![Logotipo de Azure Service Fabric](./media/service-fabric-logo.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) es una plataforma de microservicios de Microsoft para crear aplicaciones. Es un [orquestador](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) de servicios y crea clústeres de máquinas. Service Fabric puede implementar servicios como contenedores o procesos estándar. Puede incluso combinar servicios en procesos con servicios en contenedores dentro de la misma aplicación y el mismo clúster. <br/> <br/> Los clústeres de *Service Fabric* pueden implementarse en Azure, de forma local o en cualquier nube. Con todo, la implementación se simplifica en Azure con un enfoque administrado. <br/> <br/> *Service Fabric* proporciona [modelos de programación de Service Fabric](https://azure.microsoft.com/documentation/articles/service-fabric-choose-framework/) prescriptivos adicionales y opcionales como [servicios con estado](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-services-introduction/) y [Reliable Actors](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-actors-introduction/). <br/> <br/> *Service Fabric* está más desarrollado en Windows (con años de evolución en Windows) que en Linux. <br/> <br/> Tanto los contenedores de Linux como los de Windows son compatibles con Service Fabric desde 2017. |
| **Malla de Azure Service Fabric** <br/> ![Logotipo de malla de Azure Service Fabric](./media/azure-service-fabric-mesh-logo.png) | [*Azure Service Fabric malla* ](https://docs.microsoft.com/azure/service-fabric-mesh/service-fabric-mesh-overview) ofrece el mismo nivel de fiabilidad, rendimiento crítico y escala como Service Fabric, pero también ofrece una plataforma totalmente administrada y sin servidor. No es necesario administrar un clúster, las máquinas virtuales, el almacenamiento o la configuración de red. Puede centrarse en el desarrollo de la aplicación. <br/> <br/> *Service Fabric malla* admite contenedores de Windows y Linux, lo que le permite desarrollar con cualquier lenguaje de programación y el marco de trabajo de su elección.

## <a name="using-container-based-orchestrators-in-azure"></a>Uso de orquestadores de contenedor en Azure

Varios proveedores de nube ofrecen compatibilidad con contenedores de Docker y clústeres de Docker y compatibilidad con la orquestación, incluidos Azure, Amazon EC2 Container Service y Google Container Engine. Azure proporciona compatibilidad con orquestador y clúster a través de Azure Kubernetes Service (AKS), Azure Service Fabric y Azure Service Fabric malla de Docker.

## <a name="using-azure-kubernetes-service"></a>Uso de Azure Kubernetes Service

Un clúster de Kubernetes de grupos de varios hosts de Docker y los expone como un único host virtual de Docker, por lo que puede implementar varios contenedores en el clúster y la escalabilidad horizontal con cualquier número de instancias de contenedor. El clúster controlará toda la mecánica de administración compleja, como la escalabilidad, el estado, etc.

AKS proporciona una manera de simplificar la creación, la configuración y la administración de un clúster de máquinas virtuales en Azure que están preconfiguradas para ejecutar aplicaciones en contenedores. Al utilizar una configuración optimizada de herramientas de orquestación y programación de código abierto populares, AKS le permite usar sus habilidades existentes o aprovechar un gran corpus creciente de conocimientos de la comunidad para implementar y administrar aplicaciones basadas en contenedor en Microsoft Azure.

Azure Kubernetes Service optimiza la configuración de tecnologías y herramientas populares de código abierto de agrupación en clústeres de Docker específicamente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador, y AKS se encarga de todo lo demás.

![Estructura de un clúster de Kubernetes: hay un nodo maestro que controla el DNS, el programador, el proxy, etc., y varios nodos de trabajo, que hospedan los contenedores.](media/image36.png)

**Figura 4-7**. Topología y estructura simplificada del clúster de Kubernetes

Figura 4-7 muestra la estructura de un clúster de Kubernetes, donde un nodo maestro (VM) controla la mayor parte de la coordinación del clúster y puede implementar contenedores en el resto de los nodos que se administran como un único grupo desde un punto de vista de la aplicación. Esto le permite escalar hasta miles o incluso a decenas de miles de contenedores.

## <a name="development-environment-for-kubernetes"></a>Entorno de desarrollo para Kubernetes

En el entorno de desarrollo que [Docker anunciada en julio de 2018](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/), Kubernetes también puede ejecutar en un único equipo de desarrollo (Windows 10 o macOS) mediante la instalación de simplemente [Docker Desktop](https://www.docker.com/community-edition). Puede implementar posteriormente en la nube (AKS) para obtener más pruebas de integración, como se muestra en la figura 4-8.

![En julio de 2018, Docker anunció asistencia del equipo de desarrollo para los clústeres de Kubernetes con Docker Desktop.](media/kubernetes-development-environment.png)

**Figura 4-8**. Ejecución de Kubernetes en el equipo de desarrollo y la nube

## <a name="get-started-with-azure-kubernetes-service-aks"></a>Empezar a trabajar con Azure Kubernetes Service (AKS)

Para empezar a usar AKS, implemente un clúster de AKS desde Azure portal o mediante la CLI. Para obtener más información sobre la implementación de un clúster de Azure Container Service, vea [Guía de inicio rápido: Implementación de un clúster de Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

No hay cuotas para el software instalado de forma predeterminada como parte de AKS. Todas las opciones predeterminadas se implementan con el software de código abierto. AKS está disponible en varias máquinas virtuales en Azure. Se cobra únicamente por las instancias de proceso que se elijan, así como por los otros recursos subyacentes de la infraestructura que se utilicen como, por ejemplo, la red y el almacenamiento. No hay ningún cargo incremental para AKS.

Para la implementación adicional según la información sobre la implementación en Kubernetes `kubectl` y originales `.yaml` archivos, vea la entrada en [configurar eShopOnContainers en AKS (Azure Kubernetes Service)](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.-Setting-the-solution-up-in-AKS-(Azure-Kubernetes-Service)).

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Implementar con gráficos de Helm en clústeres de Kubernetes

Al implementar una aplicación en un clúster de Kubernetes, puede utilizar el original `kubectl.exe` herramienta CLI mediante archivos de implementación basada en el formato nativo (`.yaml` archivos), como ya se mencionó en la sección anterior. Pero, para aplicaciones de Kubernetes más complejas, como al implementar aplicaciones complejas basadas en microservicios, se recomienda usar [Helm](https://helm.sh/).

Gráficos de helm le ayuda a definir, versión, la instalación, recurso compartido, actualización o reversión incluso la aplicación más compleja de Kubernetes.

Adicionalmente, el uso de Helm se recomienda porque otros entornos de Kubernetes en Azure, como [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces), también se basan en los gráficos de Helm.

Helm es mantenida por el [Foundation de informática nativo en la nube (CNCF)](https://www.cncf.io/) en colaboración con Microsoft, Google, Bitnami y la Comunidad de colaborador de Helm.

Para obtener más información de implementación en los gráficos de Helm y Kubernetes, vea la entrada en [usando gráficos de Helm para implementar eShopOnContainers en AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Deploying-to-AKS-using-Helm-Charts).

## <a name="use-azure-dev-spaces-for-you-kubernetes-application-lifecycle"></a>Usar espacios de desarrollo de Azure automáticamente el ciclo de vida de aplicaciones de Kubernetes

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) proporciona una experiencia de desarrollo de Kubernetes rápida e iterativa para los equipos. Con una configuración de máquina de desarrollo mínima, puede ejecutar y depurar contenedores de forma iterativa directamente en Azure Kubernetes Service (AKS). Puede desarrollar en Windows, Mac o Linux mediante herramientas familiares como Visual Studio, Visual Studio Code o la línea de comandos.

Como se mencionó, espacios de desarrollo de Azure utiliza los gráficos de Helm al implementar aplicaciones basadas en contenedores.

Espacios de desarrollo de Azure ayuda a los equipos de desarrollo ser más productivo en Kubernetes porque permite iterar rápidamente y depure código directamente en un clúster de Kubernetes global en Azure si solo se usa Visual Studio 2017 o Visual Studio Code. Ese clúster de Kubernetes en Azure es un clúster de Kubernetes administrado compartido, por lo que su equipo puede colaborar. Puede desarrollar código de forma aislada, después implementarlo en el clúster global y realizar pruebas de un extremo a otro con otros componentes sin tener que replicar ni simular dependencias.

Como se muestra en la figura 4-9, la característica más diferenciador de espacios de desarrollo de Azure es la capacidad de crear espacios' ' que se pueden ejecutar integrados al resto de la implementación global en el clúster.

![Azure Dev Spaces puede mezclar y combinar de forma transparente los microservicios de producción con la instancia de contenedor de desarrollo para facilitar las pruebas de nuevas versiones.](media/image38.png)

**Figura 4-9**. Uso de varios espacios en Azure Dev Spaces

Básicamente, puede configurar un espacio de desarrollo compartido en Azure. Cada desarrollador puede centrarse exclusivamente en su parte de la aplicación y forma iterativa puede desarrollar código "previamente confirmado" en un espacio de desarrollo que ya contiene todos los demás servicios y recursos que dependen de sus escenarios de la nube. Las dependencias siempre estarán actualizadas y los desarrolladores trabajarán de una manera que se asemeja bastante a un entorno de producción.

Espacios de desarrollo de Azure ofrece el concepto de un espacio, lo que le permite trabajar de forma aislada y sin el riesgo de romper a los miembros del equipo. Esta característica se basa en los prefijos de URL; Si usa un prefijo de espacio de desarrollo en la dirección URL de solicitud de un contenedor, espacios de desarrollo de Azure se ejecuta una versión especial del contenedor que implementa para ese espacio, si existe alguno. En caso contrario, se ejecutará la versión global o consolidada.

Puede ver el [página wiki de eShopOnContainers en espacios de desarrollo de Azure](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.2-Using-Azure-Dev-Spaces-and-AKS) para obtener una vista práctica en un ejemplo concreto.

Para obtener más información, consulte el artículo sobre [desarrollo en equipo con espacios de desarrollo de Azure](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Recursos adicionales

- **Guía de inicio rápido: Implementación de un clúster de Azure Kubernetes Service (AKS)** \
  [*https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal*](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)

- **Azure Dev Spaces** \
  [*https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces*](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces)

- **Kubernetes.** Sitio oficial. \
  [*https://kubernetes.io/*](https://kubernetes.io/)

## <a name="using-azure-service-fabric"></a>Uso de Azure Service Fabric

Azure Service Fabric surgió de transición de Microsoft de ofrecer productos de "caja", que eran habitualmente monolíticos en estilos, para ofrecer servicios. La experiencia de crear y operar servicios grandes a escala, como Azure SQL Database, Azure Cosmos DB, Azure Service Bus o Backend de Cortana, en forma de Service Fabric. La plataforma evolucionó con el tiempo, a medida que la adoptaron cada vez más servicios. Cabe destacar que Service Fabric tuvo que ejecutarse no solo en Azure sino también en implementaciones independientes de Windows Server.

El objetivo de Service Fabric es solucionar los arduos problemas de compilar y ejecutar un servicio y usar recursos de infraestructura de forma eficaz, de manera que los equipos puedan resolver problemas empresariales con un enfoque de microservicios.

Service Fabric proporciona dos áreas generales para ayudarlo a crear aplicaciones que usan un enfoque de microservicios:

- Una plataforma que proporciona servicios de sistema para implementar, escalar, actualizar, detectar y reiniciar servicios erróneos, detectar la ubicación del servicio, administrar el estado y supervisar el mantenimiento. Estos servicios de sistema efectivamente habilitan muchas de las características de microservicios descritas anteriormente.

- Programar API, o marcos, para ayudarlo a crear aplicaciones como microservicios: [actores fiables y servicios de confianza](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Puede elegir cualquier código para generar el microservicio, pero estas API facilitan el trabajo y se integran con la plataforma a un nivel más profundo. De este modo, puede obtener información de mantenimiento y diagnóstico o puede sacar partido de la administración de estado confiable.

Para crear su servicio puede usar cualquier tecnología ya que Service Fabric no interviene en el proceso. Sin embargo, proporciona API de programación integradas que facilitan la creación de microservicios.

Como se muestra en la figura 4-10, puede crear y ejecutar microservicios en Service Fabric como procesos simples o como contenedores de Docker. También es posible mezclar microservicios basados en contenedores con microservicios basados en procesos en el mismo clúster de Service Fabric.

![Comparación de Azure service Fabric clústeres: Microservicios como procesos, donde cada nodo ejecuta un proceso para cada microservicio; Microservicios como contenedores donde cada nodo ejecuta Docker con varios contenedores, un contenedor por microservicio.](./media/azure-service-fabric-cluster-types.png)

**Figura 4-10**. Implementar microservicios como procesos o como contenedores en Azure Service Fabric

Los clústeres de Service Fabric basados en hosts de Linux y Windows pueden ejecutar contenedores de Docker Linux y Windows, respectivamente.

Para más información actualizada sobre la compatibilidad con contenedores en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric es un buen ejemplo de una plataforma donde podrá definir una arquitectura lógica diferente (microservicios empresariales o contextos delimitados) de la implementación física. Por ejemplo, si implementa [Reliable Services con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) en [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), que se describen en la sección siguiente, "[sin estado frente a microservicios con estado](#stateless-versus-stateful-microservices), "tiene un concepto de microservicio empresarial con varios servicios físicos.

Como se muestra en la figura 4-10 y pensar desde una perspectiva de microservicio lógico/empresarial, al implementar un servicio de Service Fabric con estado confiable, normalmente deberá implementar dos niveles de servicios. El primero es el servicio de confianza con estado back-end, que administra varias particiones (cada partición es un servicio con estado). El segundo es el servicio front-end, o servicio de puerta de enlace, que se encarga del enrutamiento y de la agregación de datos en varias particiones o instancias de servicio con estado. Este servicio de puerta de enlace también controla la comunicación del lado cliente con los bucles de reintento que acceden al servicio back-end. Se denomina servicio de puerta de enlace si implementa el servicio personalizado, pero alternativamente también puede usar el [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) estándar de Service Fabric.

![Service Fabric tiene la receta para admitir varios servicios confiables con estado en contenedores.](./media/service-fabric-stateful-business-microservice.png)

**Figura 4-11**. Microservicio empresarial con varias instancias de servicio con estado y un front-end de puerta de enlace personalizada

En cualquier caso, cuando se usa Service Fabric Stateful Reliable Services, también tiene un microservicio lógico o empresarial (contexto limitado) que se compone de varios servicios físicos. Cada uno de ellos, el servicio de puerta de enlace y el servicio de partición podría implementarse como servicios de ASP.NET Web API, tal como se muestra en la figura 4-11.

En Service Fabric, puede agrupar e implementar grupos de servicios como una [aplicación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), que es la unidad de empaquetado e implementación para el orquestador o clúster. Por tanto, la aplicación de Service Fabric también podría asignarse a este límite de microservicio o contexto limitado lógico y empresarial autónomo, por lo que podría implementar estos servicios de forma autónoma.

### <a name="service-fabric-and-containers"></a>Service Fabric y contenedores

Con respecto a los contenedores de Service Fabric, también puede implementar servicios en las imágenes de contenedor dentro de un clúster de Service Fabric. Como se muestra en la figura 4-12, la mayoría de los casos sólo habrá un contenedor por cada servicio.

![Una aplicación de Service Fabric puede ejecutar varios contenedores, obtener acceso a una base de datos externo y el conjunto completo sería el límite lógico de un Microservicio de negocio](./media/azure-service-fabric-business-microservice.png)

**Figura 4-12**. Microservicio empresarial con varios servicios (contenedores) en Service Fabric

Pero los contenedores llamados "asociados" (dos contenedores que deben implementarse conjuntamente como parte de un servicio lógico) también son posibles en Service Fabric. Lo importante es que un microservicio empresarial sea el límite lógico alrededor de varios elementos cohesivos. En muchos casos, puede que sea un único servicio con un solo modelo de datos, pero en otros casos también es posible que tenga varios servicios físicos.

Tenga en cuenta que puede mezclar servicios en procesos y servicios en contenedores, en la misma aplicación de Service Fabric, como se muestra en la figura 4-13.

![Una aplicación de service fabric ejecuta los servicios y contenedores en el mismo nodo.](./media/business-microservice-mapped-to-service-fabric-application.png)

**Figura 4-13**. Microservicio empresarial asignado a una aplicación de Service Fabric con contenedores y servicios con estado

Para más información sobre la compatibilidad de contenedor en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservicios sin estado frente a microservicios con estado

Como se ha mencionado anteriormente, cada microservicio (contexto limitado lógico) debe tener su modelo de dominio (datos y lógica). En el caso de los microservicios sin estado, las bases de datos serán externas y se usarán opciones relacionales, como SQL Server, u opciones de NoSQL, como MongoDB o Azure Cosmos DB.

Pero los propios servicios también pueden ser con estado en Service Fabric, lo que significa que los datos se encuentran en el microservicio. Estos datos pueden existir no solo en el mismo servidor, sino dentro del proceso del microservicio, en memoria, conservados en discos duros y replicados en otros nodos. En la figura 4-30 se muestran los distintos enfoques.

![En los servicios sin estado se mantiene el estado (persistencia, base de datos) fuera del microservicio. En los servicios con estado se mantiene el estado dentro del microservicio.](./media/stateless-vs-stateful-microservices.png)

**Figura 4-14**. Microservicios sin estado frente a microservicios con estado

Un enfoque sin estado es perfectamente válido y es más fácil de implementar que los microservicios con estado, ya que el enfoque es similar a los patrones tradicionales y conocidos. Pero los microservicios sin estado imponen latencia entre el proceso y los orígenes de datos. También implican más piezas móviles cuando se intenta mejorar el rendimiento con memoria caché y colas adicionales. El resultado es que puede acabar con arquitecturas complejas que tienen demasiados niveles.

Por el contrario, los [microservicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) pueden destacar en escenarios avanzados, ya que no hay latencia entre los datos y la lógica del dominio. El procesamiento intenso de datos, los back-ends de juegos, las bases de datos como servicio y otros escenarios con baja latencia se benefician de los servicios con estado, que habilitan el estado local para un acceso más rápido.

Los servicios sin estado y los servicios con estado se complementan. Por ejemplo, como puede ver en el diagrama de la derecha en la figura 4-31, un servicio con estado se puede dividir en varias particiones. Para acceder a esas particiones, es posible que deba contar con un servicio sin estado que actúe como un servicio de puerta de enlace que sepa cómo dirigirse a cada partición en función de las claves de partición.

Los servicios con estado tienen diversos inconvenientes. Imponen un nivel de gran complejidad para escalarse horizontalmente. Las funciones que normalmente se implementarían mediante sistemas de bases de datos externas se debe abordar en tareas como la replicación de datos a través de microservicios con estado y la creación de particiones de datos. Sin embargo, esta es una de las áreas en que un orquestador como [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con sus [servicios de confianza con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede ayudar al máximo, ya que simplifica el desarrollo y el ciclo de vida de los microservicios con estado mediante la [API de Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Otros marcos de microservicio que permiten los servicios con estado, que admiten el patrón de actor y que mejoran la tolerancia a errores y la latencia entre la lógica y los datos empresariales son Microsoft [Orleans](https://github.com/dotnet/orleans), de Microsoft Research, y [ Akka.NET](https://getakka.net/). Actualmente, ambos marcos están mejorando su compatibilidad con Docker.

Recuerde que los contenedores de Docker son sin estado. Si quiere implementar un servicio con estado, debe contar con uno de los marcos prescriptivos y de nivel superior adicionales que se han indicado anteriormente.

## <a name="using-azure-service-fabric-mesh"></a>Uso de Azure Service Fabric Mesh

Malla de Azure Service Fabric es un servicio totalmente administrado que permite a los desarrolladores compilar e implementar aplicaciones de misión crítica sin tener que administrar ninguna infraestructura. Utilice Service Fabric Mesh para compilar y ejecutar aplicaciones de microservicios seguras y distribuidas que se escalan a petición.

Como se muestra en la figura 4-15, las aplicaciones hospedadas en la malla de Service Fabric, ejecutar y escalar sin preocuparse por la infraestructura enciéndala.

![Una aplicación de varios contenedores que se ejecutan en el escritorio de Docker puede implementarse en malla de Azure Service Fabric sin preocuparse sobre la infraestructura.](media/image39.png)

**Figura 4-15**. Implementación de una aplicación de microservicios/contenedores en Service Fabric Mesh

En segundo plano, Service Fabric Mesh consta de clústeres de miles de máquinas. Todas las operaciones de clúster se ocultan a los desarrolladores. Basta con cargar los contenedores y especificar los recursos necesarios, los requisitos de disponibilidad y los límites de recursos. Service Fabric Mesh asigna automáticamente la infraestructura solicitada por la implementación de la aplicación y también controla los errores de infraestructura, asegurándose de que las aplicaciones tienen una alta disponibilidad. Solo necesita preocuparse del estado y de la capacidad de respuesta de la aplicación, nunca de la infraestructura.

Para obtener más información, consulte el [documentación de Service Fabric malla](https://docs.microsoft.com/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Elección de orquestadores en Azure

En la siguiente tabla se proporcionan instrucciones sobre qué orquestador se debe usar en función de las cargas de trabajo y el foco del sistema operativo.

![Servicios de Kubernetes de Azure es más maduro en Linux que en Windows y se usa principalmente para la implementación de microservicios que se basa en contenedores. Azure Service Fabric (tanto la versión de clústeres como Mesh) está más desarrollado en Windows que en Linux, se utiliza normalmente para microservicios basados en contenedores, microservicios basados en procesos sin formato y servicios con estado.](media/image40.png)

**Figura 4-16**. Selección del orquestador en instrucciones de Azure

>[!div class="step-by-step"]
>[Anterior](soa-applications.md)
>[Siguiente](deploy-azure-kubernetes-service.md)
