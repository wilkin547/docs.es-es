---
title: Técnicas y tutoriales de introducción
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Técnicas y tutoriales de introducción
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: e89f1e79eec16919b2e70952392b6f640433156b
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846264"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Técnicas y tutoriales de introducción

Para limitar el tamaño de este libro electrónico, documentación técnica adicional y los tutoriales completos estuvieran disponibles en un repositorio de GitHub. La serie de tutoriales que se describen en este capítulo en línea cubre el programa de instalación paso a paso de los entornos de varios que se basan en los contenedores de Windows y la implementación en Azure.

Las secciones siguientes explican lo que cada tutorial trata sobre sus objetivos y la visión de alto nivel y proporciona un diagrama de las tareas que intervienen. Puede obtener los tutoriales a sí mismos en el *eShopModernizing* wiki de repositorio de GitHub de aplicaciones en [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).

## <a name="technical-walkthrough-list"></a>Lista de tutoriales técnicos

Los siguientes tutoriales de introducción proporcionan orientación técnica coherente e integral para aplicaciones de ejemplo que puede elevar y desplazar mediante el uso de contenedores y, a continuación, desplazarse a través de varias opciones de implementación de Azure.

Cada uno de los siguientes tutoriales usa la nueva eShopLegacy y eShopModernizing aplicaciones de ejemplo, que están disponibles en GitHub en [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).

- **Paseo por las aplicaciones heredadas eShop (aplicaciones de línea de base para modernizar)**

- **Incluya las aplicaciones web existentes en ASP.NET (formularios Web Forms y MVC) con contenedores de Windows**

- **Incluya los servicios WCF (aplicaciones de N niveles) existentes con contenedores de Windows**

- **Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure**

- **Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en Azure Container Service**

- **Implementar las aplicaciones de basadas en contenedores de Windows en Azure Service Fabric**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Tutorial 1: Paseo por las aplicaciones heredadas de eShop

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnico

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub eShopModernizing:

