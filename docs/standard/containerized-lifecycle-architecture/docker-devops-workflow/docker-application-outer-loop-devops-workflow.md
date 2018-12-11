---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/10/2018
ms.openlocfilehash: 37dd5481da571be56f134a5e142b7ba46427d7d8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143654"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker

Figura 5-1 presenta una representación to-end de los pasos que componen el flujo de trabajo de DevOps bucle exterior.

![](./media/image1.png)

Figura 5-1: Flujo de trabajo de bucle externo de DevOps para aplicaciones de Docker con herramientas de Microsoft

Ahora, vamos a examinar cada uno de estos pasos con mayor detalle.

## <a name="step-1-inner-loop-development-workflow"></a>Paso 1: Flujo de trabajo de desarrollo de bucle interno

Este paso se explica con detalle en el capítulo 4, pero, en resumen, aquí es donde empieza el bucle exterior, el momento en el que un desarrollador inserta código en el sistema de administración de control de código fuente (por ejemplo, Git) iniciar acciones de la canalización de CI.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Paso 2: Integración de Control de código fuente y administración con Azure DevOps Services y Git

En este paso, debe tener un sistema de control de versiones para recopilar una versión codificada de todo el código procedente de los desarrolladores diferentes en el equipo.

Aunque el control de código fuente (SCC) y la administración de código fuente pueden parecer instintivo desplazarse a la mayoría de desarrolladores, al crear aplicaciones de Docker en una vida de DevOps, es fundamental para hacer hincapié en que no debe enviar las imágenes de Docker con la aplicación directamente en el registro de Docker de global (como Azure Container Registry o Docker Hub) desde el equipo del desarrollador. Por el contrario, las imágenes de Docker se libere y se implementan en entornos de producción deben crearse únicamente en el código fuente que se integre en la compilación global o la canalización de CI basándose en el repositorio de código fuente (por ejemplo, Git).

Las imágenes locales generadas por los desarrolladores a sí mismos deben usarse solo por los desarrolladores al realizar pruebas en sus propios equipos. Esto es por eso es fundamental contar con la canalización de DevOps activa desde el código de control de código fuente.

Azure DevOps Services y Team Foundation Server admiten Git y Team Foundation Version Control. Puede elegir entre ellas y usarlo para una experiencia de Microsoft to-end. Sin embargo, también puede administrar el código en repositorios externos (como GitHub, repositorios de Git local o Subversion) y seguir siendo capaces de conectarse a ella y obtener el código como punto de partida para la canalización de CI de DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Paso 3: Compilación de CI, integrar y probar con Azure DevOps servicios y Docker

CI ha surgido como un estándar para las pruebas de software moderno y entrega. La solución de Docker mantiene una separación clara de intereses entre los equipos de desarrollo y operaciones. La inmutabilidad de imágenes de Docker garantiza una implementación repetible entre lo que ha desarrollado, probado a través de los elementos de configuración y ejecución en producción. Motor de docker implementados en los equipos portátiles de desarrollador e infraestructura de prueba hace que los contenedores portátiles entre entornos.

En este momento, una vez que un sistema de control de versiones con el código correcto enviado, necesita un *servicio de compilación* para recoger el código y ejecutar las compilación global y las pruebas.

El flujo de trabajo interno para este paso (CI, compilación, prueba) es sobre la construcción de una canalización de CI que consta del repositorio de código (Git, etc.), el servidor de compilación (servicios de Azure DevOps), el motor de Docker y un registro de Docker.

Puede usar servicios de Azure DevOps como base para crear sus aplicaciones y la configuración de la canalización de CI y para publicar los artefactos"integrados" para un "repositorio de artefactos", que se explica en el paso siguiente.

Al usar Docker para la implementación, "los artefactos finales" implementar imágenes de Docker con la aplicación o servicios incrustadas dentro de ellos. Esas imágenes se insertan o se publican en un *Docker Registry* (un repositorio privado, como los que puede tener en Azure Container Registry, o una pública, como el registro de Docker Hub, que se utiliza habitualmente las imágenes oficiales de bases).

Este es el concepto básico: La canalización de CI será inicia mediante una confirmación en un repositorio de control de código fuente como Git. La confirmación hará que Servicios de DevOps de Azure ejecutar un trabajo de compilación dentro de un contenedor de Docker y, tras la finalización correcta de ese trabajo, insertar una imagen de Docker en el registro de Docker, como se muestra en la figura 5-2.

