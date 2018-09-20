---
title: Introducción a la plataforma y las herramientas de Microsoft para aplicaciones en contenedor
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: bc13a0c8d6f14b8ea7ea2017009ba074f9a96ab3
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46473303"
---
# <a name="introduction-to-the-microsoft-platform-and-tools-for-containerized-apps"></a>Introducción a la plataforma y las herramientas de Microsoft para aplicaciones en contenedor


En la figura 3-1 se muestran los principales pilares del ciclo de vida de las aplicaciones de Docker clasificadas por el tipo de trabajo entregado por varios equipos (desarrollo de aplicaciones, procesos de infraestructuras de DevOps y operaciones y administración de TI). Por lo general, en la empresa, los perfiles del "rol" responsable de cada área son diferentes. Sus aptitudes también lo son.

![](./media/image1.png)

Figura 3-1: Pilares principales del ciclo de vida de las aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft

Un flujo de trabajo del ciclo de vida de aplicaciones de Docker en contenedor, en principio, puede ser prescriptivo en función de "opciones de productos predeterminadas", de tal forma que los desarrolladores pueden comenzar más rápido, pero es fundamental que, como opción alternativa, haya un marco abierto para que sea un flujo de trabajo flexible capaz de adaptarse a los diferentes contextos de cada organización o empresa. La infraestructura de flujo de trabajo (componentes y productos) debe ser lo suficientemente flexible para abarcar el entorno que cada empresa tendrá en el futuro, con la capacidad incluso de cambiar los productos de desarrollo o DevOps por otros. Esta flexibilidad, receptividad y amplia selección de tecnologías en la plataforma e infraestructura son precisamente las prioridades de Microsoft para aplicaciones de Docker en contenedor, como se explica en los capítulos siguientes.

En la tabla 3-1 se muestra que la intención de las operaciones de DevOps de Microsoft para aplicaciones de Docker en contenedor es ofrecer un flujo de trabajo abierto de DevOps para poder elegir qué productos usar para cada fase (Microsoft o terceros), al mismo tiempo que se ofrece un flujo de trabajo simplificado que proporciona "productos predeterminados" ya conectados; por tanto, puede comenzar rápidamente con el flujo de trabajo de DevOps de nivel empresarial para aplicaciones de Docker.

Tabla 3-1: Flujo de trabajo de DevOps abierto para cualquier tecnología

| administrador de flujos de trabajo | Tecnologías de Microsoft | Aplicaciones de terceros: acoplables a Azure |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Plataforma para aplicaciones de Docker   | • Microsoft Visual Studio y Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Container Service<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • Cualquier editor de código (por ejemplo, Sublime)<br /> • Cualquier lenguaje (Node.js, Java, Go, etc.)<br /> • Cualquier orquestrator y programador<br /> • Cualquier registro de Docker<br /> |
| DevOps para aplicaciones de Docker     | • Los servicios de azure DevOps<br /> • Microsoft Team Foundation Server<br /> • Azure Container Service<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion, etc.<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI, etc.<br /> • Centro de datos de Docker local, Docker Swarm, Mesos DC/OS, Kubernetes, etc.<br /> |
| Administración y supervisión  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon, Chronos, etc.<br />

La plataforma y las herramientas de Microsoft para aplicaciones de Docker en contenedor, como se define en la tabla 3-1, constan de los siguientes componentes:

-   **Plataforma de desarrollo de aplicaciones de Docker**. El desarrollo de un servicio una colección de servicios que componen una "aplicación". La plataforma de desarrollo ofrece todo el trabajo que los desarrolladores necesitan antes de insertar el código en un repositorio de código compartido. El desarrollo de servicios, implementados como contenedores, es muy similar al desarrollo de las mismas aplicaciones o servicios sin Docker. Puede continuar usando su lenguaje favorito (.NET, Node.js, Go, etc.) y el editor o IDE preferidos, como Visual Studio o Visual Studio Code. Sin embargo, en lugar de considerar Docker como un destino de implementación, los servicios se desarrollan en el entorno de Docker. El código se compila, ejecuta, prueba y depura en contenedores a nivel local, proporcionando el entorno de destino en la fase de desarrollo. Al proporcionar el entorno de destino local, los contenedores de Docker configuran lo que ayudará significativamente a mejorar el ciclo de vida de DevOps. Visual Studio y Visual Studio Code disponen de extensiones para integrar los contenedores de Docker en el proceso de desarrollo.