[tutoriales de wiki eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Información general

En este tutorial, puede explorar la implementación inicial de tres aplicaciones heredadas de ejemplo. Las dos primeras aplicaciones web de ejemplo tienen una arquitectura monolítica y creadas utilizando ASP.NET clásico. Una aplicación se basa en ASP.NET 4.x MVC; la segunda aplicación se basa en los formularios Web Forms ASP.NET 4.x.
El tercer trata de una aplicación de 3 niveles compuesta por una aplicación cliente de WinForms y un servidor [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.

Todas estas aplicaciones están disponibles en el [repositorio de GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Objetivos

El objetivo principal de este tutorial es simplemente para familiarizarse con estas aplicaciones y con su código y la configuración. Puede configurar las aplicaciones para que puedan generarán y usar datos simulados, sin usar la base de datos SQL, con fines de prueba. Esta configuración opcional se basa en la inserción de dependencias, de forma desacoplada.

### <a name="scenario-1-aspnet-web-apps"></a>Escenario 1: Aplicaciones Web de ASP.NET

La siguiente ilustración muestra el escenario sencillo de las aplicaciones de web ASP.NET heredadas originales.

![Escenario de arquitectura simple de las aplicaciones de web ASP.NET heredadas originales](./media/image5-1.png)

Desde una perspectiva de dominio empresarial, ambas aplicaciones ofrecen el mismo catálogo de las características de administración. Miembros del equipo de enterprise eShop usaría la aplicación para ver y editar el catálogo de productos.

En la ilustración siguiente se muestra las capturas de pantalla de la aplicación inicial.

![Aplicaciones de ASP.NET MVC y ASP.NET Web Forms (tecnologías existentes/heredadas)](./media/image5-2.png)

Dependencias en ASP.NET 4.x o versiones anteriores (ya sea para MVC o Web Forms) significa que estas aplicaciones no se ejecutarán en .NET Core a menos que el código se vuelve a escribir por completo mediante el uso de ASP.NET Core MVC.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Escenario 2: Servicio de WCF y la aplicación de cliente de WinForms (aplicación de capa 3)

La siguiente ilustración muestra el escenario sencillo de la aplicación heredada de 3 niveles original.

![Escenario de arquitectura simple de la aplicación heredada original de 3 niveles con un servicio WCF y una aplicación de cliente de WinForms](./media/image5-1.5.png)

### <a name="benefits"></a>Ventajas

Las ventajas de este tutorial son sencillas: Simplemente familiarizarse con el código y aplicaciones iniciales.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más detallada en el sitio wiki de GitHub:

- [La visita de la línea de base de ASP.NET MVC y aplicaciones de formularios Web Forms "heredadas"](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Paseo por en el servicio WCF de línea de base y la aplicación de formularios Windows Forms (nivel 3) "heredado"](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Tutorial 2: Incluya las aplicaciones .NET existentes con contenedores de Windows

### <a name="overview"></a>Información general

Usar contenedores de Windows para mejorar la implementación de aplicaciones .NET existentes, como las basadas en MVC, formularios Web Forms o WCF, para entornos de prueba, desarrollo y producción.

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es mostrar varias opciones para incluir en contenedores una aplicación existente de .NET Framework. Puede realizar lo siguiente:

- Incluya la aplicación mediante el uso de [Visual Studio 2017 Tools para Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versiones posteriores).

- Incluya la aplicación agregando manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)y, a continuación, usar el [CLI de Docker](https://docs.docker.com/engine/reference/commandline/cli/).

- Incluya la aplicación mediante el uso de la [Img2Docker](https://github.com/docker/communitytools-image2docker-win) herramienta (una herramienta de código abierto de Docker).

En este tutorial se centra en Visual Studio 2017 Tools para el enfoque de Docker, pero los otros dos enfoques son bastante similares, lo que respecta al uso Dockerfiles.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Escenario 1: Aplicaciones web ASP.NET en contenedores

La figura siguiente muestra el escenario para aplicaciones de las aplicaciones web heredadas eShop en contenedores.

![Diagrama de arquitectura simplificada de en contenedores de aplicaciones de ASP.NET en un entorno de desarrollo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Escenario 2: Servicio WCF en contenedor

La figura siguiente muestra el escenario para una aplicación de 3 niveles con un servicio WCF en contenedores.

![Diagrama de arquitectura de servicio WCF en contenedores en un entorno de desarrollo de simplificado](./media/image5-3.5.png)

### <a name="benefits"></a>Ventajas

Existen ventajas al ejecutar la aplicación monolítica en un contenedor. En primer lugar, cree una imagen de la aplicación. Desde ese momento, cada implementación se ejecuta en el mismo entorno. Cada contenedor usa la misma versión del sistema operativo, tiene la misma versión de instalar las dependencias, usa la misma versión de .NET framework y se compila mediante el mismo proceso. Básicamente, controla las dependencias de la aplicación mediante el uso de una imagen de Docker. Las dependencias de viaje con la aplicación al implementar los contenedores.

Una ventaja adicional es que los desarrolladores pueden ejecutar la aplicación en el entorno coherente que se ofrecen los contenedores de Windows. Problemas que aparecen sólo en algunas versiones se pueden observar inmediatamente, en lugar de mostrarlos en un entorno de ensayo o producción. Las diferencias en entornos de desarrollo de los miembros del equipo de desarrollo de menor importan cuando las aplicaciones se ejecutan en contenedores.

Las aplicaciones en contenedor también tienen una curva de escalado horizontal más plana. Aplicaciones en contenedores permiten tener más aplicaciones e instancias de servicio (basadas en contenedores) en una máquina virtual o física en comparación con las implementaciones de aplicaciones normales por máquina. Esto se traduce en una mayor densidad y requiere menos recursos, especialmente cuando se usa orquestadores como Kubernetes o Service Fabric.

Inclusión en contenedores, en situaciones ideales, no requiere realizar cambios en el código de aplicación (C\#). En la mayoría de los escenarios, solo necesita los archivos de metadatos de implementación de Docker (archivos archivos Dockerfile y Docker Compose).

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más detallada en el sitio wiki de GitHub:

- [Inclusión de las aplicaciones web de .NET Framework con contenedores de Windows y Docker en contenedores](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Agregar compatibilidad con Docker a un servicio WCF](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Tutorial 3: Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnico

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub eShopModernizing: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Información general

Implementación en un host de Docker en un Windows Server 2016 Virtual Machine (máquina virtual) en Azure le permite configurar rápidamente los entornos de desarrollo, prueba y almacenamiento provisional. También ofrece un lugar común para los evaluadores o usuarios empresariales validar la aplicación. Las máquinas virtuales también pueden infraestructura válido como un entorno de producción del servicio (IaaS).

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es mostrar la varias alternativas de que tener al implementar contenedores de Windows en máquinas virtuales de Azure que se basan en Windows Server 2016 o versiones posteriores.

### <a name="scenarios"></a>Escenarios

Varios escenarios se tratan en este tutorial.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Escenario A: Implementar en una máquina virtual de Azure desde un equipo de desarrollo a través de la conexión con el motor de Docker

![Implementar en una máquina virtual de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker](./media/image5-4.png)

**Figura 5-4.** Implementar en una máquina virtual de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Escenario B: Implementar en una máquina virtual de Azure a través de un registro de Docker

![Implementar en una máquina virtual de Azure a través de un registro de Docker](./media/image5-5.png)

**Figura 5-5.** Implementar en una máquina virtual de Azure a través de un registro de Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Escenario de C: Implementar en una máquina virtual de Azure desde las canalizaciones de CI/CD en servicios de Azure DevOps

![Implementar en una máquina virtual de Azure desde las canalizaciones de CI/CD en servicios de Azure DevOps](./media/image5-6.png)

**Figura 5-6**. Implementar en una máquina virtual de Azure desde las canalizaciones de CI/CD en servicios de Azure DevOps

### <a name="azure-vms-for-windows-containers"></a>Máquinas virtuales de Azure para contenedores de Windows

Máquinas virtuales de Azure para contenedores de Windows son máquinas virtuales basadas en Windows Server 2016, Windows 10 o versiones posteriores, ambos con el motor de Docker configuración. En la mayoría de los casos, Windows Server 2016 se usa en las máquinas virtuales de Azure.

Actualmente, Azure proporciona una máquina virtual denominada **Windows Server 2016 con Containers**. Puede usar esta máquina virtual para probar la nueva característica de contenedor de Windows Server, con Windows Server Core o Windows Nano Server. Se instalan las imágenes de sistema operativo de contenedor y, a continuación, la máquina virtual está lista para su uso con Docker.

### <a name="benefits"></a>Ventajas

Aunque los contenedores de Windows se pueden implementar en las máquinas virtuales de un entorno local Windows Server 2016, cuando se implementa en Azure, obtenga una manera más fácil empezar a trabajar, con máquinas virtuales de contenedor de listas para usar Windows Server. También obtendrá una ubicación común en línea que se puede acceder a los evaluadores y escalabilidad automática a través de conjuntos de escalado de máquina virtual de Azure.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más detallada en el sitio wiki de GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Tutorial 4: Implementar las aplicaciones de basadas en contenedores de Windows en Azure Container Instances (ACI)

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnico

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub eShopModernizing:

[Implementación de las aplicaciones en ACI (instancias de contenedor de Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Información general

[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) es la forma más rápida para tener un entorno de desarrollo, prueba y almacenamiento provisional de los contenedores donde puede implementar instancias únicas de contenedores.

### <a name="goals"></a>Objetivos

En este tutorial se muestra los escenarios principales al implementar contenedores de Windows en Azure Container Instances (ACI) y cómo se pueden implementar aplicaciones eShopModernizing en ACI.

### <a name="scenarios"></a>Escenarios

Puede haber variaciones sobre cómo implementar las aplicaciones eShopModernizing en ACI como la implementación de una o todas las aplicaciones (aplicación de MVC, aplicación de formularios Web Forms o servicio WCF). En el siguiente escenario que se muestra a continuación puede ver la aplicación ASP.NET MVC y el contenedor de SQL Server de ellas implementan como contenedores en ACI (Azure Container Instances).

![Implementación en ACI desde un entorno de desarrollo](./media/image5-3.5.6.png)

### <a name="benefits"></a>Ventajas

Azure Container Instances es muy fácil de crear y administrar contenedores de Docker en Azure, sin tener que aprovisionar máquinas virtuales ni recurrir a un servicio de nivel superior. Con ACI, directamente puede implementar un contenedor de Windows en Azure y lo expondremos en internet con un nombre de dominio completo (FQDN) en cuestión de segundos (siempre que tenga la imagen de contenedor de Windows lista en un registro de Docker como Docker Hub o Azure Container Registro).

### <a name="considerations"></a>Consideraciones

Implementación de contenedores de Windows con cualquier versión de .NET Framework completo / ASP.NET o SQL Server en Azure Container Instances (ACI) no es bastante tan rápido como la implementación en un Host de Docker normales (por ejemplo, Windows Server 2016 con contenedores de Windows) porque la imagen de Docker debe ser descargado (extraigan desde el registro de Docker) cada vez y los tamaños de la imagen de contenedor SQL (15.1 GB) y la imagen de contenedor (13.9 GB) de ASP.NET son considerablemente grandes, pero es mucho más barato que el mantenimiento de su propio host de docker (permanentemente en línea Windows Server 2016 con la máquina virtual de contenedores de Windows en Azure) no se mencione un orquestador como Kubernetes en Azure (AKS/ACS) o Azure Service Fabric que, por otro lado, son excelentes alternativas para las implementaciones de producción completo.

Como término principal, mediante Azure Container Instances es una opción muy atractiva para escenarios de desarrollo/pruebas y para las canalizaciones de CI/CD.

## <a name="next-steps"></a>Pasos siguientes

Explore este contenido más detallada en el sitio wiki de GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Tutorial 5: Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en Azure Container Service

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnico

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub eShopModernizing:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Información general

Una aplicación que se basa en contenedores de Windows rápidamente deba usar las plataformas, aún más aleja desde máquinas virtuales de IaaS. Esto es necesario para lograr una alta escalabilidad fácilmente y mejor automatizada escalabilidad y para una mejora considerable en las implementaciones y control de versiones automatizadas. Puede lograr estos objetivos utilizando el orquestador [Kubernetes](https://kubernetes.io/), disponible en [Azure Container Service](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Objetivos

Es el objetivo de este tutorial aprender a implementar una aplicación basada en el contenedor de Windows en Kubernetes (también denominado *K8s*) en Azure Container Service. Implementación en Kubernetes desde cero es un proceso de dos pasos:

1. Implementar un clúster de Kubernetes en Azure Container Service.

2. Implementar la aplicación y los recursos relacionados en el clúster de Kubernetes.

### <a name="scenarios"></a>Escenarios

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Escenario A: Implementar directamente en un clúster de Kubernetes desde un entorno de desarrollo

![Implementar directamente en un clúster de Kubernetes desde un entorno de desarrollo](./media/image5-7.png)

**Figura 5-7.** Implementar directamente en un clúster de Kubernetes desde un entorno de desarrollo

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Escenario B: Implementar en un clúster de Kubernetes desde las canalizaciones de CI/CD en servicios de Azure DevOps

![Implementar en un clúster de Kubernetes desde las canalizaciones de CI/CD en servicios de Azure DevOps](./media/image5-8.png)

**Figura 5-8.** Implementar en un clúster de Kubernetes desde las canalizaciones de CI/CD en servicios de Azure DevOps

### <a name="benefits"></a>Ventajas

Hay muchas ventajas a la implementación en un clúster de Kubernetes. La principal ventaja es que obtiene un entorno listo para producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de nodos o máquinas virtuales en el clúster) escalabilidad global del clúster).

Azure Container Service optimiza las tecnologías y herramientas populares de código abierto diseñadas especialmente para Azure. Obtenga una solución abierta que ofrece la portabilidad tanto para los contenedores para la configuración de la aplicación. Seleccione el tamaño, el número de hosts, y el servicio de contenedor-herramientas de orchestrator controla todo lo demás.

Con Kubernetes, los desarrolladores pueden avanzar de pensar en máquinas físicas y virtuales, planeamiento de una infraestructura centrada en el contenedor que facilita las capacidades siguientes, entre otros:

- Aplicaciones basadas en varios contenedores

- Replicación de las instancias de contenedor y el escalado automático horizontal

- Nomenclatura y detectar (por ejemplo, DNS interno)

- Equilibrio de carga

- Actualizaciones graduales

- Distribuir secretos

- Comprobaciones de estado de aplicación

## <a name="next-steps"></a>Pasos siguientes

Explore este contenido más detallada en el sitio wiki de GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Tutorial: 6: Implementar las aplicaciones de basadas en contenedores de Windows en Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnico

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub eShopModernizing:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Información general

Una aplicación basada en contenedores de Windows rápidamente debe usar las plataformas, aún más aleja desde máquinas virtuales de IaaS. Esto es necesario para lograr una alta escalabilidad fácilmente y mejor automatizada escalabilidad y para una mejora considerable en las implementaciones y control de versiones automatizadas. Puede lograr estos objetivos con el orquestador de Azure Service Fabric, que está disponible en la nube de Azure, pero también disponible para su uso en el entorno local, o incluso en una nube pública diferente.

### <a name="goals"></a>Objetivos

Es el objetivo de este tutorial aprender a implementar una aplicación basada en el contenedor de Windows en un clúster de Service Fabric en Azure. Implementación en Service Fabric desde cero es un proceso de dos pasos:

1. Implementar un clúster de Service Fabric en Azure (o a un entorno diferente).

2. Implementar la aplicación y los recursos relacionados en el clúster de Service Fabric.

### <a name="scenarios"></a>Escenarios

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Escenario A: Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo

![Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo](./media/image5-9.png)

> **Figura 5-9.** Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Escenario B: Implementar en un clúster de Service Fabric desde canalizaciones de CI/CD en servicios de Azure DevOps

![Implementar en un clúster de Service Fabric desde canalizaciones de CI/CD en servicios de Azure DevOps](./media/image5-10.png)

**Figura 5-10.** Implementar en un clúster de Service Fabric desde canalizaciones de CI/CD en servicios de Azure DevOps

## <a name="benefits"></a>Ventajas

Las ventajas de implementar en un clúster de Service Fabric son similares a las ventajas del uso de Kubernetes. Una diferencia, sin embargo, es que Service Fabric es un entorno de producción más maduro para aplicaciones de Windows en comparación con Kubernetes, que se encuentra en una fase beta para los contenedores de Windows en Kubernetes versión 1.9 (diciembre de 2017). Kubernetes es un entorno más maduro para Linux.

La principal ventaja del uso de Azure Service Fabric es que obtiene un entorno listo para producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de los nodos o máquinas virtuales del clúster (escalabilidad global del clúster).

Azure Service Fabric ofrece la portabilidad para sus contenedores tanto para la configuración de la aplicación. Puede tener un tejido de servicio de clúster en Azure, o bien instalarlo de forma local en su propio centro de datos. Incluso puede instalar un clúster de Service Fabric en una nube diferente, como [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

Con Service Fabric, los desarrolladores pueden avanzar de pensar en máquinas físicas y virtuales a la planificación de una infraestructura centrada en el contenedor que facilita las capacidades siguientes, entre otros:

- Aplicaciones basadas en varios contenedores.

- Replicación de las instancias de contenedor y el escalado automático horizontal.

- Nomenclatura y detectar (por ejemplo, DNS interno).

- Equilibrio de carga.

- Actualizaciones graduales.

- Distribuir secretos.

- Comprueba el estado de la aplicación.

Las siguientes funcionalidades son excluyentes en Service Fabric (en comparación con otros orquestadores):

- Capacidad de los servicios con estado, a través del modelo de aplicación de Reliable Services.

- Patrón de actores a través del modelo de aplicación de Reliable Actors.

- Implemente procesos esencial, además de los contenedores de Windows o Linux.

- Avanzada de actualizaciones graduales y comprobaciones de estado.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más detallada en el sitio wiki de GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

> [!div class="step-by-step"]
> [Anterior](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [Siguiente](conclusions.md)
