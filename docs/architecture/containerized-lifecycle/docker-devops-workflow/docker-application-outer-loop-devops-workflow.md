---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Conozca los pasos del "bucle exterior" del flujo de trabajo de DevOps.
ms.date: 02/15/2019
ms.openlocfilehash: 735f92c00cd6279649ec3b0c35cfb00543f21a8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936782"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker

En la figura 5-1 se muestra una representación de un extremo a otro de los pasos que componen el flujo de trabajo del bucle externo de DevOps. Muestra el "bucle externo" de DevOps. Cuando se inserta código en el repositorio, se inicia una canalización de CI y, después, comienza la canalización de CD, donde se implementa la aplicación. Las métricas recopiladas de las aplicaciones implementadas se envían a la carga de trabajo de desarrollo, donde se produce el "bucle interno", a fin de que los equipos de desarrollo tengan datos reales para responder a las necesidades del usuario y de la organización.

![Diagrama que muestra los 6 pasos del flujo de trabajo del bucle externo de DevOps.](./media/docker-application-outer-loop-devops-workflow/overview-dev-ops-outter-loop-workflow.png)

**Figura 5-1**. Flujo de trabajo del bucle externo de DevOps para aplicaciones de Docker con herramientas de Microsoft

Examinemos cada uno de estos pasos con mayor detalle.

## <a name="step-1-inner-loop-development-workflow"></a>Paso 1: flujo de trabajo de desarrollo del bucle interno

Este paso se explica con detalle en el capítulo 4, pero, a modo de resumen, aquí es donde empieza el bucle externo. En este momento, el desarrollador inserta código en el sistema de administración de control de código fuente (por ejemplo, GIT), lo que da inicio a acciones de la canalización de CI.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Paso 2: integración y administración del control de código fuente con Azure DevOps Services y GIT

En este paso, debe contar con un sistema de control de versiones para recopilar una versión consolidada de todo el código procedente de los diferentes desarrolladores del equipo.

Aunque el control de código fuente (SCC) y la administración de código fuente pueden parecerles algo instintivo a la mayoría de los desarrolladores, al crear aplicaciones de Docker en un ciclo de vida de DevOps, es fundamental hacer hincapié en que no se deben enviar las imágenes de Docker con la aplicación directamente al registro de Docker de global (como Azure Container Registry o Docker Hub) desde el equipo del desarrollador. Por el contrario, las imágenes de Docker que van a lanzarse e implementarse en entornos de producción deben crearse únicamente en el código fuente que se está integrando en la canalización de compilación o CI global, en función del repositorio de código fuente (por ejemplo, GIT).

Las imágenes locales que generen los desarrolladores se usarán exclusivamente cuando estos prueben sus equipos. Por este motivo es fundamental que la canalización de DevOps esté activada desde el código de SCC.

Azure DevOps Services y Team Foundation Server admiten GIT y Control de versiones de Team Foundation. Puede elegir cualquiera de ellos y usarlo para disfrutar de una experiencia de Microsoft de un extremo a otro. Aun así, también puede administrar el código en repositorios externos (como GitHub, repositorios de GIT locales o Subversion) y seguir siendo capaz de conectarse a él y obtener el código como punto de partida para la canalización de CI de DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Paso 3: compilación, CI, integración y prueba con Azure DevOps Services y Docker

CI se ha convertido en un estándar para las pruebas y la entrega de software moderno. La solución de Docker mantiene una clara separación de intereses entre los equipos de desarrollo y operaciones. La inmutabilidad de las imágenes de Docker garantiza una implementación repetible entre lo que se ha desarrollado, lo que se ha probado a través de CI y lo que se ha ejecutado en producción. El motor de Docker implementado en los portátiles de los desarrolladores y la infraestructura de prueba hace que los contenedores puedan transportarse a distintos entornos.

