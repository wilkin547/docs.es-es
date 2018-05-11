---
title: Tutoriales y technical obtienen información general de introducción
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Tutoriales y technical obtienen información general de introducción
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 27de9d1c5475855a22f2d8a3518982605277f6d9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Tutoriales y technical obtienen información general de introducción

Para limitar el tamaño de este libro electrónico, documentación técnica adicional y los tutoriales completos se encontraban disponibles en un repositorio de GitHub. La serie de tutoriales que se describen en este capítulo en línea trata el programa de instalación paso a paso de los entornos de varios que se basan en los contenedores de Windows y la implementación en Azure.

Las siguientes secciones explican lo que cada tutorial trata sobre sus objetivos y la visión de alto nivel y proporciona un diagrama de las tareas que están implicados. Puede obtener los tutoriales por sí mismos en el *eShopModernizing* wiki de repositorio de GitHub de aplicaciones en [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).

## <a name="technical-walkthrough-list"></a>Lista de tutoriales técnicos

Los siguientes tutoriales iniciada por get proporcionan orientación técnica de coherente y completo para las aplicaciones de ejemplo que puede levantar y desplazar mediante el uso de contenedores y, a continuación, mueva con varias opciones de implementación de Azure.

Cada uno de los siguientes tutoriales utiliza el nuevo eShopLegacy y eShopModernizing aplicaciones de ejemplo, que están disponibles en GitHub en [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).

- **Paseo por aplicaciones heredadas de compras (aplicaciones de línea de base para modernizar)**

- **Incluya las aplicaciones web existentes en ASP.NET (formularios Web Forms y MVC) con contenedores de Windows**

- **Incluya los servicios WCF existentes (aplicaciones de N niveles) con contenedores de Windows**

- **Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure**

- **Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en el servicio de contenedor de Azure**

- **Implementar las aplicaciones de Windows basada en contenedores en Azure Service Fabric.**


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Tutorial 1: Paseo de compras de aplicaciones heredadas

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnica

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:

