---
title: Orquestar microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad
description: Descubra las opciones para orquestar microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad de las posibilidades de espacios de desarrollo de Azure durante el desarrollo del ciclo de vida de aplicación de Kubernetes.
ms.date: 01/30/2020
ms.openlocfilehash: f9e91d3958e2d567e68257c377f76cc3c2325a0b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502984"
---
# <a name="orchestrate-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orquestar microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad

La utilización de orquestadores para aplicaciones listas para producción es fundamental si la aplicación se basa en microservicios o simplemente está dividida entre varios contenedores. Como se mencionó anteriormente, en un enfoque basado en microservicios, cada microservicio posee su modelo y sus datos para que sea autónomo desde un punto de vista del desarrollo y la implementación. Pero incluso si tiene una aplicación más tradicional que se compone de varios servicios (por ejemplo, SOA), también tendrá varios contenedores o servicios que conforman una sola aplicación de negocio que deban implementarse como un sistema distribuido. Estos tipos de sistemas son difíciles de administrar y escalar horizontalmente; por lo tanto, un orquestador es indispensable si se quiere tener una aplicación de varios contenedores, escalable y lista para la producción.

La figura 4-23 ilustra la implementación en un clúster de una aplicación formada por varios microservicios (contenedores).

![Diagrama que muestra las aplicaciones de Docker compuestas en un clúster.](./media/scalable-available-multi-container-microservice-applications/composed-docker-applications-cluster.png)

**Figura 4-23**. Un clúster de contenedores

use un contenedor para cada instancia de servicio. Los contenedores de Docker son “unidades de implementación” y un contenedor es una instancia de Docker. Un host controla muchos contenedores. Parece un enfoque lógico. Pero, ¿cómo se está administrando el equilibrio de carga de control, el enrutamiento y la orquestación de estas aplicaciones compuestas?

El motor de Docker estándar en hosts de Docker único satisface las necesidades de administración de instancias de imagen únicas en un host, pero se queda corto a la hora de administrar varios contenedores implementados en varios hosts para aplicaciones distribuidas más complejas. En la mayoría de los casos, se necesita una plataforma de administración que automáticamente inicie contenedores, escale horizontalmente contenedores con varias instancias por imagen, los suspenda o los cierre cuando sea necesario y, a ser posible, también controle su acceso a recursos como la red y el almacenamiento de datos.

Para ir más allá de la administración de contenedores individuales o aplicaciones compuestas muy simples y pasar a aplicaciones empresariales más grandes con microservicios, debe cambiar a orquestación y plataformas de agrupación en clústeres.

Desde el punto de vista de la arquitectura y el desarrollo, si está compilando grandes aplicaciones empresariales basadas en microservicios, es importante familiarizarse con las siguientes plataformas y productos que admiten escenarios avanzados:

**Clústeres y orquestadores**. Cuando se necesita escalar horizontalmente las aplicaciones a varios hosts de Docker, como con una aplicación grande basada en microservicios, es fundamental poder administrar todos los hosts como un solo clúster mediante la abstracción de la complejidad de la plataforma subyacente. Eso es lo que proporcionan los clústeres de contenedor y los orquestadores. Kubernetes es un ejemplo de orquestador, y está disponible en Azure a través de Azure Kubernetes Service.

**Programadores**. *Programar* significa tener la capacidad de que un administrador inicie los contenedores de un clúster, y de proporcionar también una interfaz de usuario. Un programador de clúster tiene varias responsabilidades: usar eficazmente los recursos del clúster, establecer las restricciones definidas por el usuario, equilibrar eficazmente la carga de los contenedores entre los distintos nodos o hosts, ser resistente a los errores y proporcionar un alto grado de disponibilidad.

Los conceptos de un clúster y un programador están estrechamente relacionados, por lo que los productos proporcionados por diferentes proveedores suelen ofrecer ambos conjuntos de funciones. En la lista siguiente se muestran las plataformas y las opciones de software más importantes disponibles para clústeres y programadores. Estos orquestadores generalmente se ofrecen en nubes públicas como Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Plataformas de software para agrupación en clústeres de contenedores, orquestación y programación

