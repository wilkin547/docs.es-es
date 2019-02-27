---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Conozca los pasos para el "bucle exterior" del flujo de trabajo de DevOps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 7043f34557651c3e8e79baf263bd0bcefd5a847a
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836414"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker

Figura 5-1 presenta una representación to-end de los pasos que componen el flujo de trabajo de DevOps bucle exterior.

![Este diagrama muestra el "bucle exterior" de DevOps. Cuando se inserta código en el repositorio, una canalización de CI se inicia, a continuación, comienza la canalización de CD, donde se implementa la aplicación. Las métricas recopiladas desde las aplicaciones implementadas se alimentan en la carga de trabajo de desarrollo, donde se produce el "bucle interno", por lo que los equipos de desarrollo tienen datos reales para responder a necesidades empresariales y de usuario.](./media/image1.png)

**Figura 5-1**. Flujo de trabajo de bucle externo de DevOps para aplicaciones de Docker con herramientas de Microsoft

Ahora, vamos a examinar cada uno de estos pasos con mayor detalle.

## <a name="step-1-inner-loop-development-workflow"></a>Paso 1: Flujo de trabajo de desarrollo de bucle interno

Este paso se explica con detalle en el capítulo 4, pero, en resumen, aquí es donde empieza el bucle exterior, el momento en el que un desarrollador inserta código en el sistema de administración de control de código fuente (por ejemplo, Git) iniciar acciones de la canalización de CI.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Paso 2: Integración de Control de código fuente y administración con Azure DevOps Services y Git

En este paso, debe tener un sistema de control de versiones para recopilar una versión codificada de todo el código procedente de los desarrolladores diferentes en el equipo.

Aunque el control de código fuente (SCC) y la administración de código fuente pueden parecer instintivo desplazarse a la mayoría de desarrolladores, al crear aplicaciones de Docker en una vida de DevOps, es fundamental para hacer hincapié en que no debe enviar las imágenes de Docker con la aplicación directamente en el registro de Docker de global (como Azure Container Registry o Docker Hub) desde el equipo del desarrollador. Por el contrario, las imágenes de Docker se libere y se implementan en entornos de producción deben crearse únicamente en el código fuente que se integre en la compilación global o la canalización de CI basándose en el repositorio de código fuente (por ejemplo, Git).

Las imágenes locales, generadas por los desarrolladores, se deben utilizar por ellos cuando las pruebas con sus propios equipos. Por este motivo es fundamental contar con la canalización de DevOps activa desde el código de control de código fuente.

Azure DevOps Services y Team Foundation Server admiten Git y Team Foundation Version Control. Puede elegir entre ellas y usarlo para una experiencia de Microsoft to-end. Sin embargo, también puede administrar el código en repositorios externos (como GitHub, repositorios de Git local o Subversion) y seguir siendo capaces de conectarse a ella y obtener el código como punto de partida para la canalización de CI de DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Paso 3: Compilación de CI, integrar y probar con Azure DevOps servicios y Docker

CI ha surgido como un estándar para las pruebas de software moderno y entrega. La solución de Docker mantiene una separación clara de intereses entre los equipos de desarrollo y operaciones. La inmutabilidad de imágenes de Docker garantiza una implementación repetible entre lo que ha desarrollado, probado a través de los elementos de configuración y ejecución en producción. Motor de docker implementados en los equipos portátiles de desarrollador e infraestructura de prueba hace que los contenedores portátiles entre entornos.

En este momento, una vez que un sistema de control de versiones con el código correcto enviado, necesita un *servicio de compilación* para recoger el código y ejecutar las compilación global y las pruebas.

El flujo de trabajo interno para este paso (CI, compilación, prueba) es sobre la construcción de una canalización de CI que consta del repositorio de código (Git, etc.), el servidor de compilación (servicios de Azure DevOps), el motor de Docker y un registro de Docker.

Puede usar servicios de Azure DevOps como base para crear sus aplicaciones y la configuración de la canalización de CI y para publicar los artefactos"integrados" para un "repositorio de artefactos", que se explica en el paso siguiente.

Al usar Docker para la implementación, "los artefactos finales" implementar imágenes de Docker con la aplicación o servicios incrustadas dentro de ellos. Esas imágenes se insertan o se publican en un *Docker Registry* (un repositorio privado, como los que puede tener en Azure Container Registry, o una pública, como el registro de Docker Hub, que se utiliza habitualmente las imágenes oficiales de bases).

