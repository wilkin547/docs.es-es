---
title: Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: aab939af29849ceeef76d6f61b3d4f59d701094c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105467"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad

La utilización de orquestadores para aplicaciones listas para producción es fundamental si la aplicación se basa en microservicios o simplemente está dividida entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicios, cada microservicio posee su modelo y sus datos para que sea autónomo desde un punto de vista del desarrollo y la implementación. Pero incluso si tiene una aplicación más tradicional que se compone de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una sola aplicación de negocio que deben implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de administrar y escalar horizontalmente; por lo tanto, un orquestador es indispensable si se quiere tener una aplicación de varios contenedores, escalable y lista para la producción.

La figura 4-23 ilustra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![](./media/image23.PNG)

**Figura 4-23**. Un clúster de contenedores

Parece un enfoque lógico. Pero, ¿cómo se está administrando el equilibrio de carga de control, el enrutamiento y la orquestación de estas aplicaciones compuestas?

El motor de Docker estándar en hosts de Docker único satisface las necesidades de administración de instancias de imagen únicas en un host, pero se queda corto a la hora de administrar varios contenedores implementados en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, se necesita una plataforma de administración que automáticamente inicie contenedores, escale horizontalmente contenedores con varias instancias por imagen, los suspenda o los cierre cuando sea necesario y, a ser posible, también controle su acceso a recursos como la red y el almacenamiento de datos.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas muy simples y pasar a aplicaciones empresariales más grandes con microservicios, debe cambiar a orquestación y plataformas de agrupación en clústeres.

Desde el punto de vista de la arquitectura y el desarrollo, si está compilando grandes aplicaciones empresariales basadas en microservicios, es importante familiarizarse con las siguientes plataformas y productos que admiten escenarios avanzados:

**Clústeres y orquestadores**. Cuando se necesita escalar horizontalmente las aplicaciones a varios hosts de Docker, como con una aplicación grande basada en microservicios, es fundamental poder administrar todos los hosts como un solo clúster mediante la abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y los orquestadores. Algunos ejemplos de orquestadores son Azure Service Fabric, Kubernetes, Docker Swarm y Mesosphere DC/OS. Los tres últimos orquestadores de código abierto están disponibles en Azure a través de Azure Container Service.

**Programadores**. *Programar* significa tener la capacidad de que un administrador inicie los contenedores de un clúster, y de proporcionar también una interfaz de usuario. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, establecer las restricciones definidas por el usuario, equilibrar eficazmente la carga de los contenedores entre los distintos nodos o hosts, ser resistente a los errores y proporcionar un alto grado de disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen ofrecer ambos conjuntos de funciones. En la lista siguiente se muestran las plataformas y las opciones de software más importantes disponibles para clústeres y programadores. Estos orquestadores generalmente se ofrecen en nubes públicas como Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Plataformas de software para agrupación en clústeres de contenedores, orquestación y programación

Kubernetes

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes es un producto de código abierto cuya funcionalidad abarca desde la infraestructura de clúster y la programación de contenedores a las capacidades de orquestación. Permite automatizar la implementación, la escala y las operaciones de contenedores de aplicaciones en varios clústeres de hosts.
>
> Kubernetes proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección.
>
> Kubernetes está más desarrollado en Linux que en Windows.

Docker Swarm

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> Docker Swarm permite agrupar y programar contenedores de Docker. Con Swarm se puede convertir un grupo de hosts de Docker en un único host virtual de Docker. Los clientes pueden realizar las solicitudes de API a Microsoft de la misma manera que a los hosts, lo que significa que Swarm facilita el escalado de las aplicaciones a varios hosts.
>
> Docker Swarm es un producto de la empresa Docker.
>
> Docker v1.12 o posterior puede ejecutar el modo nativo e integrado de Swarm.

Mesosphere DC/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> Mesosphere Enterprise DC/OS (basado en Apache Mesos) es una plataforma para entornos de producción que permite ejecutar contenedores y aplicaciones distribuidas.
>
> DC/OS funciona mediante la abstracción de una colección de los recursos disponibles en el clúster y poniendo dichos recursos a disposición de los componentes creados sobre él. Marathon suele utilizarse como un programador integrado con DC/OS.
>
> DC/OS está más desarrollado en Linux que en Windows.

Azure Service Fabric

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) es una plataforma de microservicios de Microsoft para crear aplicaciones. Es un [orquestador](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) de servicios y crea clústeres de máquinas. Service Fabric puede implementar servicios como contenedores o procesos estándar. Puede incluso combinar servicios en procesos con servicios en contenedores dentro de la misma aplicación y el mismo clúster.
>
> Service Fabric proporciona [modelos de programación de Service Fabric ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) prescriptivos adicionales y opcionales como [servicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).
>
> Service Fabric está más desarrollado en Windows (con años de evolución en Windows) que en Linux. 
> Tanto los contenedores de Linux como los de Windows son compatibles con Service Fabric desde 2017.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Uso de orquestadores basados en contenedor en Microsoft Azure

