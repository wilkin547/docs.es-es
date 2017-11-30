---
title: "Orquestar microservicios y aplicaciones de contenedor múltiples de alta escalabilidad y disponibilidad"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Orquestar microservicios y aplicaciones de contenedor múltiples de alta escalabilidad y disponibilidad"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orquestar microservicios y aplicaciones de contenedor múltiples de alta escalabilidad y disponibilidad

Usar orchestrators para las aplicaciones para entornos de producción es fundamental si la aplicación se basa en microservicios o simplemente se dividen entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicio, cada microservicio posee su modelo y sus datos para que sea autónomo desde un desarrollo y el punto de vista de implementación. Pero incluso si tiene una aplicación más tradicional que se compone de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una aplicación de negocio individual que deben implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de escalar y administrar; por lo tanto, sea absolutamente necesario organizador si desea tener una aplicación de contenedor múltiples para entornos de producción y escalable.

Figura 4-23 ilustra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![](./media/image23.PNG)

**Figura 4-23**. Un clúster de contenedores

Parece que un enfoque lógico. Pero, ¿cómo está equilibrio de carga de control, enrutamiento y orquestar estos compuesto por las aplicaciones?

El motor de Docker sin formato en el host Docker único satisfaga las necesidades de administración de instancias de la imagen en un host, pero no cumple las expectativas en cuanto a la administración de varios contenedores de implementada en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, se necesita una plataforma de administración que automáticamente inicie contenedores, contenedores de escalabilidad horizontal con varias instancias por imagen, suspenderá ellos o apagarlos cuando sea necesario y lo ideal es que también controlan cómo tener acceso a recursos como la red y los datos almacenamiento de información.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas muy simples y mover hacia las aplicaciones empresariales más grandes con microservicios, debe desactivar la orquestación y plataformas de agrupación en clústeres.

Desde una arquitectura y desarrollo de punto de vista, si está generando grandes empresas formada por las aplicaciones basadas en microservicios, es importante comprender las siguientes plataformas y productos que admiten escenarios avanzados:

**Clústeres y orchestrators**. Cuando necesite escalar las aplicaciones a través de varios hosts de Docker, como cuando una aplicación basada en microservicio grande, es fundamental para poder administrar todos los hosts como un solo clúster mediante la abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y orchestrators. Ejemplos de orchestrators son Azure Service Fabric, Kubernetes, Docker Swarm y Mesosphere DC/OS. Las tres últimas orchestrators de código abierto están disponibles en Azure a través del servicio de contenedor de Azure.

**Los programadores**. *Programación* significa tener la capacidad para que un administrador iniciar contenedores en un clúster, lo que también proporciona una interfaz de usuario. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, para establecer las restricciones proporcionadas por el usuario, a los contenedores de equilibrar la carga eficazmente entre nodos o hosts y para ser robustas frente a errores al proporcionar alto disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen proporcionan ambos conjuntos de funciones. En la lista siguiente muestra la plataforma más importante y opciones de software que tiene para clústeres y programadores. Estos orchestrators generalmente se ofrecen en nubes públicas como Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Plataformas de software para el contenedor de agrupación en clústeres, la orquestación y la programación

Kubernetes