Este es el concepto básico: La canalización de CI será inicia mediante una confirmación en un repositorio de control de código fuente como Git. La confirmación hará que Servicios de DevOps de Azure ejecutar un trabajo de compilación dentro de un contenedor de Docker y, tras la finalización correcta de ese trabajo, insertar una imagen de Docker en el registro de Docker, como se muestra en la figura 5-2.

![La primera parte del bucle exterior implica los pasos 1 a 3, desde el código, ejecutar, depurar y, a continuación, validar el repositorio de código hasta el paso de compilación y prueba de integración continua](./media/image2.png)

**Figura 5-2**. Los pasos implicados en el elemento de configuración

Estos son los pasos básicos de flujo de trabajo de CI con Docker y los servicios de DevOps de Azure:

1. El desarrollador envía una confirmación a un repositorio de control de código fuente (Git/Azure DevOps Services, GitHub, etcetera.).

2. Si usa servicios de Azure DevOps o Git, CI está integrada, lo que significa que es tan sencilla como seleccionar una casilla en los servicios de Azure DevOps. Si usas un SCC externo (como GitHub), un `webhook` se notifíquelo a los servicios de DevOps de Azure de la actualización o inserción en Git/GitHub.

3. Servicios de Azure DevOps extrae el repositorio de control de código fuente, incluido el Dockerfile que describe la imagen, así como el código de aplicación y prueba.

4. Servicios de Azure DevOps compila una imagen de Docker y se etiqueta con un número de compilación.

5. Servicios de Azure DevOps crea una instancia del contenedor de Docker en el Host aprovisionado de Docker y ejecuta las pruebas adecuadas.

6. Si las pruebas son correctas, la imagen en primer lugar se vuelven a un nombre descriptivo para que sepa es una "compilación designada" (como "/ 1.0.0" o cualquier otra etiqueta) y, a continuación, insertan en el registro de Docker (Docker Hub, Azure Container Registry, DTR, etcetera.)

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementación de la canalización de CI con servicios de Azure DevOps y la extensión Docker para servicios de Azure DevOps

Servicios de DevOps de Azure de Visual Studio contiene plantillas de versión que puede usar en la canalización de CI/CD con la que puede crear imágenes de Docker, inserte imágenes de Docker en un registro autenticado de Docker, ejecutar imágenes de Docker o ejecutar otras operaciones que ofrece & compilación la CLI de Docker. También agrega una tarea de Docker Compose que puede usar para crear, insertar y ejecutar aplicaciones de Docker de varios contenedores o ejecutar otras operaciones de la CLI de Docker Compose, como se muestra en la figura 5-3.

![Vista del explorador de la canalización de CI de Docker en Azure DevOps](./media/image3.png)

**Figura 5-3**. La canalización de CI de Docker en servicios de DevOps de Azure incluidas las compilación & plantillas de versión y las tareas asociadas.

Puede usar estas plantillas y tareas para construir los artefactos de CI/CD para compilar / probar e implementar en Azure Service Fabric, Azure Kubernetes Service y ofertas similares.

Con estas tareas de Visual Studio Team Services, una compilación o máquina virtual Linux Docker Host aprovisionado en Azure y el registro de Docker preferido (Azure Container Registry, Docker Hub, DTR privado de Docker o cualquier otro registro de Docker) puede ensamblar su canalización de CI de Docker en un forma muy coherente.

***Requisitos:***

- Servicios de Azure DevOps, o para las instalaciones locales, Team Foundation Server 2015 Update 3 o posterior.

- Un agente de servicios de DevOps de Azure que tiene los archivos binarios de Docker.

  Una manera fácil de crear uno de estos agentes es usar Docker para ejecutar un contenedor basado en la imagen de Docker de agente de servicios de Azure DevOps.