|     |   |
|-----|---|
| **Kubernetes** <br> ![Una imagen del logotipo de Kubernetes.](./media/scalable-available-multi-container-microservice-applications/kubernetes-container-orchestration-system-logo.png) | [*Kubernetes*](https://kubernetes.io/) es un producto de código abierto cuya funcionalidad abarca desde la infraestructura de clúster y la programación de contenedores a las capacidades de orquestación. Permite automatizar la implementación, la escala y las operaciones de contenedores de aplicaciones en varios clústeres de hosts. <br><br> *Kubernetes* proporciona una infraestructura centrada en el contenedor que agrupa los contenedores de la aplicación en unidades lógicas para facilitar la administración y detección. <br><br> *Kubernetes* está más desarrollado en Linux que en Windows. |
| **Azure Kubernetes Service (AKS)** <br> ![Una imagen del logotipo de Azure Kubernetes Service](./media/scalable-available-multi-container-microservice-applications/azure-kubernetes-service-logo.png). | [AKS](https://azure.microsoft.com/services/kubernetes-service/) es un servicio administrado de orquestación de contenedores de Kubernetes en Azure que simplifica la administración, implementación y operaciones del clúster de Kubernetes. |

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Uso de orquestadores basados en contenedor en Microsoft Azure

Existen varios proveedores de nube que ofrecen compatibilidad con contenedores de Docker más compatibilidad con la orquestación y los clústeres de Docker, como Microsoft Azure, Amazon EC2 Container Service y Google Container Engine. Microsoft Azure proporciona compatibilidad con orquestador y clúster de Docker a través de Azure Kubernetes Service (AKS).

## <a name="using-azure-kubernetes-service"></a>Uso de Azure Kubernetes Service

Un clúster de Kubernetes agrupa varios hosts de Docker y los expone como un único host virtual de Docker, lo que permite implementar varios contenedores en el clúster y escalar horizontalmente con cualquier número de instancias de contenedor. El clúster controlará toda la mecánica de administración compleja, como la escalabilidad, el estado, etc.

AKS proporciona una manera de simplificar la creación, la configuración y la administración de un clúster de máquinas virtuales en Azure que están preconfiguradas para ejecutar aplicaciones en contenedores. Al utilizar una configuración optimizada de herramientas de orquestación y programación de código abierto populares, AKS le permite usar sus habilidades existentes o aprovechar un gran corpus creciente de conocimientos de la comunidad para implementar y administrar aplicaciones basadas en contenedor en Microsoft Azure.

Azure Kubernetes Service optimiza la configuración de tecnologías y herramientas populares de código abierto de agrupación en clústeres de Docker específicamente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador, y AKS se encarga de todo lo demás.

![Diagrama que muestra una estructura de un clúster de Kubernetes.](./media/scalable-available-multi-container-microservice-applications/kubernetes-cluster-simplified-structure.png)

**Figura 4-24**. Topología y estructura simplificada del clúster de Kubernetes

En la figura 4-24 puede ver la estructura de un clúster de Kubernetes, donde un nodo maestro (VM) controla la mayor parte de la coordinación del clúster y puede implementar contenedores en el resto de los nodos que se administran como un único grupo desde un punto de vista de la aplicación y permite escalar a miles o incluso a decenas de miles de contenedores.

## <a name="development-environment-for-kubernetes"></a>Entorno de desarrollo para Kubernetes

En el entorno de desarrollo, [Docker anunció en julio de 2018](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/) que Kubernetes también puede ejecutarse en un único equipo de desarrollo (Windows 10 o macOS), basta con instalar [Docker Desktop](https://docs.docker.com/install/). Puede implementar posteriormente en la nube (AKS) para obtener más pruebas de integración, como se muestra en la figura 4-25.

![Diagrama que muestra Kubernetes en una máquina de desarrollo y luego se implementa en AKS](./media/scalable-available-multi-container-microservice-applications/kubernetes-development-environment.png)

**Figura 4-25**. Ejecución de Kubernetes en el equipo de desarrollo y la nube

## <a name="getting-started-with-azure-kubernetes-service-aks"></a>Introducción a Azure Kubernetes Service (AKS)

Para empezar a usar AKS, implemente un clúster de AKS desde Azure Portal o mediante la CLI. Para más información sobre la implementación de un clúster de Kubernetes en Azure, consulte [Inicio rápido: Implementación de un clúster de Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

No hay cuotas para el software instalado de forma predeterminada como parte de AKS. Todas las opciones predeterminadas se implementan con el software de código abierto. AKS está disponible en varias máquinas virtuales en Azure. Se cobra únicamente por las instancias de proceso que se elijan, así como por los otros recursos subyacentes de la infraestructura que se utilicen como, por ejemplo, la red y el almacenamiento. No hay ningún cargo incremental para AKS.

La opción de implementación de producción predeterminada para Kubernetes es usar gráficos Helm, pero esto lo veremos en la sección siguiente.

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Implementación con gráficos de Helm en clústeres de Kubernetes

Al implementar una aplicación en un clúster de Kubernetes, puede usar la herramienta de CLI kubectl.exe original mediante archivos de implementación basados en el formato nativo (archivos .yaml), como ya se mencionó en la sección anterior. Pero, para aplicaciones de Kubernetes más complejas, como al implementar aplicaciones complejas basadas en microservicios, se recomienda usar [Helm](https://helm.sh/).

Los gráficos de Helm le ayudan a definir, establecer la versión, instalación, compartir, actualizar o revertir incluso la aplicación más compleja de Kubernetes.

Adicionalmente, el uso de Helm se recomienda porque otros entornos de Kubernetes en Azure, como [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces), también se basan en los gráficos de Helm.

La [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) mantiene Helm en colaboración con Microsoft, Google, Bitnami y la Comunidad de colaboradores de Helm.

Para obtener más información sobre la implementación de gráficos de Helm y Kubernetes, vea la entrada de blog [Uso de gráficos de Helm para implementar eShopOnContainers en AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)).

## <a name="use-azure-dev-spaces-for-your-kubernetes-application-lifecycle"></a>Uso de Azure Dev Spaces para el ciclo de vida de la aplicación de Kubernetes

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) proporciona una experiencia de desarrollo de Kubernetes rápida e iterativa para los equipos. Con una configuración de máquina de desarrollo mínima, puede ejecutar y depurar contenedores de forma iterativa directamente en Azure Kubernetes Service (AKS). Desarrolle en Windows, Mac o Linux mediante herramientas familiares como Visual Studio, Visual Studio Code o la línea de comandos.

Como se mencionó, Kubernetes utiliza los gráficos de Helm al implementar las aplicaciones basadas en contenedores.

Azure Dev Spaces ayuda a los equipos de desarrollo a ser más productivos en Kubernetes porque permite iterar rápidamente y depurar código directamente en un clúster de Kubernetes global en Azure solo con Visual Studio 2019 o Visual Studio Code. Ese clúster de Kubernetes en Azure es un clúster de Kubernetes administrado compartido, por lo que su equipo puede colaborar. Puede desarrollar código de forma aislada, después implementarlo en el clúster global y realizar pruebas de un extremo a otro con otros componentes sin tener que replicar ni simular dependencias.

Como se muestra en la figura 4-26, la característica distintiva de Azure Dev Spaces es la capacidad de crear "espacios" que se pueden ejecutar integrados al resto de la implementación global en el clúster.

![Diagrama que muestra el uso de varios espacios en Azure Dev Spaces.](./media/scalable-available-multi-container-microservice-applications/use-multiple-spaces-azure-dev.png)

**Figura 4-26**. Uso de varios espacios en Azure Dev Spaces

Básicamente, puede configurar un espacio de desarrollo compartido en Azure. Así, cada programador se puede centrar exclusivamente en su parte de la aplicación y desarrollar de forma iterativa código previo a la confirmación en un espacio de desarrollo que ya contenga todos los demás servicios y recursos en la nube de los que sus escenarios dependen. Las dependencias siempre estarán actualizadas y los desarrolladores trabajarán de una manera que se asemeja bastante a un entorno de producción.

En Azure Dev Spaces existe el concepto de espacio, que permite trabajar de manera relativamente aislada y sin riesgo de romper el trabajo del equipo. Cada espacio de desarrollo forma parte de una estructura jerárquica que le permite invalidar un microservicio (o muchos), desde el espacio de desarrollo maestro "top", con su propio microservicio en curso.

Esta característica se basa en los prefijos de dirección URL, por lo que al utilizar cualquier prefijo de espacio de desarrollo en la dirección url, se sirve una solicitud desde el microservicio de destino si existe en el espacio de desarrollo, de lo contrario, se reenvía hasta la primera instancia del microservicio de destino que se encuentra en la jerarquía, que finalmente llega al espacio de desarrollo maestro en la parte superior.

Para obtener una vista práctica en un ejemplo concreto, vea la [página wiki de eShopOnContainers en Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces).

Para obtener más información, vea el artículo sobre [Desarrollo en equipo con Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Recursos adicionales

- **Guía de inicio rápido: Implementación de un clúster de Azure Kubernetes Service (AKS)**  \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Azure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes** El sitio oficial. \
  <https://kubernetes.io/>

>[!div class="step-by-step"]
>[Anterior](resilient-high-availability-microservices.md)
>[Siguiente](../docker-application-development-process/index.md)