Llegado a este punto, cuando tenga un sistema de control de versiones con el código correcto enviado, necesitará un *servicio de compilación* para tomar el código y ejecutar la compilación y las pruebas globales.

El flujo de trabajo interno para este paso (CI, compilación, prueba) consiste en la construcción de una canalización de CI que consta del repositorio de código (GIT, etc.), el servidor de compilación (Azure DevOps Services), el motor de Docker y un registro de Docker.

Puede usar Azure DevOps Services como base para compilar las aplicaciones y configurar la canalización de CI, así como para publicar los "artefactos" compilados en un "repositorio de artefactos", como se explica en el paso siguiente.

Al usar Docker para la implementación, los "artefactos finales" que se implementarán son imágenes de Docker en las que se ha insertado la aplicación o los servicios. Dichas imágenes se insertan o se publican en un *registro de Docker* (un repositorio privado, como los que se pueden tener en Azure Container Registry, o un repositorio público, como el registro de Docker Hub, que suele usarse para imágenes base oficiales).

Este es el concepto básico: la canalización de CI la iniciará una confirmación en un repositorio de SCC, como GIT. La confirmación hará que Azure DevOps Services ejecute un trabajo de compilación dentro de un contenedor de Docker y, tras la finalización correcta de ese trabajo, insertará una imagen de Docker en el registro de Docker, como se muestra en la figura 5-2. La primera parte del bucle externo implica los pasos del 1 a 3, es decir, primero el paso de programación, ejecución, depuración y validación, después el repositorio de código y, por último, la compilación, la CI y la prueba.

![Diagrama que muestra los tres pasos implicados en el flujo de trabajo de CI.](./media/docker-application-outer-loop-devops-workflow/continuous-integration-steps.png)

**Figura 5-2**. Pasos del proceso de CI

Estos son los pasos básicos del flujo de trabajo de CI con Docker y Azure DevOps Services:

1. El desarrollador envía una confirmación a un repositorio de SCC (GIT/Azure DevOps Services, GitHub, etc.).

2. Si usa Azure DevOps Services o GIT, CI estará integrada, lo que significa que es tan fácil como activar una casilla en Azure DevOps Services. Si usa SCC externo (como GitHub), un `webhook` notificará a Azure DevOps Services la actualización o la insertará en GIT/GitHub.

3. Azure DevOps Services extrae el repositorio de SCC, incluido el archivo Dockerfile que describe la imagen, así como el código de la aplicación y la prueba.

4. Azure DevOps Services compila una imagen de Docker y la etiqueta con un número de compilación.

5. Azure DevOps Services crea una instancia del contenedor de Docker en el host de Docker aprovisionado y ejecuta las pruebas adecuadas.

6. Si las pruebas son correctas, primero se vuelve a etiquetar la imagen con un nombre descriptivo para que se sepa que es una "compilación designada" (como "/1.0.0" o cualquier otra etiqueta) y, después, se inserta en el registro de Docker (Docker Hub, Azure Container Registry, DTR, etc.)

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementación de la canalización de CI con Azure DevOps Services y la extensión de Docker para Azure DevOps Services

Azure DevOps Services de Visual Studio contiene plantillas de compilación y versión que se pueden usar en la canalización de CI/CD para crear imágenes de Docker, insertarlas en un registro autenticado de Docker, ejecutarlas o llevar a cabo otras operaciones que ofrece la CLI de Docker. También agrega una tarea de Docker Compose que se puede usar para compilar, insertar y ejecutar aplicaciones de Docker de varios contenedores, o bien para ejecutar otras operaciones de la CLI de Docker Compose, como se muestra en la figura 5-3.

![Captura de pantalla de la canalización de CI de Docker en Azure DevOps.](./media/docker-application-outer-loop-devops-workflow/docker-ci-pipeline-azure-devops.png)

**Figura 5-3**. Canalización de CI de Docker en Azure DevOps Services, incluidas las plantillas de compilación y versión y tareas asociadas

