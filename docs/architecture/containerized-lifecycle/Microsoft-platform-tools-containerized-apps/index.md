---
title: Introducción a la plataforma y las herramientas de Microsoft para aplicaciones en contenedor
description: Descubra las ofertas de Microsoft compatibles con el ciclo de vida de aplicaciones de Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 8cb7870035003e956ee57684a2a2528732849379
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738447"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Introducción a la plataforma y las herramientas de Microsoft para aplicaciones en contenedor

*Visión: Creación de un ciclo de vida de aplicación en contenedor adaptable y de nivel empresarial que abarque el desarrollo, las operaciones de TI y la administración de la producción.*

En la figura 3-1 se muestran los principales pilares del ciclo de vida de las aplicaciones de Docker clasificadas por el tipo de trabajo entregado por varios equipos (desarrollo de aplicaciones, procesos de infraestructuras de DevOps y operaciones y administración de TI). Por lo general, en la empresa, los perfiles del "rol" responsable de cada área son diferentes. Sus aptitudes también lo son.

:::image type="complex" source="./media/index/microsoft-tools-contanerized-docker-app.png" alt-text="Diagrama en el que se muestran las herramientas de Microsoft necesarias para mantener aplicaciones de Docker.":::
Herramientas de Microsoft. Para la carga de trabajo de desarrollo y diseño: motor de Docker para Windows, VS y VS Code, .NET Core y Azure Kubernetes Service. Para la carga de trabajo de compilación, prueba y envío: Azure DevOps, Team Foundation Server, la CLI de Docker y Azure Kubernetes Service. Para la carga de trabajo de ejecución, supervisión y administración: Azure Monitor, Azure Portal, Azure Kubernetes Services, Service Fabric y otros orquestadores.
:::image-end:::

**Figura 3-1.** Pilares principales del ciclo de vida de las aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft.

Un flujo de trabajo del ciclo de vida de aplicaciones de Docker en contenedor, en principio, puede ser prescriptivo en función de "opciones de productos predeterminadas", de tal forma que los desarrolladores pueden comenzar más rápido, pero es fundamental que, como opción alternativa, haya un marco abierto para que sea un flujo de trabajo flexible capaz de adaptarse a los diferentes contextos de cada organización o empresa. La infraestructura de flujo de trabajo (componentes y productos) debe ser lo suficientemente flexible para abarcar el entorno que cada empresa tendrá en el futuro, con la capacidad incluso de cambiar los productos de desarrollo o DevOps por otros. Esta flexibilidad, receptividad y amplia selección de tecnologías en la plataforma e infraestructura son precisamente las prioridades de Microsoft para aplicaciones de Docker en contenedor, como se explica en los capítulos siguientes.

En la tabla 3-1 se muestra que la intención de las operaciones de DevOps de Microsoft para aplicaciones de Docker en contenedor es ofrecer un flujo de trabajo abierto de DevOps para poder elegir qué productos usar para cada fase (Microsoft o terceros), al mismo tiempo que se ofrece un flujo de trabajo simplificado que proporciona "productos predeterminados" ya conectados; por tanto, puede comenzar rápidamente con el flujo de trabajo de DevOps de nivel empresarial para aplicaciones de Docker.

**Tabla 3-1.** Flujos de trabajo de DevOps, abiertos para cualquier tecnología.

| administrador de flujos de trabajo | Tecnologías de Microsoft | Aplicaciones de terceros: acoplables a Azure |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Plataforma para aplicaciones de Docker   | • Microsoft Visual Studio y Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Kubernetes Service (AKS)<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • Cualquier editor de código (por ejemplo, Sublime)<br /> • Cualquier lenguaje (Node.js, Java, Go, etc.)<br /> • Cualquier orquestrator y programador<br /> • Cualquier registro de Docker<br /> |
| DevOps para aplicaciones de Docker     | • Azure DevOps Services<br /> • Microsoft Team Foundation Server<br /> • Azure Kubernetes Service (AKS)<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion, etc.<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI, etc.<br /> • Centro de datos de Docker local, Docker Swarm, Mesos DC/OS, Kubernetes, etc.<br /> |
| Administración y supervisión  | • Azure Monitor | • Marathon, Chronos, etc.<br />|

La plataforma y las herramientas de Microsoft para aplicaciones de Docker en contenedor, como se define en la tabla 3-1, constan de los siguientes componentes:

- **Plataforma de desarrollo de aplicaciones de Docker**. El desarrollo de un servicio una colección de servicios que componen una "aplicación". La plataforma de desarrollo ofrece todo el trabajo que los desarrolladores necesitan antes de insertar el código en un repositorio de código compartido. El desarrollo de servicios, implementados como contenedores, es similar al desarrollo de las mismas aplicaciones o servicios sin Docker. Puede seguir usando su lenguaje favorito (.NET, Node.js, Go, etc.) y su editor o IDE preferidos, como Visual Studio o Visual Studio Code. Sin embargo, en lugar de considerar Docker como un destino de implementación, los servicios se desarrollan en el entorno de Docker. El código se compila, ejecuta, prueba y depura en contenedores a nivel local, proporcionando el entorno de destino en la fase de desarrollo. Al proporcionar el entorno de destino local, los contenedores de Docker configuran lo que ayudará significativamente a mejorar el ciclo de vida de DevOps. Visual Studio y Visual Studio Code disponen de extensiones para integrar los contenedores de Docker en el proceso de desarrollo.

- **DevOps para las aplicaciones de Docker**. Los desarrolladores que crean aplicaciones de Docker pueden usar [Azure DevOps Services](https://azure.microsoft.com/services/devops/) o cualquier otro producto de terceros, como Jenkins, para crear una administración integral y automatizada del ciclo de vida de las aplicaciones.

  Con Azure DevOps Services, los desarrolladores pueden crear DevOps centradas en contenedores para un proceso rápido e iterativo que abarque el control del código fuente desde cualquier plataforma (Azure DevOps Services-Git, GitHub, cualquier repositorio Git remoto o Subversion), integración continua (CI), pruebas unitarias internas, pruebas de integración entre contenedores y servicios, entrega continua (CD) y administración de versiones. Los desarrolladores también pueden automatizar las versiones de las aplicaciones de Docker en Azure Kubernetes Service (AKS), desde entornos de desarrollo hasta almacenamiento provisional y producción.

- **Administración y supervisión**. Los equipos de TI pueden administrar y supervisar aplicaciones y servicios de producción de varias maneras, mediante la integración de ambas perspectivas en una experiencia consolidada.

  - **Azure Portal** Si usa orquestadores de código abierto, Azure Kubernetes Service (AKS), Service Fabric y otros orquestadores le ayudarán a configurar y mantener los entornos de Docker. Si usa Azure Service Fabric, la herramienta Service Fabric Explorer permite visualizar y configurar el clúster.

  - **Herramientas de Docker** Puede administrar las aplicaciones de contenedor con herramientas conocidas. No es necesario cambiar sus prácticas de administración de Docker existentes para mover cargas de trabajo de contenedor a la nube. Use las herramientas de administración de aplicaciones con las que ya está familiarizado y conéctelas a través de los puntos de conexión de API para el orquestador de su elección. También puede usar otras herramientas de terceros para administrar las aplicaciones de Docker, como Docker Datacenter o las herramientas de Docker para la CLI.

    Incluso si está familiarizado con los comandos de Linux, puede administrar las aplicaciones de contenedor mediante Microsoft Windows y PowerShell con una línea de comandos del subsistema de Linux y los productos (Docker, Kubernetes, etc.) que los clientes ejecutan en esta funcionalidad del subsistema de Linux. Más adelante en este libro obtendrá más información sobre el uso de estas herramientas en el subsistema de Linux con su sistema operativo favorito de Microsoft Windows.

  - **Herramientas de código abierto** Como AKS expone los puntos de conexión de API estándar para el motor de orquestación, las herramientas más populares son compatibles con AKS y, en la mayoría de los casos, son fáciles de usar, incluidos los visualizadores, las herramientas de supervisión, las herramientas de línea de comandos e incluso futuras herramientas a medida que estén disponibles.

  - **Azure Monitor** Se trata de una solución de Azure para supervisar todos los aspectos del entorno de producción. Puede supervisar las aplicaciones de Docker en producción con solo configurar su SDK en los servicios, a fin de obtener datos de registro generados por el sistema a partir de las aplicaciones.

Por tanto, Microsoft ofrece una base completa para un ciclo de vida de aplicaciones de Docker en contenedor de un extremo a otro. Se trata de *una colección de productos y tecnologías que le permiten seleccionar, como opción, las herramientas y procesos existentes, así como realizar la integración con ellos*. La flexibilidad de un amplio enfoque y la eficacia de las funcionalidades posicionan a Microsoft como una solución eficaz para el desarrollo de aplicaciones de Docker en contenedor.

>[!div class="step-by-step"]
>[Anterior](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Siguiente](../design-develop-containerized-apps/index.md)
