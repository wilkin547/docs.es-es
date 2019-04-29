---
title: Introducción a la plataforma y las herramientas de Microsoft para aplicaciones en contenedor
description: Familiarícese con las ofertas de Microsoft para admitir el ciclo de vida de las aplicaciones de Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 8536703a520434c0e393c5f46005c2ac02d5d849
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934671"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Introducción a la plataforma de Microsoft y herramientas para aplicaciones en contenedor

*Visión: Crear un adaptable, de nivel empresarial en contenedores ciclo de vida de aplicación que abarca el desarrollo, operaciones de TI y administración de producción.*

En la figura 3-1 se muestran los principales pilares del ciclo de vida de las aplicaciones de Docker clasificadas por el tipo de trabajo entregado por varios equipos (desarrollo de aplicaciones, procesos de infraestructuras de DevOps y operaciones y administración de TI). Por lo general, en la empresa, los perfiles del "rol" responsable de cada área son diferentes. Sus aptitudes también lo son.

![Herramientas de Microsoft. Para la carga de trabajo de desarrollo y diseño: Motor de docker para Windows, VS y VS Code, .NET Core, Azure Kubernetes Service. Para la carga de trabajo de compilación o prueba de envío: Azure DevOps, Team Foundation Server, Docker CLI de Azure Kubernetes Service. Para ejecutar, supervisar o administrar cargas de trabajo: Azure Monitor, servicios de Kubernetes de Azure Portal de Azure, Service Fabric, otros orquestadores.](./media/image1.png)

**Figura 3-1.** Pilares principales del ciclo de vida de aplicaciones en contenedores de Docker con herramientas y plataforma de Microsoft

Un flujo de trabajo del ciclo de vida de Docker en contenedor puede ser preceptiva inicialmente según "de forma predeterminada opciones de productos," lo que facilita a los desarrolladores empezar a trabajar con mayor rapidez, pero es fundamental que debajo del capó debe haber un marco abierto para que sea un flujo de trabajo flexible capaz de adaptarse a los diferentes contextos de cada organización o empresa. La infraestructura de flujo de trabajo (componentes y productos) debe ser lo suficientemente flexible para abarcar el entorno que cada empresa tendrá en el futuro, con la capacidad incluso de cambiar los productos de desarrollo o DevOps por otros. Esta flexibilidad, receptividad y amplia selección de tecnologías en la plataforma e infraestructura son precisamente las prioridades de Microsoft para aplicaciones de Docker en contenedor, como se explica en los capítulos siguientes.

En la tabla 3-1 se muestra que la intención de las operaciones de DevOps de Microsoft para aplicaciones de Docker en contenedor es ofrecer un flujo de trabajo abierto de DevOps para poder elegir qué productos usar para cada fase (Microsoft o terceros), al mismo tiempo que se ofrece un flujo de trabajo simplificado que proporciona "productos predeterminados" ya conectados; por tanto, puede comenzar rápidamente con el flujo de trabajo de DevOps de nivel empresarial para aplicaciones de Docker.

**Tabla 3-1.** Abra los flujos de trabajo de DevOps para cualquier tecnología

| administrador de flujos de trabajo | Tecnologías de Microsoft | Aplicaciones de terceros: acoplables a Azure |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Plataforma para aplicaciones de Docker   | • Microsoft Visual Studio y Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Container Service<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • Cualquier editor de código (por ejemplo, Sublime)<br /> • Cualquier lenguaje (Node.js, Java, Go, etc.)<br /> • Cualquier orquestrator y programador<br /> • Cualquier registro de Docker<br /> |
| DevOps para aplicaciones de Docker     | • Los servicios de azure DevOps<br /> • Microsoft Team Foundation Server<br /> • Azure Container Service<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion, etc.<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI, etc.<br /> • Centro de datos de Docker local, Docker Swarm, Mesos DC/OS, Kubernetes, etc.<br /> |
| Administración y supervisión  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon, Chronos, etc.<br />

La plataforma y las herramientas de Microsoft para aplicaciones de Docker en contenedor, como se define en la tabla 3-1, constan de los siguientes componentes:

- **Plataforma de desarrollo de aplicaciones de Docker**. El desarrollo de un servicio una colección de servicios que componen una "aplicación". La plataforma de desarrollo ofrece todo el trabajo que los desarrolladores necesitan antes de insertar el código en un repositorio de código compartido. Desarrollo de servicios, implementado como contenedores, es similar al desarrollo de las mismas aplicaciones o servicios sin Docker. Seguir usando su idioma preferido (. NET, Node.js, Go, etc.) y el editor que prefiera o el IDE como Visual Studio o Visual Studio Code. Sin embargo, en lugar de considerar Docker como un destino de implementación, los servicios se desarrollan en el entorno de Docker. El código se compila, ejecuta, prueba y depura en contenedores a nivel local, proporcionando el entorno de destino en la fase de desarrollo. Al proporcionar el entorno de destino local, los contenedores de Docker configuran lo que ayudará significativamente a mejorar el ciclo de vida de DevOps. Visual Studio y Visual Studio Code disponen de extensiones para integrar los contenedores de Docker en el proceso de desarrollo.

- **DevOps para aplicaciones de Docker** pueden usar los desarrolladores que crean aplicaciones de Docker [servicios de Azure DevOps](https://azure.microsoft.com/services/devops/) o cualquier otro producto de terceros, como Jenkins, para elaborar un ciclo de vida de aplicaciones automatizadas completas Management (ALM).

  Con los servicios de Azure DevOps, los desarrolladores pueden crear centrada en el contenedor de control de DevOps para un proceso rápido e iterativo que abarque el código fuente desde cualquier lugar (Git de Azure DevOps Services, GitHub, cualquier repositorio Git remoto o Subversion), integración continua (CI) , pruebas unitarias internas, las pruebas de integración entre Multi-Container o servicio, entrega continua (CD) y la administración de versiones (RM). Los desarrolladores también pueden automatizar las versiones de las aplicaciones de Docker en Azure Container Service, desde entornos de desarrollo a almacenamiento provisional y producción.

- **Administración y supervisión** TI puede administrar y supervisar las aplicaciones de producción y los servicios de varias maneras, la integración de ambas perspectivas en una experiencia consolidada.

  - **Portal de Azure** si usa orquestadores de código abierto, Azure Kubernetes Service (AKS), Service Fabric y otros orquestadores le ayudan a configurar y mantener los entornos de Docker. Si usa Azure Service Fabric, la herramienta Service Fabric Explorer permite visualizar y configurar el clúster.

  - **Herramientas de Docker** Puede administrar las aplicaciones de contenedor con herramientas conocidas. No es necesario cambiar sus prácticas de administración de Docker existentes para mover cargas de trabajo de contenedor a la nube. Use las herramientas de administración de aplicaciones con las que ya está familiarizado y conéctelas a través de los puntos de conexión de API para el orquestador de su elección. También puede usar otras herramientas de terceros para administrar las aplicaciones de Docker, como Docker Datacenter o las herramientas de Docker para la CLI. 

    Incluso si está familiarizado con los comandos de Linux, puede administrar sus aplicaciones de contenedor con Microsoft Windows y PowerShell con una línea de comandos del subsistema de Linux y los productos (Docker, Kubernetes...) los clientes que ejecutan esta capacidad del subsistema de Linux. Aprenderá más acerca de cómo utilizar estas herramientas en el subsistema de Linux con el sistema operativo Windows de Microsoft favoritos más adelante en este libro.

  - **Herramientas de código abierto** AKS porque expone los puntos de conexión de API estándares para el motor de orquestaciones, las herramientas más populares son compatibles con AKS y, en la mayoría de los casos, funcionarán desde el cuadro, incluidos los visualizadores, supervisión, herramientas de línea de comandos e incluso, herramientas futuras conforme estén disponibles.

  - **Azure Monitor** soluciones de Azure es para supervisar todos los ángulos del entorno de producción. Puede supervisar aplicaciones Docker en producción mediante la configuración solo de su SDK en los servicios para que puedan obtener datos de registro generados por el sistema de las aplicaciones.

Por tanto, Microsoft ofrece una base completa para un ciclo de vida de aplicaciones de Docker en contenedor de un extremo a otro. Sin embargo, resulta *una colección de productos y tecnologías que permiten seleccionar opcionalmente y integrarla con los de herramientas y procesos*. La flexibilidad de un amplio enfoque y la eficacia de las funcionalidades posicionan a Microsoft como una solución eficaz para el desarrollo de aplicaciones de Docker en contenedor.

>[!div class="step-by-step"]
>[Anterior](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Siguiente](../design-develop-containerized-apps/index.md)