Puede usar estas plantillas y tareas a fin de construir artefactos de CI/CD para realizar la compilación, prueba e implementación en Azure Service Fabric, Azure Kubernetes Service y ofertas similares.

Con estas tareas de Visual Studio Team Services, un host o máquina virtual de Docker de Linux de compilación aprovisionados en Azure y su registro de Docker preferido (Azure Container Registry, Docker Hub, DTR de Docker privado o cualquier otro registro de Docker), puede ensamblar su canalización de CI de Docker de forma coherente.

***Requisitos:***

- Azure DevOps Services o, para instalaciones locales, Team Foundation Server 2015 Update 3 o una versión posterior.

- Un agente de Azure DevOps Services que tenga los archivos binarios de Docker.

  Una manera fácil de crear uno de estos agentes consiste en usar Docker para ejecutar un contenedor basado en la imagen de Docker del agente de Azure DevOps Services.

> [INFORMACIÓN] Para obtener más detalles sobre cómo ensamblar una canalización de CI de Docker de Azure DevOps Services y consultar los tutoriales, visite estos sitios:
>
> - Ejecución de un agente de Visual Studio Team Services (ahora Azure DevOps Services) como un contenedor de Docker: \
>   <https://hub.docker.com/_/microsoft-azure-pipelines-vsts-agent>
>
> - Creación de imágenes de Docker de Linux para .NET Core con Azure DevOps Services: \
>   <https://docs.microsoft.com/archive/blogs/stevelasker/building-net-core-linux-docker-images-with-visual-studio-team-services>
>
> - Creación de una máquina de compilación de Visual Studio Team Services basada en Linux con compatibilidad con Docker: \
>   <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multi-container-docker-applications"></a>Integración, prueba y validación de aplicaciones de Docker de varios contenedores

Normalmente, la mayoría de las aplicaciones de Docker se componen de varios contenedores, en lugar de uno solo. Un buen ejemplo es una aplicación orientada a microservicios que tenga un contenedor por microservicio. Pero incluso si no se sigue estrictamente una filosofía basada en microservicios, es probable que una aplicación de Docker esté compuesta de varios contenedores o servicios.

Por lo tanto, después de compilar los contenedores de aplicación en la canalización de CI, también deberá implementar, integrar y probar la aplicación en su conjunto con todos sus contenedores en un host de Docker de integración, o incluso en un clúster de prueba en el que se distribuyan los contenedores.

Si usa un solo host, puede recurrir a comandos de Docker como docker-compose para compilar e implementar contenedores relacionados a fin de probar y validar el entorno de Docker en una sola máquina virtual. Aun así, si trabaja con un clúster de orquestador como DC/OS, Kubernetes o Docker Swarm, deberá implementar los contenedores mediante un mecanismo u orquestador diferentes, en función del clúster o programador que haya seleccionado.

A continuación se muestran varios tipos de pruebas que se pueden ejecutar en contenedores de Docker:

- Pruebas unitarias para contenedores de Docker

- Pruebas de grupos de aplicaciones o microservicios interrelacionados

- Pruebas en versiones de producción y de lanzamiento controlado

Lo importante al ejecutar las pruebas funcionales y de integración es que las realice desde fuera de los contenedores. Las pruebas no se incluyen ni se ejecutan en los contenedores que va a implementar, porque los contenedores se basan en imágenes estáticas que deberían ser exactamente iguales a las que implementará en producción.

Una opción práctica al realizar las pruebas en escenarios más avanzados, como cuando se incluyen varios clústeres (clúster de prueba, de almacenamiento provisional y de producción), consiste en publicar las imágenes en un registro, de modo que se pueda probar en varios clústeres.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Inserción de imágenes de Docker de aplicación personalizadas en el registro de Docker global

