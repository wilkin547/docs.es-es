---
title: Tutoriales e introducción técnica
description: Modernización de aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Tutoriales e introducción técnica
ms.date: 04/28/2018
ms.openlocfilehash: 98d33b13d2b28bfe1c35894df45e525cff0520c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172149"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Tutoriales e introducción técnica

Para limitar el tamaño de este libro electrónico, hay disponible documentación técnica adicional y los tutoriales completos en un repositorio de GitHub. En la serie de tutoriales en línea que se describe en este capítulo se abarca la configuración paso a paso de los diversos entornos que están basados en contenedores de Windows y la implementación en Azure.

En las secciones siguientes se explica en qué consiste cada tutorial, sus objetivos y visión de alto nivel y se proporciona un diagrama de las tareas implicadas. Puede obtener los tutoriales en la wiki del repositorio de GitHub de aplicaciones *eShopModernizing* en <https://github.com/dotnet-architecture/eShopModernizing/wiki>.

## <a name="technical-walkthrough-list"></a>Lista de tutoriales técnicos

Los tutoriales de introducción siguientes proporcionan una guía técnica coherente y completa para las aplicaciones de ejemplo que se pueden migrar mediante lift-and-shift a través del uso de contenedores y, a continuación, moverse con varias opciones de implementación en Azure.

Cada uno de los tutoriales siguientes usa las aplicaciones eShopLegacy e eShopModernizing de ejemplo nuevas, que están disponibles en GitHub en <https://github.com/dotnet-architecture/eShopModernizing>.

- **Un paseo por las aplicaciones heredadas de eShop (aplicaciones de línea de base que se van a modernizar)**

- **Inclusión en contenedores de las aplicaciones web de ASP.NET (WebForms y MVC) con contenedores de Windows**

- **Inclusión en contenedores de los servicios WCF existentes (aplicaciones de n niveles) con contenedores de Windows**

- **Implementación de una aplicación basada en contenedores de Windows en máquinas virtuales de Azure**

- **Implementación de aplicaciones basadas en contenedores de Windows en Kubernetes en Azure Container Service**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Tutorial 1: Un paseo por las aplicaciones heredadas de eShop

### <a name="technical-walkthrough-availability"></a>Disponibilidad del tutorial técnico

El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:

[Tutoriales de la wiki de eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Información general

En este tutorial puede explorar la implementación inicial de tres aplicaciones heredadas de ejemplo. Las dos primeras aplicaciones web de ejemplo tienen una arquitectura monolítica y se crearon con ASP.NET clásico. Una aplicación se basa en ASP.NET 4.x MVC, mientras que la segunda, en formularios ASP.NET 4.x Web Forms.
La tercera es una aplicación de 3 niveles que consta de una aplicación de WinForms de cliente y un servicio [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) del lado servidor.

Todas estas aplicaciones están disponibles en el [repositorio eShopModernizing de GitHub](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Objetivos

El objetivo principal de este tutorial es familiarizarse con estas aplicaciones y con su código y configuración. Puede configurar las aplicaciones para que generen y usen datos ficticios, sin usar la base de datos SQL, con fines de prueba. Esta configuración opcional se basa en la inserción de dependencias de manera desacoplada.

### <a name="scenario-1-aspnet-web-apps"></a>Escenario 1: Aplicaciones web ASP.NET

En la ilustración siguiente se muestra el escenario simple de las aplicaciones web ASP.NET heredadas originales.

![Escenario de arquitectura simple de las aplicaciones web ASP.NET heredadas originales](./media/image5-1.png)

Desde la perspectiva del dominio empresarial, ambas aplicaciones ofrecen las mismas características de administración de catálogos. Los miembros del equipo empresarial de eShop usarían la aplicación para ver y editar el catálogo de productos.

En la ilustración siguiente se muestran las capturas de pantallas de las aplicaciones iniciales.

![Aplicaciones ASP.NET MVC y ASP.NET Web Forms (tecnologías existentes o heredadas)](./media/image5-2.png)

Las dependencias de ASP.NET 4.x o versiones anteriores (ya sea para MVC o para Web Forms) significan que estas aplicaciones no se ejecutarán en .NET Core a menos que el código se reescriba por completo mediante ASP.NET Core MVC.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Escenario 2: Servicio WCF y aplicación cliente de WinForms (aplicación de 3 niveles)

En la ilustración siguiente se muestra el escenario simple de la aplicación web de 3 niveles original.

![Escenario de arquitectura simple de la aplicación heredada de 3 niveles original con un servicio WCF y una aplicación cliente de WinForms](./media/image5-1.5.png)

### <a name="benefits"></a>Ventajas

Las ventajas de este tutorial son sencillas: Familiarícese con el código y las aplicaciones iniciales.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más en profundidad en la wiki de GitHub:

- [Un paseo por las aplicaciones ASP.NET MVC y ASP.NET Web Forms de línea de base "heredadas"](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Un paseo por la aplicación del servicio WCF y WinForms (de tres niveles) de línea de base "heredadas"](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Tutorial 2: Inclusión en contenedores de las aplicaciones .NET existentes con contenedores de Windows

### <a name="overview"></a>Información general

Use contenedores de Windows para mejorar la implementación de las aplicaciones .NET existentes, como las basadas en MVC, Web Forms o WCF, en entornos de producción, desarrollo y prueba.

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es mostrar varias opciones para incluir una aplicación .NET Framework existente en un contenedor. Puede realizar lo siguiente:

- Incluir la aplicación en contenedores mediante [Visual Studio 2017 Tools para Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versiones posteriores).

- Para incluir la aplicación en un contenedor, agregue manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/) y, a continuación, use la [CLI de Docker](https://docs.docker.com/engine/reference/commandline/cli/).

- Incluya la aplicación en contenedores mediante la herramienta [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (una herramienta de código abierto de Docker).

Este tutorial se centra en el enfoque de Visual Studio 2017 Tools para Docker, pero los otros dos enfoques son muy similares en lo que respecta al uso de Dockerfiles.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Escenario 1: Aplicaciones web ASP.NET en contenedores

En la ilustración siguiente se muestra el escenario para las aplicaciones web heredadas de eShop en contenedores.

![Diagrama de arquitectura simplificado de aplicaciones ASP.NET en contenedores en un entorno de desarrollo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Escenario 2: Servicio WCF en contenedores

En la ilustración siguiente se muestra el escenario de una aplicación de 3 niveles con un servicio WCF en contenedores.

![Diagrama de arquitectura simplificado de un servicio WCF en contenedores en un entorno de desarrollo](./media/image5-3.5.png)

### <a name="benefits"></a>Ventajas

Ejecutar una aplicación monolítica en un contenedor tiene ciertas ventajas. En primer lugar, cree una imagen para la aplicación. A partir de ese momento, todas las implementaciones se ejecutarán en el mismo entorno. Cada contenedor usa la misma versión de sistema operativo, tiene instalada la misma versión de dependencias, usa la misma versión de .NET Framework y se compila con el mismo proceso. Básicamente, puede controlar las dependencias de la aplicación mediante una imagen de Docker. Las dependencias viajan con la aplicación cuando se implementan los contenedores.

Una ventaja adicional es que los desarrolladores pueden ejecutar la aplicación en el entorno coherente que proporcionan los contenedores de Windows. Los problemas que solo aparecen con ciertas versiones se pueden solucionar inmediatamente, en lugar de hacerlo en un entorno de ensayo o de producción. Las diferencias en los entornos de desarrollo que usan los miembros del equipo de desarrollo tienen menos importancia cuando las aplicaciones se ejecutan en contenedores.

Las aplicaciones en contenedor también tienen una curva de escalado horizontal más plana. Las aplicaciones en contenedor permiten tener más instancias de aplicaciones y servicios (basadas en contenedores) en una máquina virtual o en una máquina física en comparación con las implementaciones de aplicaciones normales por máquina. Esto se traduce en una mayor densidad y en menos recursos necesarios, especialmente cuando se usan orquestadores como Kubernetes.

En situaciones ideales, la inclusión en contenedores no requiere ningún cambio en el código de la aplicación (C\#). En la mayoría de los escenarios, solo necesita los archivos de metadatos de implementación de Docker (archivos Dockerfiles y Docker Compose).

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más en profundidad en la wiki de GitHub:

- [Inclusión en contenedores de las aplicaciones web de .NET Framework con contenedores de Windows y Dockers](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Incorporación de la compatibilidad con Docker en un servicio WCF](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Tutorial 3: Implementación de una aplicación basada en contenedores de Windows en máquinas virtuales de Azure

### <a name="technical-walkthrough-availability"></a>Disponibilidad del tutorial técnico

El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>Información general

La implementación en un host de Docker en una máquina virtual (VM) con Windows Server 2016 en Azure le permite configurar rápidamente entornos de desarrollo, pruebas y ensayo. También ofrece un lugar común para que los evaluadores o usuarios empresariales validen la aplicación. Las máquinas virtuales también pueden ser entornos de producción de infraestructura como servicio (IaaS) válidos.

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es mostrar las diversas alternativas que se tienen en el momento de implementar contenedores de Windows en máquinas virtuales de Azure basadas en Windows Server 2016 o versiones posteriores.

### <a name="scenarios"></a>Escenarios

En este tutorial se explican varios escenarios.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Escenario A: Implementación en una máquina virtual de Azure desde un equipo de desarrollo a través de la conexión del motor de Docker

![Implementación en una máquina virtual de Azure desde un equipo de desarrollo a través de una conexión del motor de Docker](./media/image5-4.png)

**Figura 5-4.** Implementación en una máquina virtual de Azure desde un equipo de desarrollo a través de una conexión del motor de Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Escenario B: Implementación en una máquina virtual de Azure a través de un registro de Docker

![Implementación en una máquina virtual de Azure a través de un registro de Docker](./media/image5-5.png)

**Figura 5-5.** Implementación en una máquina virtual de Azure a través de un registro de Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Escenario C: Implementación en una máquina virtual de Azure desde canalizaciones de CI/CD en Azure DevOps Services

![Implementación en una máquina virtual de Azure desde canalizaciones de CI/CD en Azure DevOps Services](./media/image5-6.png)

**Figura 5-6**. Implementación en una máquina virtual de Azure desde canalizaciones de CI/CD en Azure DevOps Services

### <a name="azure-vms-for-windows-containers"></a>Máquinas virtuales de Azure para contenedores de Windows

Las máquinas virtuales de Azure para contenedores de Windows son máquinas virtuales basadas en Windows Server 2016, Windows 10 o versiones posteriores, ambas con el motor de Docker configurado. En la mayoría de los casos, se usa Windows Server 2016 en las máquinas virtuales de Azure.

Actualmente, Azure proporciona una máquina virtual llamada **Windows Server 2016 con contenedores**. Puede usar esta máquina virtual para probar la nueva característica de contenedor de Windows Server, con Windows Server Core o Windows Nano Server. Se instalan imágenes de sistema operativo de contenedor y, después, la máquina virtual está lista para usarla con Docker.

### <a name="benefits"></a>Ventajas

Aunque los contenedores de Windows se pueden implementar en máquinas virtuales locales con Windows Server 2016, cuando se implementa en Azure, se obtiene una manera más fácil de empezar, con máquinas virtuales de contenedor de Windows Server listas para usar. También obtiene una ubicación en línea común a la que pueden acceder los evaluadores y la escalabilidad automática a través de conjuntos de escalado de máquinas virtuales de Azure.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más en profundidad en la wiki de GitHub:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Tutorial 4: Implementación de aplicaciones basadas en contenedores de Windows en Azure Container Instances (ACI)

### <a name="technical-walkthrough-availability"></a>Disponibilidad del tutorial técnico

El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:

[Implementación de aplicaciones en ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Información general

[Azure Container Instances (ACI)](/azure/container-instances/) es la manera más rápida de tener un entorno de desarrollo, pruebas y ensayo de contenedores en el que pueda implementar instancias únicas de contenedores.

### <a name="goals"></a>Objetivos

En este tutorial se muestran los principales escenarios en el momento de implementar contenedores de Windows en Azure Container Instances (ACI) y cómo puede implementar aplicaciones de eShopModernizing en ACI.

### <a name="scenarios"></a>Escenarios

Puede haber variaciones sobre la implementación de las aplicaciones de eShopModernizing en ACI, como la implementación de solo una o todas las aplicaciones (aplicación MVC, aplicación WebForms o servicio WCF). En el escenario siguiente puede ver que tanto la aplicación ASP.NET MVC como el contenedor de SQL Server se han implementado como contenedores en ACI (Azure Container Instances).

![Implementación en ACI desde un entorno de desarrollo](./media/image5-3.5.6.png)

### <a name="benefits"></a>Ventajas

Con Azure Container Instances es muy fácil crear y administrar contenedores de Docker en Azure sin tener que aprovisionar máquinas virtuales ni recurrir a un servicio de nivel superior. Con ACI, puede implementar directamente un contenedor de Windows en Azure y exponerlo a Internet con un nombre de dominio completo (FQDN) en cuestión de segundos (siempre que tenga la imagen de contenedor de Windows lista en un registro de Docker, como Docker Hub o Azure Container Registry).

### <a name="considerations"></a>Consideraciones

La implementación de contenedores de Windows con .NET Framework/ASP.NET completo o SQL Server en Azure Container Instances (ACI) no es tan rápida como la implementación en un host de Docker normal (como Windows Server 2016 con contenedores de Windows) porque la imagen de Docker se debe descargar (extraer del registro de Docker) cada vez y los tamaños de la imagen de contenedor de SQL (15,1 GB) y la imagen de contenedor de ASP.NET (13,9 GB) son considerablemente grandes. Sin embargo, es mucho más barato que mantener su propio host de Docker (Windows Server 2016 en línea permanentemente con una máquina virtual de contenedores de Windows en Azure), por no mencionar un orquestador completo como Kubernetes en Azure (AKS) que, por otro lado, es una excelente opción para las implementaciones de producción.

Como conclusión principal, el uso de Azure Container Instances es una opción muy atractiva para escenarios de desarrollo/pruebas y para canalizaciones de CI/CD.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más en profundidad en la wiki de GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Tutorial 5: Implementación de aplicaciones basadas en contenedores de Windows en Kubernetes en Azure Container Service

### <a name="technical-walkthrough-availability"></a>Disponibilidad del tutorial técnico

El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>Información general

Una aplicación basada en contenedores de Windows tendrá que usar rápidamente plataformas, con lo que se alejará aún más de las máquinas virtuales de IaaS. Esto es necesario para lograr fácilmente una alta escalabilidad y mejor escalabilidad automatizada y para obtener una mejora significativa en las implementaciones automatizadas y el control de versiones. Puede alcanzar estos objetivos si usa el orquestador [Kubernetes](https://kubernetes.io/), disponible en [Azure Container Services](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es obtener información sobre cómo implementar una aplicación basada en contenedores de Windows en Kubernetes (que también se conocen como *K8s*) en Azure Container Service. La implementación de Kubernetes desde cero es un proceso de dos pasos:

1. Implementar un clúster de Kubernetes en Azure Container Service.

2. Implementar la aplicación y los recursos relacionados en el clúster de Kubernetes.

### <a name="scenarios"></a>Escenarios

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Escenario A: Implementación directa en un clúster de Kubernetes desde un entorno de desarrollo

![Implementación directa en un clúster de Kubernetes desde un entorno de desarrollo](./media/image5-7.png)

**Figura 5-7.** Implementación directa en un clúster de Kubernetes desde un entorno de desarrollo

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Escenario B: Implementación en un clúster de Kubernetes desde canalizaciones de CI/CD en Azure DevOps Services

![Implementación en un clúster de Kubernetes desde canalizaciones de CI/CD en Azure DevOps Services](./media/image5-8.png)

**Figura 5-8.** Implementación en un clúster de Kubernetes desde canalizaciones de CI/CD en Azure DevOps Services

### <a name="benefits"></a>Ventajas

La implementación en un clúster en Kubernetes tiene muchas ventajas. La principal es que se obtiene un entorno listo para la producción en el que se puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que se desean usar (escalabilidad interna en los nodos existentes) y según el número de nodos o máquinas virtuales del clúster (escalabilidad global del clúster).

Azure Container Service optimiza las herramientas y tecnologías de código abierto populares específicamente para Azure. Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orquestador; Container Service se encarga de todo lo demás.

Con Kubernetes, los desarrolladores pueden progresar desde pensar en máquinas físicas y virtuales hasta planear una infraestructura centrada en contenedores que facilita, entre otras, las siguientes funcionalidades:

- Aplicaciones basadas en varios contenedores

- Replicación de instancias de contenedor y escalado automático horizontal

- Asignaciones de nombres y detección (por ejemplo, DNS interno)

- Equilibrio de cargas

- Actualizaciones graduales

- Distribución de secretos

- Comprobaciones de estado de aplicaciones

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más en profundidad en la wiki de GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>Tutorial 6: Implementación de aplicaciones basadas en contenedores de Windows en Azure App Service para contenedores

### <a name="technical-walkthrough-availability"></a>Disponibilidad del tutorial técnico

El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>Información general

Una aplicación sencilla en contenedor que usa contenedores de Windows se puede implementar fácilmente en Azure App Service para contenedores. Este es el enfoque recomendado para la mayoría de las aplicaciones basadas en contenedores de Windows.

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es aprender a implementar una aplicación basada en contenedores de Windows en Azure App Service para contenedores de un registro (Docker Hub o Azure Container Registry).

### <a name="scenario"></a>Escenario

![Implementación de una aplicación basada en contenedores de Windows en Azure App Service para contenedores](./media/image5-11.png)

### <a name="benefits"></a>Ventajas

La implementación en Azure App Service para contenedores ofrece las ventajas de los contenedores junto con las ventajas de PaaS de Azure App Service. El servicio de aplicación se puede escalar fácilmente de manera vertical y horizontal y puede configurarse para ajustarlo automáticamente a las exigencias cambiantes. Las actualizaciones se pueden realizar sin tiempo de inactividad y la configuración de la implementación continua desde un registro también se configura fácilmente.

### <a name="next-steps"></a>Pasos siguientes

Explore este contenido más en profundidad en la wiki de GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

> [!div class="step-by-step"]
> [Anterior](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Siguiente](conclusions.md) <!-- Next Chapter -->