[tutoriales de wiki de eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a>Información general

En este tutorial, puede explorar la implementación inicial de tres aplicaciones heredadas de ejemplo. Las dos primeras aplicaciones web de ejemplo tienen una arquitectura monolítica y creadas utilizando ASP.NET clásico. Una aplicación se basa en ASP.NET 4.x MVC; la segunda aplicación se basa en formularios Web Forms ASP.NET 4.x. La tercera aplicación es una aplicación de 3 niveles compuesta por una aplicación de formularios Windows Forms de cliente y un servidor [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) servicio.

Todas estas aplicaciones están disponibles en la [repositorio de GitHub de eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Objetivos

El objetivo principal de este tutorial es simplemente para familiarizarse con estas aplicaciones y con su código y la configuración. Puede configurar las aplicaciones para que puedan generarán y utilizar los datos simulados, sin utilizar la base de datos SQL, con fines de prueba. Esta configuración opcional se basa en la inserción de dependencias, de una manera desconectada.

### <a name="scenario-1-aspnet-web-apps"></a>Escenario 1: Las aplicaciones Web ASP.NET

La siguiente ilustración muestra el escenario sencillo de las aplicaciones de web ASP.NET heredados originales.

> ![Escenario de arquitectura simple de la original heredado las aplicaciones web ASP.NET](./media/image5-1.png)
>

Desde una perspectiva de dominio empresarial, ambas aplicaciones ofrecen el mismo catálogo de características de administración. Los miembros del equipo de enterprise compras utilizaría la aplicación para ver y editar el catálogo de productos. 

La ilustración siguiente muestra las capturas de pantalla de la aplicación inicial.

![Aplicaciones de MVC de ASP.NET y formularios Web Forms de ASP.NET (tecnologías existentes/heredado)](./media/image5-2.png)

Dependencias en ASP.NET 4.x o versiones anteriores (ya sea para MVC o Web Forms) significa que estas aplicaciones no se ejecutarán en .NET Core a menos que el código se ha reescrito completamente mediante el uso de núcleo de ASP.NET MVC. 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Escenario 2: Servicio WCF y aplicación de cliente de WinForms (aplicación de nivel 3)

La siguiente ilustración muestra el escenario sencillo de la aplicación heredada de 3 niveles original.

> ![Escenario de arquitectura simple de la aplicación de 3 niveles heredada original con un servicio WCF y una aplicación de cliente de WinForms](./media/image5-1.5.png)
>

### <a name="benefits"></a>Ventajas

Las ventajas de este tutorial son sencillas: simplemente familiarizarse con el código y aplicaciones iniciales.

### <a name="next-steps"></a>Pasos siguientes

Explorar este contenido más detallada en el sitio wiki de GitHub:

  - [La visita de la línea de base de ASP.NET MVC y aplicaciones de formularios Web Forms "heredadas"](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [Paseo en el servicio WCF de línea de base y la aplicación de formularios Windows Forms (nivel 3) "heredado"](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Tutorial 2: Incluya las aplicaciones de .NET existentes con contenedores de Windows

### <a name="overview"></a>Información general

Utilice contenedores de Windows para mejorar la implementación de aplicaciones .NET existentes, como las basadas en MVC, formularios Web Forms o WCF, para entornos de prueba, desarrollo y producción.

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es mostrar varias opciones para containerizing una aplicación existente de .NET Framework. Puede realizar lo siguiente:

- Incluya la aplicación mediante el uso de [Visual Studio 2017 Tools para Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (2017 de Visual Studio o versiones posteriores).

- Incluya la aplicación agregando manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)y, a continuación, usar el [CLI de Docker](https://docs.docker.com/engine/reference/commandline/cli/).

- Incluya la aplicación mediante el uso de la [Img2Docker](https://github.com/docker/communitytools-image2docker-win) herramienta (una herramienta de código abierto de Docker).

En este tutorial se centra en Visual Studio de 2017 Tools para el enfoque de Docker, pero los otros dos enfoques son muy parecidos en relación con usando Dockerfiles.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Escenario 1: Aplicaciones web ASP.NET en contenedores

La figura siguiente muestra el escenario para aplicaciones de aplicaciones web heredadas de compras en contenedores.

> ![Diagrama de arquitectura simplificada de en contenedores de aplicaciones de ASP.NET en un entorno de desarrollo](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a>Escenario 2: Servicio WCF en contenedores

La figura siguiente muestra el escenario para una aplicación de 3 niveles con un servicio WCF en contenedores. 

> ![Diagrama de arquitectura de servicio WCF en contenedores en un entorno de desarrollo ha simplificado](./media/image5-3.5.png)
>

### <a name="benefits"></a>Ventajas

Existen ventajas a la ejecución de la aplicación monolítica en un contenedor. En primer lugar, cree una imagen de la aplicación. Desde ese momento, cada implementación se ejecuta en el mismo entorno. Cada contenedor usa la misma versión de sistema operativo, tiene la misma versión de dependencias instalada, usa la misma versión de .NET framework y se compila mediante el mismo proceso. Básicamente, controlar las dependencias de la aplicación mediante una imagen de Docker. Las dependencias de viajan con la aplicación al implementar los contenedores.

Otra ventaja adicional es que los programadores pueden ejecutar la aplicación en el entorno coherente que se ofrecen los contenedores de Windows. Los problemas que aparezcan únicamente con determinadas versiones se pueden observar inmediatamente, en lugar de así como la exposición en un entorno de ensayo o de producción. Las diferencias en los entornos de desarrollo que usan los miembros del equipo de desarrollo importan menor cuando las aplicaciones que se ejecutan en ellos.

Aplicaciones en contenedores también tienen una curva de escalado horizontal más plana. Aplicaciones en contenedores le permiten tener más aplicaciones e instancias de servicio (basados en contenedores) en una máquina virtual o la máquina física en comparación con las implementaciones de aplicaciones normal por máquina. Esto se traduce en mayor densidad y menos requiere recursos, especialmente cuando se usa orchestrators como Kubernetes o Service Fabric.

Inclusión en contenedores, en situaciones ideales, no requiere realizar cambios en el código de aplicación (C\#). En la mayoría de los escenarios, solo tiene los archivos de metadatos de implementación de Docker (archivos Dockerfiles y Docker Compose).

### <a name="next-steps"></a>Pasos siguientes

Explorar este contenido más detallada en el sitio wiki de GitHub:

  - [Cómo incluya las aplicaciones web de .NET Framework con contenedores de Windows y Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [Agregar compatibilidad de Docker a un servicio WCF](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Tutorial 3: Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnica

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Información general

Implementación en un host de Docker en una máquina Virtual de 2016 de servidor de Windows (VM) de Azure le permite configurar rápidamente entornos de desarrollo/pruebas/staging. También proporciona un lugar común para evaluadores o los usuarios empresariales validar la aplicación. Máquinas virtuales también pueden ser infraestructura válido como un entorno de producción del servicio (IaaS).

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es mostrar las alternativas varios que tiene al implementar contenedores de Windows en las máquinas virtuales de Azure que se basan en Windows Server 2016 o versiones posteriores.

### <a name="scenarios"></a>Escenarios

En este tutorial se tratan varios escenarios.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Escenario A: implementar en una VM de Azure desde un equipo de desarrollo a través de la conexión con el motor de Docker

![Implementar en una VM de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker](./media/image5-4.png)

> **Figura 5-4.** Implementar en una VM de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Escenario B: implementar en una máquina virtual de Azure a través de un registro de Docker

![Implementar en una máquina virtual de Azure a través de un registro de Docker](./media/image5-5.png)

> **Figura 5-5.** Implementar en una máquina virtual de Azure a través de un registro de Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>Escenario C: implementar en una VM de Azure desde el elemento de configuración/CD canalizaciones en Visual Studio Team Services

![Implementar en una VM de Azure de CI/CD canalizaciones en Visual Studio Team Services](./media/image5-6.png)

> **Figura 5-6**. Implementar en una VM de Azure de CI/CD canalizaciones en Visual Studio Team Services

### <a name="azure-vms-for-windows-containers"></a>Máquinas virtuales de Azure para los contenedores de Windows

Máquinas virtuales de Azure para contenedores de Windows son máquinas virtuales basadas en Windows Server 2016, Windows 10 o versiones posteriores, ambos con el motor de Docker configurar. En la mayoría de los casos, se utiliza Windows Server 2016 en las máquinas virtuales de Azure.

Actualmente, Azure proporciona una máquina virtual denominada **Windows Server 2016 con contenedores**. Puede usar esta máquina virtual para probar la nueva característica de contenedor de Windows Server, con Windows Server Core o Nano Server de Windows. Imágenes del sistema operativo de contenedor se instalan y, a continuación, la máquina virtual está lista para su uso con Docker.

### <a name="benefits"></a>Ventajas

Aunque los contenedores de Windows se pueden implementar en local 2016 máquinas virtuales Windows Server, cuando se implementa en Azure, obtendrá una manera más fácil para empezar a trabajar con máquinas virtuales de contenedor de listos para usar Windows Server. También obtendrá una ubicación en línea común que es accesible para evaluadores y escalabilidad automática a través de conjuntos de escalas de máquina virtual de Azure.

### <a name="next-steps"></a>Pasos siguientes

Explorar este contenido más detallada en el sitio wiki de GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Tutorial 4: Implementar las aplicaciones de Windows basada en contenedores en instancias de contenedor de Azure (ACI)

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnica

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:

[Implementar las aplicaciones en ACI (instancias de contenedor de Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Información general

[Instancias de contenedor de Azure (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) es la forma más rápida con un entorno de desarrollo/pruebas/staging contenedores en el que puede implementar instancias únicas de contenedores.

### <a name="goals"></a>Objetivos

Este tutorial muestra los principales escenarios que al implementar contenedores de Windows para instancias de contenedor de Azure (ACI) y cómo puede implementar aplicaciones eShopModernizing en ACI.

### <a name="scenarios"></a>Escenarios

Puede haber variaciones sobre cómo implementar las aplicaciones de eShopModernizing en ACI como la implementación de uno o todos los de las aplicaciones (aplicaciones MVC, aplicación de formularios Web Forms o servicio WCF). En el siguiente escenario que se muestra a continuación puede ver la aplicación de ASP.NET MVC y el contenedor de SQL Server de ellos implementan como contenedores en ACI (instancias de contenedor de Azure).

![Implementar en ACI desde un entorno de desarrollo](./media/image5-3.5.6.png)

### <a name="benefits"></a>Ventajas

Instancias de contenedor Azure resulta muy sencillo crear y administrar contenedores de Docker en Azure, sin tener que aprovisionar máquinas virtuales o adoptar un servicio de nivel superior. Con ACI, se puede implementar un contenedor de Windows en Azure directamente y exponerlo a internet con un nombre de dominio completo (FQDN) en cuestión de segundos (siempre que tenga la imagen de contenedor de Windows listo en un registro de Docker como Docker Hub o un contenedor de Azure Registro).

### <a name="considerations"></a>Consideraciones

Implementar contenedores de Windows con cualquier versión completa de .NET Framework o ASP.NET o SQL Server en instancias de contenedor de Azure (ACI) no es bastante tan rápido como la implementación en un Host Docker normales (por ejemplo, Windows Server 2016 con contenedores de Windows) porque la imagen de Docker debe ser Descargar (extraigan desde el registro de Docker) cada vez y los tamaños de la imagen de contenedor SQL (15.1 GB) y la imagen de contenedor ASP.NET (13.9 GB) son significativamente grandes, sin embargo, es mucho más costoso que el mantenimiento de su propio host de docker (permanentemente en línea Windows Server 2016 con la máquina virtual de contenedores de Windows en Azure) no para hacer mención a un orchestrator todo como Kubernetes en Azure (AKS/ACS) o Azure Service Fabric que son, por otro lado, las opciones excelentes para las implementaciones de producción.

Como término principal, con instancias de contenedor de Azure es una opción muy atractiva para escenarios de desarrollo/pruebas y para las canalizaciones de CI/CD.

## <a name="next-steps"></a>Pasos siguientes

Explorar este contenido más detallada en el sitio wiki de GitHub: 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Tutorial 5: Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en el servicio de contenedor de Azure

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnica

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Información general

Una aplicación que se basa en los contenedores de Windows rápidamente necesite usan las plataformas, aleja el aún más de las máquinas virtuales IaaS. Esto es necesario para lograr fácilmente alta escalabilidad y mejor automatizada escalabilidad y para una mejora considerable en automatizar las implementaciones y control de versiones. Puede lograr estos objetivos utilizando el orchestrator [Kubernetes](https://kubernetes.io/), disponible en [servicios de contenedor de Azure](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es aprender a implementar una aplicación basada en el contenedor de Windows para Kubernetes (también denominada *K8s*) en el servicio de contenedor de Azure. Implementación a Kubernetes desde cero es un proceso de dos pasos:

1.  Implementar un clúster de Kubernetes al servicio de contenedor de Azure.

2.  Implementar la aplicación y los recursos relacionados en el clúster Kubernetes.

### <a name="scenarios"></a>Escenarios

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Escenario A: implementar directamente a un clúster de Kubernetes desde un entorno de desarrollo

![Implementar directamente en un clúster Kubernetes desde un entorno de desarrollo](./media/image5-7.png)

> **Figura 5-7.** Implementar directamente en un clúster Kubernetes desde un entorno de desarrollo

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>Escenario B: implementar en un clúster Kubernetes desde el elemento de configuración/CD canalizaciones en Team Services

![Implementar en un clúster de Kubernetes de canalizaciones de CI/CD en Team Services](./media/image5-8.png)

> **Figura 5-8.** Implementar en un clúster de Kubernetes de canalizaciones de CI/CD en Team Services

### <a name="benefits"></a>Ventajas

Hay muchas ventajas a la implementación en un clúster en Kubernetes. La mayor ventaja es que se obtiene de un entorno para entornos de producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de nodos o máquinas virtuales en el clúster ( escalabilidad global del clúster).

Servicio de contenedor de Azure optimiza las tecnologías y herramientas de código abierto populares específicamente para Azure. Obtener una solución abierta que ofrece la portabilidad tanto para los contenedores de la configuración de la aplicación. Seleccione el tamaño, el número de hosts, y el servicio de contenedor-herramientas de orchestrator controla todo lo demás.

Con Kubernetes, los desarrolladores pueden progreso de pensar en máquinas físicas y virtuales, para planear una infraestructura centrada en el contenedor que facilita las siguientes capacidades, entre otros:

- Aplicaciones basadas en varios contenedores

- La replicación de instancias de contenedor y ajuste automático de escala horizontal

- Nomenclatura y detectar (por ejemplo, DNS interno)

- Equilibrio de carga

- Actualizaciones graduales

- Distribuir secretos

- Comprobaciones de estado de aplicación

## <a name="next-steps"></a>Pasos siguientes

Explorar este contenido más detallada en el sitio wiki de GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Tutorial 6: Implementar las aplicaciones de Windows basada en contenedores en Azure Service Fabric.

### <a name="technical-walkthrough-availability"></a>Disponibilidad de tutorial técnica

El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Información general

Una aplicación basada en los contenedores de Windows rápidamente debe usar plataformas, aleja el aún más de las máquinas virtuales IaaS. Esto es necesario para lograr fácilmente alta escalabilidad y mejor automatizada escalabilidad y para una mejora considerable en automatizar las implementaciones y control de versiones. Puede lograr estos objetivos con el orchestrator Azure Service Fabric, que está disponible en la nube de Azure, pero también disponible para su uso local, o incluso en una nube pública diferente.

### <a name="goals"></a>Objetivos

El objetivo de este tutorial es aprender a implementar una aplicación basada en el contenedor de Windows a un clúster de Service Fabric en Azure. Implementación a Service Fabric desde cero es un proceso de dos pasos:

1.  Implementar un clúster de Service Fabric en Azure (o en un entorno diferente).

2.  Implementar la aplicación y los recursos relacionados en el clúster de Service Fabric.

### <a name="scenarios"></a>Escenarios

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Escenario A: implementar directamente a un clúster de Service Fabric desde un entorno de desarrollo

![Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo](./media/image5-9.png)

> **Figura 5-9.** Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>Escenario B: implementar en un clúster de Service Fabric desde el elemento de configuración/CD canalizaciones en Team Services

![Implementar en un clúster de Service Fabric de CI/CD canalizaciones en Visual Studio Team Services](./media/image5-10.png)

> **Figura 5-10.** Implementar en un clúster de Service Fabric de CI/CD canalizaciones en Visual Studio Team Services

## <a name="benefits"></a>Ventajas

Las ventajas de la implementación en un clúster de Service Fabric son similares a las ventajas de usar Kubernetes. Sin embargo, no obstante, es que Service Fabric es un entorno de producción más maduro para aplicaciones de Windows en comparación con Kubernetes, que se encuentra en una fase beta para contenedores de Windows en Kubernetes versión 1.9 (diciembre de 2017). Kubernetes es un entorno más maduro para Linux.

La principal ventaja del uso de Azure Service Fabric es que se obtiene de un entorno para entornos de producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de los nodos o máquinas virtuales del clúster (escalabilidad global del clúster).

Azure Service Fabric ofrece portabilidad de los contenedores y para la configuración de la aplicación. Puede tener un tejido de servicio de clúster en Azure, o instalar localmente en su propio centro de datos. Incluso puede instalar un clúster de Service Fabric en una nube diferente, como [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

Con Service Fabric, los desarrolladores pueden progreso de pensar en máquinas físicas y virtuales para planear una infraestructura centrada en el contenedor que facilita las siguientes capacidades, entre otros:

- Aplicaciones basadas en varios contenedores.

- Replicación de instancias de contenedor y ajuste automático de escala horizontal.

- Nomenclatura y detectar (por ejemplo, DNS interno).

- Equilibrio de carga.

- Actualizaciones graduales.

- Distribuir secretos.

- Comprueba el estado de la aplicación.

Las siguientes capacidades son exclusivas de Service Fabric (en comparación con otras orchestrators):

- Capacidad de servicios con estado, a través del modelo de aplicación de servicios de confianza.

- Patrón de actores a través del modelo de aplicación de Reliable Actors.

- Implementar procesos descubierto, además de los contenedores de Windows o Linux.

- Advanced actualizaciones graduales y comprobaciones de mantenimiento.

### <a name="next-steps"></a>Pasos siguientes

Explorar este contenido más detallada en el sitio wiki de GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[Anterior](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Siguiente](conclusions.md)