Una vez que se hayan probado y validado las imágenes de Docker, querrá etiquetarlas y publicarlas en el registro de Docker. El registro de Docker es un elemento fundamental en el ciclo de vida de la aplicación de Docker, ya que es la ubicación central en la que se almacena la prueba personalizada (también conocida como "imagen designada") que se implementará en entornos de producción y control de calidad.

Del mismo modo que el código de la aplicación almacenado en el repositorio de SCC (GIT, etc.) es el "origen fiable", el registro de Docker es el "origen fiable" de la aplicación binaria o los bits que se implementarán en los entornos de producción o control de calidad.

Normalmente, le interesa tener los repositorios privados para las imágenes personalizadas en un repositorio privado en Azure Container Registry, en un registro local como Docker Trusted Registry o en un registro de nube pública con acceso restringido (por ejemplo, Docker Hub), aunque en este último caso, si no se trata de código abierto, debe confiar en la seguridad del proveedor. En cualquier caso, el método que use es similar y se basa en el comando `docker push`, como se muestra en la figura 5-4.

![Diagrama que muestra la extracción de imágenes personalizadas a un registro de contenedor.](./media/docker-application-outer-loop-devops-workflow/docker-push-custom-images.png)

**Figura 5-4**. Publicación de imágenes personalizadas en el registro de Docker

En el paso 3, para la compilación, la integración y las pruebas (CI), podría interesarle publicar las imágenes de Docker resultantes en un registro privado o público. Existen proveedores de nube que ofrecen diversos registros de Docker, como Azure Container Registry, Amazon Web Services Container Registry, Google Container Registry, Quay Registry, etc.

Mediante el uso de tareas de Docker, puede insertar un conjunto de imágenes de servicio definidas por un archivo `docker-compose.yml`, con varias etiquetas, en un registro de Docker autenticado (como Azure Container Registry), tal como se muestra en la figura 5-5.

![Captura de pantalla que muestra el paso para publicar imágenes en un registro.](./media/docker-application-outer-loop-devops-workflow/publish-custom-image-to-docker-registry.png)

**Figura 5-5**. Uso de Azure DevOps Services para publicar imágenes personalizadas en un registro de Docker

> [INFORMACIÓN] Para obtener más detalles sobre Azure Container Registry, vea <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Paso 4: CD e implementación

La inmutabilidad de las imágenes de Docker garantiza una implementación repetible entre lo que se ha desarrollado, lo que se ha probado a través de CI y lo que se ha ejecutado en producción. Una vez que las imágenes de Docker de la aplicación se han publicado en el registro de Docker (ya sea privado o público), puede implementarlas en los diversos entornos que tenga (producción, control de calidad, almacenamiento provisional, etc.) desde la canalización de CD mediante el uso de tareas de canalización de Azure DevOps Services o Release Management de Azure DevOps Services.

Aun así, este paso depende del tipo de aplicación de Docker que vaya a implementar. La implementación de una aplicación sencilla (desde el punto de vista de la composición y la implementación), por ejemplo, una aplicación monolítica que contenga unos pocos contenedores o servicios y que esté implementada en unos pocos servidores o máquinas virtuales, es diferente de la implementación de una aplicación más compleja, como una aplicación orientada a microservicios con funcionalidades de hiperescala. Estos dos escenarios se explican en las secciones siguientes.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Implementación de aplicaciones compuestas de Docker en varios entornos de Docker

Veamos primero el escenario menos complejo: la implementación en hosts simples de Docker (máquinas virtuales o servidores) en uno o varios entornos (control de calidad, almacenamiento provisional y producción). En este escenario, la canalización de CD puede usar internamente docker-compose (desde las tareas de implementación de Azure DevOps Services) para implementar las aplicaciones de Docker con su conjunto relacionado de contenedores y servicios, como se muestra en la figura 5-6.

![Diagrama que muestra el paso de implementación de CD que se implementa en tres entornos.](./media/docker-application-outer-loop-devops-workflow/deploy-app-containers-to-docker-host-environments.png)

**Figura 5-6**. Implementación de contenedores de aplicación en el registro de entornos de host de Docker simple