> [! INFORMACIÓN] para leer más acerca de cómo ensamblar un elemento de configuración de Docker de servicios de Azure DevOps de canalización y ver los tutoriales, visite estos sitios:
>
> - Ejecución de un agente de Visual Studio Team Services (ahora los servicios de DevOps de Azure) como un contenedor de Docker: \
>   [*https://hub.docker.com/r/microsoft/vsts-agent/*](https://hub.docker.com/r/microsoft/vsts-agent/)
>
> - Creación de imágenes de Docker de Linux de .NET Core con los servicios de Azure DevOps: \
>   [*https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/*](https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/)
>
> - Creación de un servicio de equipo basado en Linux, Visual Studio crea la máquina con compatibilidad con Docker: \
>   [*http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support*](http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support)

### <a name="integrate-test-and-validate-multi-container-docker-applications"></a>Integrar, probar y validar las aplicaciones de varios contenedores Docker

Normalmente, la mayoría de las aplicaciones de Docker se compone de varios contenedores en lugar de un solo contenedor. Un buen ejemplo es una aplicación orientada a microservicios que tendría un contenedor por microservicio. Pero, incluso sin seguir estrictamente los patrones de enfoque de microservicios, es probable que la aplicación de Docker podría estar compuesta de varios contenedores o servicios.

Por lo tanto, después de compilar los contenedores de aplicación en la canalización de CI, también deberá implementar, integrar y probar la aplicación como un todo con todos sus contenedores dentro de un host de Docker de integración o incluso en un clúster de prueba a los que son los contenedores distribuido.

Si usa un único host, puede usar comandos de Docker como docker-compose para compilar e implementar contenedores relacionados para probar y validar el entorno de Docker en una sola máquina virtual. Sin embargo, si está trabajando con un clúster de orchestrator como DC/OS, Kubernetes o Docker Swarm, deberá implementar los contenedores a través de un mecanismo diferente o orchestrator, según su programador/clústeres seleccionado.

Continuación se muestran varios tipos de pruebas que se pueden ejecutar en contenedores de Docker:

- Pruebas unitarias para contenedores de Docker

- Probar los grupos de aplicaciones interrelacionadas o microservicios

- Probar en las versiones de producción y "chivato"

Lo importante es que, al ejecutar pruebas funcionales e integración, debe ejecutar las pruebas desde fuera de los contenedores. Pruebas no están incluidas o ejecutar en los contenedores que se va a implementar, porque los contenedores se basan en las imágenes estáticas que deben ser exactamente igual que las implementará en producción.

Es una opción práctica cuando las pruebas más escenarios avanzados, como la inclusión de varios clústeres (probar el clúster, clúster de ensayo y producción) publicar las imágenes a un registro, por lo que se puede probar en varios clústeres.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Insertar la imagen de Docker de la aplicación personalizada en el registro de Docker global

Después de que las imágenes de Docker se han probado y validado, desea etiquetar y publicarlos en el registro de Docker. El registro de Docker es una pieza fundamental en el ciclo de vida de la aplicación de Docker, porque es la ubicación central desde donde se almacena la prueba personalizada (también conocido como "designadas imágenes") para implementarse en entornos de producción y control de calidad.

De forma similar a cómo el código de aplicación almacenado en el repositorio de control de código fuente (Git, etc.) es el "origen de verdad", el registro de Docker es el "origen de verdad" de la aplicación binaria o bits para su implementación en los entornos de producción o control de calidad.

Normalmente, desea tener sus repositorios privados para sus imágenes personalizadas en un repositorio privado en Azure Container Registry en un registro de forma local como Docker Trusted Registry o en un registro de nube pública con acceso restringido (por ejemplo Docker Hub), aunque en este último caso, si el código no está abierto, debe confiar en seguridad del proveedor. En cualquier caso, el método que utilice es similar y se basa en el `docker push` de comandos, tal como se muestra en la figura 5-4.

![En el paso 3 para generar integración y pruebas (CI) podría publicar las imágenes de docker resultante a un registro privado o público.](./media/image4.png)

**Figura 5-4**. Publicar imágenes personalizadas en el registro de Docker

Hay varias ofertas de los registros de Docker de proveedores de nube como Azure Container Registry, registro de contenedor de servicios Web de Amazon, Google Container Registry, registro del muelle y así sucesivamente.

Uso de las tareas de Docker, puede insertar un conjunto de imágenes de servicio definidos por un `docker-compose.yml` de archivos, con varias etiquetas, en un registro autenticado de Docker (como Azure Container Registry), tal como se muestra en la figura 5-5.

![Vista de explorador del paso para publicar imágenes en un registro de DevOps de Azure.](./media/image5.png)

**Figura 5-5**. Uso de servicios de Azure DevOps para publicar imágenes personalizadas a un registro de Docker

> [! INFORMACIÓN] para obtener más información sobre Azure Container Registry, consulte <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Paso 4: CD, implementar

La inmutabilidad de imágenes de Docker garantiza una implementación repetible, con lo que ha desarrollado, probado a través de los elementos de configuración y ejecución en producción. Una vez que las imágenes de Docker de la aplicación publicadas en el registro de Docker (privado o público), puede implementarlas en los entornos de varias que pueda haber (producción, control de calidad, almacenamiento provisional, etc.) desde la canalización de CD mediante los servicios de Azure DevOps las tareas de canalización o servicios de Release Management de Azure DevOps.

Sin embargo, en este punto depende de qué tipo de aplicación de Docker está implementando. Implementar una aplicación sencilla (desde una implementación y la composición de punto de vista) como un monolítica implementada y de aplicaciones que incluyen algunos contenedores o servicios a unos servidores o máquinas virtuales es diferente de la implementación de una aplicación más compleja, como un aplicación orientada a microservicios con capacidades de hiperescala. Estos dos escenarios se explican en las secciones siguientes.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Implementación de aplicaciones de Docker en varios entornos de Docker compuestas

Veamos primero el escenario menos complejo: implementar en hosts de Docker simple (máquinas virtuales o servidores) en un entorno único o varios entornos (control de calidad, ensayo y producción). En este escenario, internamente la canalización de CD puede usar docker-compose (de las tareas de implementación de servicios de Azure DevOps) para implementar las aplicaciones de Docker con su conjunto relacionado de contenedores y servicios, como se muestra en la figura 5-6.

![Implementar el CD de paso (4) puede publicar en diferentes entornos, como q & a, ensayo y producción.](./media/image6.png)

**Figura 5-6**. Implementación de contenedores de aplicación para el registro de los entornos de host de Docker simple

Figura 5-7 destaca cómo pueden conectar los elementos de configuración de compilación para entornos de control de calidad y pruebas a través de servicios de Azure DevOps haciendo clic en Docker Compose en el cuadro de diálogo Agregar tarea. Sin embargo, al implementar en entornos de ensayo o producción, normalmente usaría las características de Release Management para administrar varios entornos (como el control de calidad, ensayo y producción). Si va a implementar en hosts de Docker único, que utiliza los servicios de Azure DevOps tarea "Docker Compose" (que está invocando el `docker-compose up` comando en segundo plano). Si va a implementar en Azure Container Service, utiliza la tarea de implementación de Docker, como se explica en la sección siguiente.

![Vista del explorador de agregar una tarea de Docker Compose.](./media/image7.png)

**Figura 5-7**. Agregar una tarea de Docker Compose en una canalización de servicios de Azure DevOps

Cuando se crea una versión en los servicios de Azure DevOps, toma un conjunto de artefactos de entrada. Estos artefactos están diseñados para ser inmutable durante la vigencia de la versión, en todos los entornos. Cuando introduzca contenedores, los artefactos de entrada identifican imágenes en un registro para implementar. Dependiendo de cómo se identifican estas imágenes, no se garantiza que no cambian a lo largo de la duración de la versión, el más evidente caso es cuando se hace referencia `myimage:latest` desde un `docker-compose` archivo.

Las plantillas de Azure DevOps Services proporcionan resúmenes de la capacidad de generar los artefactos de compilación que contienen la imagen específica del registro que se garantiza que identifican la misma imagen binaria. Estos son lo que realmente desea utilizar como entrada para una versión.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Administración de versiones para entornos de Docker mediante el uso de servicios de Release Management de Azure DevOps

A través de las plantillas de servicios de Azure DevOps, puede crear una nueva imagen, publicarlo en un registro de Docker, se ejecutan en hosts de Linux o Windows y usar comandos como `docker-compose` para implementar varios contenedores como una aplicación completa, todo ello gracias a la Azure DevOps Servicios de capacidades de Release Management destinadas a varios entornos, como se muestra en la figura 5-8.

![Vista del explorador de Azure DevOps, configuración de Docker compose de versiones.](./media/image8.png)

**Figura 5-8**. Configurar tareas de Docker Compose de servicios de DevOps de Azure desde Release Management para servicios de Azure DevOps

Sin embargo, tenga en cuenta que el escenario se muestra en la figura 5-6 y se implementa en la figura 5-8 es una sencilla (que se está implementando para máquinas virtuales y hosts de Docker único y habrá un único contenedor o una instancia por imagen) y probablemente debe usarse solo para desarrollo o prueba de sce narios. En la mayoría de los escenarios de producción empresarial, querría tener alta disponibilidad (HA) y fácil de administrar la escalabilidad al equilibrar la carga entre varios nodos, los servidores y las máquinas virtuales, además de "inteligente las conmutaciones por error" por lo que si un servidor o un nodo se produce un error, sus servicios y contenedores se moverá a otro servidor host o máquina virtual. En ese caso, necesita las tecnologías más avanzadas como clústeres de contenedor, los orquestadores y los programadores. Por lo tanto, la forma de implementar dichos clústeres es controlando los escenarios avanzados se explica en la sección siguiente.

### <a name="deploying-docker-applications-to-docker-clusters"></a>Implementación de aplicaciones de Docker en clústeres de Docker

La naturaleza de las aplicaciones distribuidas requiere recursos de proceso que también se distribuyen. Para que las capacidades de escala de producción, debe tener la agrupación en clústeres las capacidades que ofrecen alta escalabilidad y alta disponibilidad basada en recursos agrupados.

Podría implementar manualmente los contenedores en esos clústeres desde una herramienta CLI o una interfaz de usuario web, pero debe reservar ese tipo de trabajo manual para las pruebas de implementación detectar o con fines de administración, como el escalado horizontal o supervisión.

Desde un punto de vista de CD y servicios de Azure DevOps en concreto, puede ejecutar tareas de implementación creados especialmente desde los entornos de administración de versiones de servicios de Azure DevOps que va a implementar las aplicaciones en contenedores para clústeres distribuidos en contenedor Servicio, como se muestra en la figura 5-9.

![Implementar el CD de paso (4) también puede publicar en clústeres a través de los orquestadores.](./media/image9.png)

**Figura 5-9**. Implementación de aplicaciones distribuidas en Container Service

Inicialmente, al implementar en ciertas clústeres u orquestadores, tradicionalmente usaría los scripts de implementación específicos y mecanismos por cada orquestador (es decir, Kubernetes y Service Fabric tienen mecanismos de implementación diferentes) en lugar de la más sencilla y fácil de usar `docker-compose` herramienta basada en el `docker-compose.yml` archivo de definición. Sin embargo, gracias a la tarea de Azure DevOps servicios de implementación de Docker, se muestra en la figura 5-10, ahora también puede implementar en los orquestadores compatibles si solo se usa el familiar `docker-compose.yml` archivo porque la herramienta realiza esa traducción de"" por usted (desde su `docker-compose.yml`archivo al formato necesario para el orquestador).

![Vista de explorador del catálogo de tareas en Azure, DevOps, que muestra el Docker de la tarea de implementación.](./media/image10.png)

**Figura 5-10**. Agregar la tarea de implementación de Docker al entorno de RM

Figura 5-11 se muestra cómo puede modificar la tarea de implementación de Docker y especificar el tipo de destino (Azure Container Service DC/OS, en este caso), el archivo de Docker Compose y la conexión de registro de Docker (como Azure Container Registry o Docker Hub). Se trata de la tarea que recuperará las imágenes de Docker listos para usar personalizadas que desee implementar como contenedores en el clúster.

![Vista del explorador de Azure DevOps, implemente en la definición de tarea de orchestrator.](./media/image11.png)

**Figura 5-11**. Implementación de docker implementar tareas definición a Azure Container Service DC/OS

> [! INFORMACIÓN] para obtener más información acerca de la canalización de CD con Docker y servicios de DevOps de Azure, visite <https://azure.microsoft.com/services/devops/pipelines>

## <a name="step-5-run-and-manage"></a>Paso 5: Ejecutar y administrar

Porque está ejecutando y administración de aplicaciones en producción de la empresa nivel es un asunto principal de sí mismo y debido al tipo de operaciones y personas que trabajan en ese nivel (operaciones de TI), así como el ámbito de esta área de gran tamaño, nos hemos dedicado todo el contenido a continuación capítulo a explicarlo.

## <a name="step-6-monitor-and-diagnose"></a>Paso 6: Supervisión y diagnóstico

Este tema se trata en el siguiente capítulo como parte de las tareas que realiza en sistemas de producción; Sin embargo, es importante resaltar que deben suministrar los conocimientos obtenidos en este paso hasta que el equipo de desarrollo para que la aplicación se mejora constantemente. Desde ese punto de vista, también forma parte de DevOps, aunque las tareas y las operaciones se realizan normalmente por TI.

Solo cuando la supervisión y el diagnóstico son 100% en el ámbito de DevOps son los procesos de supervisión y análisis realizadas por el equipo de desarrollo frente a entornos de prueba o beta. Esto se hace mediante la realización de pruebas de carga o mediante la supervisión de la versión beta o entornos de preguntas y respuestas, donde los evaluadores de beta están tratando de las nuevas versiones.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