![](./media/image2.png)

Figura 5-2: Los pasos implicados en el elemento de configuración

Estos son los pasos básicos de flujo de trabajo de CI con Docker y los servicios de DevOps de Azure:

1.  El desarrollador envía una confirmación a un repositorio de control de código fuente (Git/Azure DevOps Services, GitHub, etcetera.).

2.  Si usa servicios de Azure DevOps o Git, CI está integrada, lo que significa que es tan sencilla como seleccionar una casilla en los servicios de Azure DevOps. Si usas un SCC externo (como GitHub), un *webhook* se notifíquelo a los servicios de DevOps de Azure de la actualización o inserción en Git/GitHub.

3.  Servicios de Azure DevOps extrae el repositorio de control de código fuente, incluido el DockerFile que describe la imagen, así como el código de aplicación y prueba.

4.  Servicios de Azure DevOps compila una imagen de Docker y se etiqueta con un número de compilación.

5.  Servicios de Azure DevOps crea una instancia del contenedor de Docker en el Host aprovisionado de Docker y ejecuta las pruebas adecuadas.

6.  Si las pruebas son correctas, la imagen en primer lugar se vuelven a un nombre descriptivo para que sepa es una "compilación designada" (como "/ 1.0.0" o cualquier otra etiqueta) y, a continuación, insertan en el registro de Docker (Docker Hub, Azure Container Registry, DTR, etcetera.)

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementación de la canalización de CI con servicios de Azure DevOps y la extensión Docker para servicios de Azure DevOps