En la figura 5-7 se muestra cómo se pueden conectar la compilación y CI con entornos de control de calidad y pruebas a través de Azure DevOps Services si se hace clic en Docker Compose en el cuadro de diálogo Agregar tarea. Aun así, al realizar la implementación en entornos de almacenamiento provisional o producción, normalmente usará las características de Release Management para administrar varios entornos (como control de calidad, almacenamiento provisional y producción). Si lleva a cabo la implementación en hosts de Docker únicos, lo hará mediante la tarea "Docker Compose" de Azure DevOps Services (que invoca el comando `docker-compose up` en segundo plano). Si va a proceder a la implementación en Azure Kubernetes Service (AKS), usará la tarea de implementación de Docker, como se explica en la sección siguiente.

![Captura de pantalla que muestra el cuadro de diálogo Add tasks (Agregar tareas) de la tarea Docker Compose.](./media/docker-application-outer-loop-devops-workflow/add-tasks-docker-compose.png)

**Figura 5-7**. Adición de una tarea de Docker Compose en una canalización Azure DevOps Services

Cuando se crea una versión en Azure DevOps Services, se toma un conjunto de artefactos de entrada. Estos artefactos están diseñados para ser inmutables durante la vigencia de la versión y en todos los entornos. Al introducir contenedores, los artefactos de entrada identifican las imágenes de un registro que se van a implementar. Según cómo se identifiquen estas imágenes, no se garantiza que no vayan a cambiar durante la vigencia de la versión. El caso más evidente es cuando se hace referencia a `myimage:latest` desde un archivo `docker-compose`.

Las plantillas de Azure DevOps Services permiten generar artefactos de compilación que contienen resúmenes de las imágenes específicas del registro, con la garantía de que identifican de manera única cada imagen binaria. Esto es lo que realmente le interesa usar como entrada para una versión.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Administración de versiones para entornos de Docker mediante el uso de Release Management de Azure DevOps Services

A través de las plantillas de Azure DevOps Services, puede crear una imagen, publicarla en un registro de Docker, ejecutarla en hosts de Linux o Windows y usar comandos como `docker-compose` para implementar varios contenedores como una aplicación completa, y todo ello gracias a las funcionalidades de Release Management de Azure DevOps Services destinadas a diversos entornos, como se muestra en la figura 5-8.

![Captura de pantalla que muestra la configuración de las versiones de Docker Compose.](./media/docker-application-outer-loop-devops-workflow/configure-docker-compose-release.png)

**Figura 5-8**. Configuración de tareas de Docker Compose de Azure DevOps Services desde Release Management para Azure DevOps Services

Aun así, tenga en cuenta que el escenario que se muestra en la figura 5-6 y que se implementa en la figura 5-8 es sencillo (se implementa en hosts y máquinas virtuales únicos de Docker y solo habrá un contenedor o instancia por imagen) y probablemente solo debería usarse para escenarios de desarrollo o prueba. En la mayoría de los escenarios de producción empresariales, le interesará tener alta disponibilidad y escalabilidad fácil de administrar mediante el equilibrio de carga entre varios nodos, servidores y máquinas virtuales, así como "conmutaciones por error inteligentes" de modo que, si se produce un error en un servidor o un nodo, sus servicios y contenedores se moverán a otro servidor host o máquina virtual. En ese caso, necesita tecnologías más avanzadas, como clústeres de contenedores, orquestadores y programadores. Así pues, la forma de implementar dichos clústeres consiste en controlar los escenarios avanzados que se explican en la sección siguiente.

### <a name="deploying-docker-applications-to-docker-clusters"></a>Implementación de aplicaciones de Docker en clústeres de Docker

La naturaleza de las aplicaciones distribuidas requiere recursos de proceso también distribuidos. Para disponer de funcionalidades a escala de producción, debe tener funcionalidades de agrupación en clústeres que proporcionen alta escalabilidad y alta disponibilidad en función de los recursos agrupados.