![https://PBS.twimg.com/Media/BT\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes es un producto de código abierto que proporciona la funcionalidad que varía entre la infraestructura de clúster y el contenedor de programación a las capacidades de organización. Le permite automatizar la implementación, la escala y las operaciones de contenedores de aplicaciones a través de clústeres de hosts.
>
> Kubernetes proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección.
>
> Kubernetes es maduro en Linux, menos maduro en Windows.

Conjunto de docker

![http://rancher.com/wp-content/Themes/rancher-2016/Assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> Conjunto de docker permite agrupar y programar contenedores de Docker. Mediante el uso conjunto, puede convertir un grupo de hosts de Docker en un único host virtual de Docker. Los clientes pueden realizar las solicitudes de API a Microsoft se reúnen en la misma manera que lo hacen a los hosts, lo que significa que conjunto facilita el proceso para las aplicaciones escalar a varios hosts.
>
> Conjunto de docker es un producto de la empresa Docker.
>
> Docker v1.12 o posterior puede ejecutar modo Swarm nativo e integradas.

Mesosphere DC/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-Styled.png](./media/image26.png)

> Mesosphere Enterprise DC/OS (según Apache Mesos) es una plataforma de para entornos de producción para ejecutar contenedores y las aplicaciones distribuidas.
>
> Controlador de dominio/OS funciona mediante la abstracción de una colección de los recursos disponibles en el clúster y poner dichos recursos a disposición de los componentes creados sobre él. Maratón normalmente se utiliza como un programador integrado con un controlador de dominio o sistema operativo.
>
> Controlador de dominio/OS es maduro en Linux, menos maduro en Windows.

Azure Service Fabric.

![https://Azure.Microsoft.com/svghandler/Service-fabric?Width=600&Height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) es una plataforma de microservicios de Microsoft para crear aplicaciones. Es un [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) de servicios y crea clústeres de máquinas. Tejido de servicio puede implementar servicios como contenedores o procesos sin formato. Puede incluso servicios de combinación en procesos con los servicios en contenedores dentro de la misma aplicación y el clúster.
>
> Service Fabric proporciona adicionales y opcionales preceptiva [modelos de programación de Service Fabric ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) como [servicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).
>
> Service Fabric es maduro en Windows (años evolucionando en Windows), menos maduro en Linux. 
> Contenedores de Linux y Windows son compatibles con Service Fabric desde 2017.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Uso de orchestrators basada en el contenedor en Microsoft Azure

Varios proveedores de nube que ofrecen compatibilidad con contenedores de Docker más clústeres de Docker y soporte técnico de orquestación, incluido Microsoft Azure, servicio de contenedor de Amazon EC2 y motor de contenedor de Google. Microsoft Azure proporciona a Docker soporte de clúster y orchestrator mediante el servicio de contenedor de Azure (ACS), como se explica en la sección siguiente.

Otra opción consiste en utilizar a Microsoft Azure Service Fabric (una plataforma de microservicios), que también es compatible con Docker en función de los contenedores de Windows y Linux. Tejido de servicio se ejecuta en Azure o cualquier otra en la nube y también se ejecuta [local](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Usar servicio de contenedor de Azure

Un clúster de Docker de grupos de varios hosts de Docker y los expone como un único host virtual de Docker, que se pueden implementar varios contenedores en el clúster. El clúster controlará todas la mecánica de administración complejas, como la escalabilidad, estado y así sucesivamente. Figura 4-24 representa cómo se asigna un clúster de Docker para aplicaciones compuestos para el servicio de contenedor de Azure (ACS).

ACS proporciona una manera de simplificar la creación, configuración y administración de un clúster de máquinas virtuales que están preconfigurados para ejecutar aplicaciones en contenedores. Utilizar una configuración optimizada de herramientas de programación y la orquestación de código abierto populares, ACS le permite utilizar sus conocimientos existentes o dibujar en un cuerpo elevado y creciente de especialización de la Comunidad para implementar y administrar aplicaciones basadas en el contenedor en Microsoft Azure .

Servicio de contenedor de Azure optimiza la configuración de populares tecnologías y herramientas de código abierto de agrupación en clústeres de Docker específicamente para Azure. Obtener una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orchestrator y servicio de contenedor controla todo lo demás.

![](./media/image28.png)

**Figura 4-24**. Opciones de agrupación en clústeres en el servicio de contenedor de Azure

ACS usa imágenes de Docker para asegurarse de que los contenedores de la aplicación sean totalmente portables. Es compatible con la elección de plataformas de orquestación de código abierto como controlador de dominio/OS (con tecnología de Apache Mesos), Kubernetes (el cual se creó originalmente por Google) y Docker Swarm, para asegurarse de que estas aplicaciones se pueden escalar hasta miles o incluso decenas de miles de contenedores.

El servicio de contenedor de Azure permite sacar provecho de las características de nivel empresarial de Azure manteniendo la portabilidad de aplicación, incluidos en las capas de la orquestación.

![](./media/image29.png)

**Figura 4-25**. Orchestrators en ACS

Como se muestra en la figura 4-25, servicio de contenedor de Azure es simplemente la infraestructura proporcionada por Azure para implementar el controlador de dominio/OS, Kubernetes o Docker Swarm, pero ACS implementar cualquier orchestrator adicional. Por lo tanto, ACS no es un orchestrator por lo tanto, solo una infraestructura que aprovecha existentes orchestrators de código abierto para contenedores.

Desde una perspectiva de uso, el objetivo del servicio de contenedor de Azure es proporcionar un entorno de hospedaje de contenedor mediante el uso de tecnologías y herramientas de código abierto populares. Para ello, expone los extremos de API estándar para su orchestrator elegido. Mediante el uso de estos puntos de conexión, puede aprovechar cualquier software que puede comunicarse con los puntos de conexión. Por ejemplo, en el caso extremo de Docker Swarm, puede utilizar la interfaz de línea de comandos de Docker (CLI). Para el controlador de dominio/OS, puede utilizar la CLI de DC/OS.

### <a name="getting-started-with-azure-container-service"></a>Introducción a servicio de contenedor de Azure 

Para empezar a usar el servicio de contenedor de Azure, implementar un clúster de servicio de contenedor de Azure desde el portal de Azure mediante una plantilla de Azure Resource Manager o la [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Las plantillas disponibles incluyen [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), y [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Las plantillas de inicio rápido se pueden modificar para incluir la configuración de Azure adicional o avanzado. Para obtener más información sobre la implementación de un clúster de servicio de contenedor de Azure, consulte [implementar un clúster de servicio de contenedor de Azure](https://docs.microsoft.com/azure/container-service/container-service-deployment) en el sitio Web de Azure.

No hay ningún cuotas para el software instalado de forma predeterminada como parte de ACS. Todas las opciones predeterminadas se implementan con el software de código abierto.

ACS está actualmente disponible para la serie A estándar, D, DS, G y GS máquinas virtuales de Linux en Azure. Se le cobra solo para las instancias de proceso que elija, así como los otros subyacente recursos de infraestructura utilizados, por ejemplo, red y almacenamiento. No hay ningún cargo incremental para ACS propio.

## <a name="additional-resources"></a>Recursos adicionales

-   **Introducción a soluciones con el servicio de contenedor de Azure de alojamiento de contenedor de Docker**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Información general sobre el conjunto de docker**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Información general de modo se reúnen en**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Información general de DC/OS mesosphere**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes.** El sitio oficial. \
    [*http://kubernetes.IO/*](http://kubernetes.io/)


>[!div class="step-by-step"]
[Anterior] (resistente-alta-disponibilidad-microservices.md) [siguiente] (utilizando-azure-service-fabric.md)