Existen varios proveedores de nube que ofrecen compatibilidad con contenedores de Docker más compatibilidad con la orquestación y los clústeres de Docker, como Microsoft Azure, Amazon EC2 Container Service y Google Container Engine. Microsoft Azure proporciona compatibilidad con orquestador y clúster de Docker mediante el servicio Azure Container Service (ACS), como se explica en la sección siguiente.

Otra opción consiste en utilizar Microsoft Azure Service Fabric (una plataforma de microservicios), que también es compatible con Docker basado en contenedores de Windows y Linux. Service Fabric se ejecuta en Azure o en cualquier otra nube y también [localmente](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso de Azure Container Service

Un clúster de Docker agrupa varios hosts de Docker y los expone como un único host virtual de Docker, lo que permite implementar varios contenedores en el clúster. El clúster controlará toda la mecánica de administración compleja, como la escalabilidad, el estado, etc. La figura 4-24 representa cómo se asigna un clúster de Docker para aplicaciones compuestas a Azure Container Service (ACS).

ACS proporciona una manera de simplificar la creación, la configuración y la administración de un clúster de máquinas virtuales que están preconfiguradas para ejecutar aplicaciones en contenedores. Al utilizar una configuración optimizada de herramientas de orquestación y programación de código abierto populares, ACS le permite utilizar sus habilidades existentes o aprovechar un gran corpus creciente de conocimientos de la comunidad para implementar y administrar aplicaciones basadas en contenedor en Microsoft Azure.

Azure Container Service optimiza la configuración de tecnologías y herramientas populares de código abierto de agrupación en clústeres de Docker específicamente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador, y Azure Container Service se encarga de todo lo demás.

![](./media/image28.png)

**Figura 4-24**. Opciones de agrupación en clústeres en Azure Container Service

ACS usa imágenes de Docker para asegurarse de que los contenedores de la aplicación sean totalmente portables. Es compatible con plataformas de orquestación de código abierto como DC/OS (con tecnología de Apache Mesos), Kubernetes (creado originalmente por Google) y Docker Swarm, para asegurarse de que estas aplicaciones se pueden escalar hasta miles o incluso decenas de miles de contenedores.

Azure Container Service permite sacar provecho de las características de nivel empresarial de Azure manteniendo la portabilidad de la aplicación, incluso en las capas de orquestación.

![](./media/image29.png)

**Figura 4-25**. Orquestadores en ACS

Como se muestra en la figura 4-25, Azure Container Service es simplemente la infraestructura proporcionada por Azure para implementar DC/OS, Kubernetes o Docker Swarm, pero ACS no implementa ningún orquestador adicional. Por lo tanto, ACS no es un orquestador como tal; solo es una infraestructura que aprovecha los orquestadores existentes de código abierto para contenedores.

Desde una perspectiva de uso, el objetivo de Azure Container Service es proporcionar un entorno de hospedaje de contenedores mediante tecnologías y herramientas de código abierto populares. Para ello, expone los puntos de conexión de API estándar para el orquestador elegido. Mediante el uso de estos puntos de conexión, se puede aprovechar cualquier software que se comunique con los puntos de conexión. Por ejemplo, en el caso del punto de conexión de Docker Swarm, se puede utilizar la interfaz de línea de comandos (CLI) de Docker. Para DC/OS, puede utilizar la CLI de DC/OS.

### <a name="getting-started-with-azure-container-service"></a>Introducción a Azure Container Service 

Para empezar a usar Azure Container Service, implemente un clúster de Azure Container Service desde Azure Portal mediante una plantilla de Azure Resource Manager o la [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). Las plantillas disponibles son [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) y [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Las plantillas de inicio rápido se pueden modificar para incluir configuración adicional o avanzada de Azure. Para obtener más información sobre la implementación de un clúster de Azure Container Service, consulte [Implementar un clúster de Azure Container Service](https://docs.microsoft.com/azure/container-service/container-service-deployment) en el sitio web de Azure.

No hay cuotas para el software instalado de forma predeterminada como parte de ACS. Todas las opciones predeterminadas se implementan con el software de código abierto.

ACS está actualmente disponible para las máquinas virtuales de Linux de las series estándar A, D, DS, G y GS en Azure. Se cobra únicamente por las instancias de proceso que se elijan, así como por los otros recursos subyacentes de la infraestructura que se utilicen como, por ejemplo, la red y el almacenamiento. No hay ningún cargo incremental para ACS.

## <a name="additional-resources"></a>Recursos adicionales

-   **Introducción a las soluciones de hospedaje del contenedor de Docker con Azure Container Service**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Docker Swarm overview (Información general de Docker Swarm)**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Swarm mode overview (Información general del modo Swarm)**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Mesosphere DC/OS Overview (Información general de Mesosphere DC/OS)**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes.** Sitio oficial.
    [*https://kubernetes.io/*](https://kubernetes.io/)


>[!div class="step-by-step"]
[Anterior](resilient-high-availability-microservices.md)
[Siguiente](using-azure-service-fabric.md)