Podría implementar contenedores manualmente en esos clústeres desde una herramienta de CLI o una interfaz web, pero debe reservar este tipo de trabajo manual para detectar las pruebas de implementación o con fines de administración, como el escalado horizontal o la supervisión.

Desde el punto de vista de CD, y más concretamente de Azure DevOps Services, puede ejecutar tareas de implementación creadas de forma especial desde los entornos de Release Management de Azure DevOps Services que vayan a implementar las aplicaciones en contenedores en clústeres distribuidos en Container Service, como se muestra en la figura 5-9.

![Diagrama que muestra el paso de la implementación de CD que se implementa en los orquestadores.](./media/docker-application-outer-loop-devops-workflow/cd-deploy-to-orchestrators.png)

**Figura 5-9**. Implementación de aplicaciones distribuidas en Container Service

En principio, al implementar en ciertos clústeres u orquestadores, tradicionalmente se usarían mecanismos y scripts de implementación específicos por cada orquestador (es decir, Kubernetes y Service Fabric tienen mecanismos de implementación diferentes), en lugar de la herramienta `docker-compose` (más sencilla y fácil de usar) basada en el archivo de definición `docker-compose.yml`. Aun así, gracias a la tarea de implementación de Docker de Azure DevOps Services, que aparece en la figura 5-10, ahora también puede realizar la implementación en los orquestadores compatibles mediante el archivo `docker-compose.yml`, que ya conoce, puesto que la herramienta realiza automáticamente la "traducción" (del archivo `docker-compose.yml` al formato que requiere el orquestador).

![Captura de pantalla que muestra la tarea Implementar en Kubernetes.](./media/docker-application-outer-loop-devops-workflow/add-deploy-to-kubernetes-task.png)

**Figura 5-10**. Adición de la tarea Implementar en Kubernetes al entorno

En la figura 5-11 se muestra cómo se puede modificar la tarea Implementar en Kubernetes con las secciones disponibles para la configuración. Esta es la tarea que recuperará las imágenes de Docker personalizadas listas para usar que se implementarán como contenedores en el clúster.

![Captura de pantalla que muestra la configuración de la tarea Implementar en Kubernetes.](./media/docker-application-outer-loop-devops-workflow/edit-deploy-to-kubernetes-task.png)

**Figura 5-11**. Definición de la tarea de implementación de Docker implementada en ACS DC/OS

> [INFORMACIÓN] Para obtener más detalles sobre la canalización de CD con Azure DevOps Services y Docker, visite <https://azure.microsoft.com/services/devops/pipelines>.

## <a name="step-5-run-and-manage"></a>Paso 5: ejecución y administración

Dado que la ejecución y la administración de aplicaciones a nivel de producción empresarial es un asunto de gran importancia por sí mismo, y dado el tipo de operaciones y personas que trabajan en este nivel (operaciones de TI), así como el extenso ámbito de esta cuestión, el próximo capítulo está dedicado al completo a explicarlo.

## <a name="step-6-monitor-and-diagnose"></a>Paso 6: Supervisión y diagnóstico

Este tema también se trata en el capítulo siguiente como parte de las tareas que lleva a cabo el equipo de TI en los sistemas de producción, pero es importante destacar que los conocimientos obtenidos en este paso deben remitirse al equipo de desarrollo para garantizar una mejora constante de la aplicación. Desde ese punto de vista, también forma parte de DevOps, aunque las tareas y las operaciones suele realizarlas el equipo de TI.

Solo cuando la supervisión y el diagnóstico se encuentran exclusivamente en el ámbito de DevOps la tarea de llevar a cabo los procesos de supervisión y análisis en los entornos beta o de prueba recae en el equipo de desarrollo. Para ello, realizan pruebas de carga o supervisan los entornos beta o de control de calidad en los que se prueban las versiones nuevas.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