El [extensión de Docker de servicios de Azure DevOps](https://aka.ms/vstsdockerextension) agrega una tarea a la canalización de CI con el que puede crear imágenes de Docker, inserte imágenes de Docker en un registro autenticado de Docker, ejecutar imágenes de Docker o ejecutar otras operaciones de Docker CLI. También agrega una tarea de Docker Compose que puede usar para crear, insertar y ejecutar aplicaciones de Docker de varios contenedores o ejecutar otras operaciones de la CLI de Docker Compose, como se muestra en la figura 5-3.

![](./media/image3.png)

Figura 5-3: La canalización de CI de Docker en los servicios de Azure DevOps

La extensión de Docker puede utilizar los puntos de conexión de servicio para hosts de Docker y de contenedor o los registros de imágenes. El valor predeterminado de las tareas al uso de un host de Docker local si está disponible (Esto requiere actualmente un agente de servicios de Azure DevOps personalizado); en caso contrario, requieren que proporcione una conexión de host de Docker. Las acciones que dependen de que se autentica con un registro de Docker, como la inserción de una imagen, requieren que proporcione a un Docker conexión de registro.

La extensión de Docker de servicios de Azure DevOps instala los componentes siguientes en su cuenta de servicios de Azure DevOps:

-   Un punto de conexión de servicio para conectarse a un registro de Docker

-   Un punto de conexión de servicio para conectarse a un Host de contenedor de Docker

-   Una tarea de Docker para hacer lo siguiente:

-   Crear una imagen

-   Insertar una imagen o un repositorio en un registro

-   Ejecutar una imagen en un contenedor

-   Ejecutar un comando de Docker

-   Una tarea de Docker Compose para ejecutar un comando de Docker Compose

Con estas tareas de servicios de Azure DevOps, una compilación o máquina virtual Linux Docker Host aprovisionado en Azure y el registro de Docker preferido (Azure Container Registry, Docker Hub, DTR privado de Docker o cualquier otro registro de Docker) puede ensamblar su canalización de CI de Docker en un muy manera coherente.

***Requisitos:***

-   Servicios de Azure DevOps, o para las instalaciones locales, Team Foundation Server 2015 Update 3 o posterior.

-   Un agente de servicios de DevOps de Azure que tiene los archivos binarios de Docker.

Una manera fácil de crear uno de estos es usar Docker para ejecutar un contenedor basado en la imagen de Docker de agente de servicios de Azure DevOps.

**Obtener más información** para leer más acerca de cómo ensamblar un elemento de configuración de Docker de servicios de Azure DevOps de canalización y para ver tutoriales, visite los sitios siguientes:

Ejecuta un agente de servicios de Azure DevOps como un contenedor de Docker: [ https://hub.docker.com/r/\ microsoft/vsts-agent /](https://hub.docker.com/r/microsoft/vsts-agent/)

Extensión de Docker de servicios de DevOps de Azure: <https://aka.ms/vstsdockerextension>

Creación de imágenes de Docker de Linux de .NET Core con los servicios de Azure DevOps: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Creación de una máquina de compilación basado en Linux, Visual Studio Team Service con compatibilidad con Docker: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Integrar, probar y validar las aplicaciones de varios contenedores Docker

Normalmente, la mayoría de las aplicaciones de Docker se compone de varios contenedores en lugar de un solo contenedor. Un buen ejemplo es una aplicación orientada a microservicios que tendría un contenedor por microservicio. Pero, incluso sin seguir estrictamente los patrones de enfoque de microservicios, es muy probable que la aplicación de Docker podría estar compuesta de varios contenedores o servicios.

Por lo tanto, después de compilar los contenedores de aplicación en la canalización de CI, también deberá implementar, integrar y probar la aplicación como un todo con todos sus contenedores dentro de un host de Docker de integración o incluso en un clúster de prueba a los que son los contenedores distribuido.

Si usa un único host, puede usar comandos de Docker como docker-compose para compilar e implementar contenedores relacionados para probar y validar el entorno de Docker en una sola máquina virtual. Sin embargo, si está trabajando con un clúster de orchestrator como DC/OS, Kubernetes o Docker Swarm, deberá implementar los contenedores a través de un mecanismo diferente o orchestrator, según su programador/clústeres seleccionado.

Continuación se muestran varios tipos de pruebas que se pueden ejecutar en contenedores de Docker:

-   Pruebas unitarias para contenedores de Docker

-   Probar los grupos de aplicaciones interrelacionadas o microservicios

-   Probar en las versiones de producción y "chivato"

Lo importante es que, al ejecutar pruebas funcionales e integración, debe ejecutar las pruebas desde fuera de los contenedores. Las pruebas no deben definirse y ejecutar dentro de los contenedores que se va a implementar, porque los contenedores se basan en las imágenes estáticas que deben ser exactamente iguales a los que se va a implementar en producción.

Es una opción muy factible al probar los escenarios más avanzados, como pruebas de varios clústeres (probar el clúster, clúster de ensayo y producción) publicar las imágenes en un registro de prueba en varios clústeres.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Insertar la imagen de Docker de la aplicación personalizada en el registro de Docker global

Después de que las imágenes de Docker se han probado y validado, desea etiquetar y publicarlos en el registro de Docker. El registro de Docker es una pieza fundamental en el ciclo de vida de la aplicación de Docker, porque es la ubicación central desde donde se almacena la prueba personalizada (también conocido como "designadas imágenes") para implementarse en entornos de producción y control de calidad.

De forma similar a cómo el código de aplicación almacenado en el repositorio de control de código fuente (Git, etc.) es el "origen de verdad", el registro de Docker es el "origen de verdad" de la aplicación binaria o bits para su implementación en los entornos de producción o control de calidad.

Normalmente, desea tener sus repositorios privados para sus imágenes personalizadas en un repositorio privado en Azure Container Registry en un registro de forma local como Docker Trusted Registry o en un registro de nube pública con acceso restringido (por ejemplo Docker Hub), aunque en este último caso, si el código no está abierto, debe confiar en seguridad del proveedor. En cualquier caso, el método por el que hacer esto es bastante similar y se basa en última instancia en el comando de inserción de docker, como se muestra en la figura 5-4.

![](./media/image4.png)

Figura 5-4: Publicar imágenes personalizadas en el registro de Docker

Hay varias ofertas de los registros de Docker de proveedores de nube como Azure Container Registry, registro de contenedor de servicios Web de Amazon, Google Container Registry, registro del muelle y así sucesivamente.

Con la extensión de Docker de servicios de Azure DevOps, puede insertar un conjunto de imágenes de servicio definidos por un archivo docker-compose.yml, con varias etiquetas, en un registro autenticado de Docker (como Azure Container Registry), tal como se muestra en la figura 5-5.

![](./media/image5.png)

Figura 5-5: Uso de servicios de Azure DevOps para publicar imágenes personalizadas a un registro de Docker

**Obtener más información** para obtener más información acerca de la extensión Docker para los servicios de Azure DevOps, vaya a <https://aka.ms/vstsdockerextension>. Para obtener más información sobre Azure Container Registry, vaya a <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Paso 4: CD, implementar

La inmutabilidad de imágenes de Docker garantiza una implementación repetible, con lo que ha desarrollado, probado a través de los elementos de configuración y ejecución en producción. Una vez que las imágenes de Docker de la aplicación publicadas en el registro de Docker (privado o público), puede implementarlas en los entornos de varias que pueda haber (producción, control de calidad, almacenamiento provisional, etc.) desde la canalización de CD mediante los servicios de Azure DevOps las tareas de canalización o servicios de Release Management de Azure DevOps.

Sin embargo, en este punto depende de qué tipo de aplicación de Docker está implementando. Implementar una aplicación sencilla (desde una implementación y la composición de punto de vista) como un monolítica implementada y de aplicaciones que incluyen algunos contenedores o servicios a unos servidores o máquinas virtuales es muy diferente de la implementación de una aplicación más compleja, como un aplicación orientada a microservicios con capacidades de hiperescala. Estos dos escenarios se explican en las secciones siguientes.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Implementación de aplicaciones de Docker en varios entornos de Docker compuestas

Veamos primero el escenario menos complejo: implementar en hosts de Docker simple (máquinas virtuales o servidores) en un entorno único o varios entornos (control de calidad, ensayo y producción). En este escenario, internamente la canalización de CD puede usar docker-compose (de las tareas de implementación de servicios de Azure DevOps) para implementar las aplicaciones de Docker con su conjunto relacionado de contenedores y servicios, como se muestra en la figura 5-6.

![](./media/image6.png)

Figura 5-6: Implementación de contenedores de aplicación para el registro de los entornos de host de Docker simple

Figura 5-7 destaca cómo pueden conectar los elementos de configuración de compilación para entornos de control de calidad y pruebas a través de servicios de Azure DevOps haciendo clic en Docker Compose en el cuadro de diálogo Agregar tarea. Sin embargo, al implementar en entornos de ensayo o producción, normalmente usaría las características de Release Management para administrar varios entornos (como el control de calidad, ensayo y producción). Si va a implementar en hosts de Docker único, que utiliza los servicios de Azure DevOps tarea "Docker Compose" (que está invocando a docker-compose comando debajo del capó). Si va a implementar en Azure Container Service, utiliza la tarea de implementación de Docker, como se explica en la sección siguiente.

![](./media/image7.png)

Figura 5-7: Agregar una tarea de Docker Compose en una canalización de servicios de Azure DevOps

Cuando se crea una versión en los servicios de Azure DevOps, toma un conjunto de artefactos de entrada. Estos están diseñados para ser inmutable durante la vigencia de la versión en varios entornos. Cuando introduzca contenedores, los artefactos de entrada identifican imágenes en un registro para implementar. Dependiendo de cómo éstas vienen identificadas, no se garantiza que no cambian a lo largo de la duración de la versión, el caso más obvio que se va a cuando se hace referencia "myimage:latest" desde un archivo docker-Compose.

La extensión Docker para los servicios de Azure DevOps proporciona resúmenes de la capacidad de generar los artefactos de compilación que contienen la imagen específica del registro que se garantiza que identifican la misma imagen binaria. Estos son lo que realmente desea utilizar como entrada para una versión.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Administración de versiones para entornos de Docker mediante el uso de servicios de Release Management de Azure DevOps

Mediante las extensiones de servicios de Azure DevOps, puede cree una nueva imagen, publicarlo en un registro de Docker, se ejecutan en hosts de Linux o Windows y usar comandos como docker-compose para implementar varios contenedores como una aplicación completa, todo ello gracias a la Azure DevOps Servicios de capacidades de Release Management destinadas a varios entornos, como se muestra en la figura 5-8.

![](./media/image8.png)

Figura 5-8: Configurar tareas de Docker Compose de servicios de DevOps de Azure desde Release Management para servicios de Azure DevOps

Sin embargo, tenga en cuenta que el escenario se muestra en la figura 5-6 y se implementa en la figura 5-8 es bastante básico (que se está implementando en los hosts de Docker simple y máquinas virtuales, y habrá un único contenedor o una instancia por imagen) y probablemente se debe usar solo para desarrollo o prueba sc Router. En la mayoría de los escenarios de producción empresarial, querría tener alta disponibilidad (HA) y fácil de administrar la escalabilidad mediante Equilibrio de carga entre varios nodos, los servidores y las máquinas virtuales, además de "inteligente las conmutaciones por error" así que si un servidor o un nodo produce un error, sus servicios y los contenedores se moverá a otro servidor host o máquina virtual. En ese caso, necesita las tecnologías más avanzadas, como clústeres de contenedor, los orquestadores y los programadores. Por lo tanto, la forma de implementar dichos clústeres es precisamente a través de los escenarios avanzados que se explica en la sección siguiente.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Implementar aplicaciones complejas de Docker para clústeres de Docker (DC/OS, Kubernetes y Docker Swarm)

La naturaleza de las aplicaciones distribuidas requiere recursos de proceso que también se distribuyen. Para que las capacidades de escala de producción, deberá tener funcionalidades que proporcionan una gran escalabilidad de clústeres y alta disponibilidad según los recursos agrupados.

Podría implementar manualmente los contenedores en esos clústeres desde una herramienta CLI como Docker Swarm (como el uso de [crear servicio docker](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) o una interfaz de usuario web, como [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) para DC/OS, clústeres, pero debe reservar sólo para las pruebas de implementación punctual o para fines de administración, como el escalado horizontal o con fines de supervisión.

Desde un punto de vista de CD y servicios de Azure DevOps en concreto, puede ejecutar tareas de implementación creados especialmente desde los entornos de Release Management de Azure DevOps Services que se va a implementar las aplicaciones en contenedores para clústeres distribuidos en contenedor Servicio, como se muestra en la figura 5-9.

![](./media/image9.png)

Figura 5-9: Implementación de aplicaciones distribuidas en Container Service

Inicialmente, al implementar en ciertas clústeres u orquestadores, tradicionalmente usaría los scripts de implementación específicos y mecanismos por cada orquestador (es decir, Mesosphere DC/OS o Kubernetes tienen mecanismos de implementación diferentes que Docker y Docker Swarm) en lugar de hacerlo más sencillo y fácil de usar docker-componen tool basándose en el archivo de definición de docker-compose.yml. Sin embargo, gracias a la tarea de implementación de Docker de servicios de Microsoft Azure DevOps, que se muestra en la figura 5-10, ahora también puede implementar en DC/OS si solo se usa el archivo docker-compose.yml familiar ya que Microsoft realiza esa traducción de"" por usted (desde la archivo docker-compose.yml a otros formatos necesarios para DC/OS).

![](./media/image10.png)

Figura 5-10: Agregar la tarea de implementación de Docker al entorno de RM

Figura 5-11 se muestra cómo puede modificar la tarea de implementación de Docker y especificar el tipo de destino (Azure Container Service DC/OS, en este caso), el archivo de Docker Compose y la conexión de registro de Docker (como Azure Container Registry o Docker Hub). Esto es donde la tarea recuperará las imágenes de Docker listos para usar personalizadas que desee implementar como contenedores en el clúster de DC/OS.

![](./media/image11.png)

Figura 5-11: Implementación de docker implementar tareas definición a Azure Container Service DC/OS

**Obtener más información** para obtener más información acerca de la canalización de CD con Docker y servicios de DevOps de Azure, visite los sitios siguientes:

Extensión de servicios de DevOps de Azure para Docker y Azure Container Service: [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Azure Container Service: <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Paso 5: Ejecutar y administrar

Porque está ejecutando y administración de aplicaciones en producción de la empresa nivel es un asunto principal de sí mismo y debido al tipo de operaciones y personas que trabajan en ese nivel (operaciones de TI), así como el ámbito de esta área de gran tamaño, nos hemos dedicado todo el contenido a continuación capítulo a explicarlo.

## <a name="step-6-monitor-and-diagnose"></a>Paso 6: Supervisión y diagnóstico

Este tema también se trata en el capítulo siguiente como parte de las tareas que realiza las operaciones de TI en sistemas de producción; Sin embargo, es importante resaltar que deben suministrar los conocimientos obtenidos en este paso hasta que el equipo de desarrollo para que la aplicación se mejora constantemente. Desde ese punto de vista, también forma parte de DevOps, aunque normalmente se realizan las tareas y operaciones por TI.

Solo cuando la supervisión y diagnóstico es 100% en el ámbito de DevOps son los procesos de supervisión y análisis realizadas por el equipo de desarrollo frente a entornos de prueba o beta. Esto se hace mediante la realización de pruebas de carga o simplemente mediante la supervisión de la versión beta o entornos de preguntas y respuestas, donde los evaluadores de beta están tratando de las nuevas versiones.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](../run-manage-monitor-docker-environments/index.md)