-   **DevOps para aplicaciones de Docker** los desarrolladores que crean aplicaciones de Docker pueden usar Azure DevOps Services o cualquier otro producto de terceros, como Jenkins elaborar una completa automatizada administración del ciclo de vida de aplicaciones (ALM).

Con los servicios de Azure DevOps, los desarrolladores pueden crear centrada en el contenedor de control de DevOps para un proceso rápido e iterativo que abarque el código fuente desde cualquier lugar (Git de Azure DevOps Services, GitHub, cualquier repositorio Git remoto o Subversion), integración continua (CI) , pruebas unitarias internas, entre las pruebas de integración de contenedores y servicios, entrega continua (CD) y la administración de versiones (RM). Los desarrolladores también pueden automatizar las versiones de las aplicaciones de Docker en Azure Container Service, desde entornos de desarrollo a almacenamiento provisional y producción.
 
-   Supervisión y administración de producción de TI.

**Administración**. Los equipos de TI pueden administrar aplicaciones y servicios de producción de varias formas:

-   **Azure Portal** Si usa orquestadores de código abierto, Azure Container Service (ACS) y las herramientas de administración de clústeres, como Docker Datacenter y Mesosphere Marathon, ayudan a configurar y mantener los entornos de Docker. Si usa Azure Service Fabric, la herramienta Service Fabric Explorer permite visualizar y configurar el clúster.

-   **Herramientas de Docker** Puede administrar las aplicaciones de contenedor con herramientas conocidas. No es necesario cambiar sus prácticas de administración de Docker existentes para mover cargas de trabajo de contenedor a la nube. Use las herramientas de administración de aplicaciones con las que ya está familiarizado y conéctelas a través de los puntos de conexión de API para el orquestador de su elección. También puede usar otras herramientas de terceros para administrar las aplicaciones de Docker, como Docker Datacenter o las herramientas de Docker para la CLI.

-   **Herramientas de código abierto** Como ACS expone los puntos de conexión de API estándar para el motor de orquestación, las herramientas más populares son compatibles con ACS y, en la mayoría de los casos, son fáciles de utilizar, incluidos los visualizadores, las herramientas de supervisión, las herramientas de línea de comandos e incluso futuras herramientas a medida que estén disponibles.

**Supervisión** Mientras ejecuta entornos de producción, puede supervisar cualquier ángulo con los siguientes elementos:

-   **Operations Management Suite (OMS)** La "solución de contenedores de OMS" puede administrar y supervisar los hosts y contenedores de Docker mostrando información sobre dónde están los contenedores y los hosts de los contenedores, qué contenedores se están ejecutando o cuáles presentan errores y los registros de demonio y de contenedores de Docker. También muestra las métricas de rendimiento, como la CPU, la memoria, la red y el almacenamiento del contenedor y los hosts, para ayudar a solucionar problemas y detectar contenedores próximos ruidosos.

-   **Application Insights** Puede supervisar las aplicaciones de Docker en producción con solo configurar su SDK en los servicios, a fin de poder obtener los datos de telemetría de las aplicaciones.

Por tanto, Microsoft ofrece una base completa para un ciclo de vida de aplicaciones de Docker en contenedor de un extremo a otro. Sin embargo, se trata de *una colección de productos y tecnologías que le permiten seleccionar, como opción, las herramientas y procesos existentes, así como realizar la integración con ellos*. La flexibilidad de un amplio enfoque y la eficacia de las funcionalidades posicionan a Microsoft como una solución eficaz para el desarrollo de aplicaciones de Docker en contenedor.

>[!div class="step-by-step"]
[Anterior](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
[Siguiente](../design-develop-containerized-apps/index.md)
