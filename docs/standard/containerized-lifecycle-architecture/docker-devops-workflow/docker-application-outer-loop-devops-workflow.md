---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 198313c260b36d3f3025606e73e220c361a7ebb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579007"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker

Figura 5-1 presenta una representación to-end de los pasos que componen el flujo de trabajo de DevOps bucle exterior.

![](./media/image1.png)

Figura 5-1: flujo de trabajo de DevOps bucle externo para las aplicaciones de Docker con herramientas de Microsoft

Ahora, examinemos cada uno de estos pasos con más detalle.

## <a name="step-1-inner-loop-development-workflow"></a>Paso 1: Flujo de trabajo de desarrollo de bucle interno

Este paso se explica con detalle en el capítulo 4, pero, en resumen, aquí es donde empieza el bucle exterior, el momento en que un desarrollador inserta código en el sistema de administración de control de código fuente (por ejemplo, Git) iniciar acciones de canalización de elemento de configuración.

## <a name="step-2-source-code-control-integration-and-management-with-visual-studio-team-services-and-git"></a>Paso 2: Integración de Control de código fuente y la administración con Visual Studio Team Services y Git

En este paso, debe tener un sistema de control de versiones para recopilar una versión consolidada de todo el código procedente de los desarrolladores diferentes en el equipo.

Aunque el control de código fuente (SCC) y la administración de código fuente pueden parecer rutinario desplazarse a la mayoría de los desarrolladores, al crear aplicaciones de Docker en una vida DevOps, es fundamental para destacar que no se debe enviar las imágenes de Docker con la aplicación directamente en el registro de Docker de global (como registro de contenedor de Azure o Docker Hub) desde el equipo del desarrollador. Por el contrario, las imágenes de Docker se libera y se implementan en entornos de producción deben crearse únicamente en el código fuente que se integra en la compilación global o la canalización de elemento de configuración basado en el repositorio de código fuente (por ejemplo, Git).

Las imágenes locales generadas por los desarrolladores a sí mismos deben utilizarse solo por los desarrolladores al probar dentro de sus propios equipos. Este es el motivo por el que es fundamental que la canalización de DevOps activa desde el código de control de código fuente.

Visual Studio Team Services y Team Foundation Server admiten Git y Control de versiones de Team Foundation. Puede elegir entre ellos y usarlo para obtener una experiencia de Microsoft-to-end. Sin embargo, también puede administrar el código en repositorios externos (por ejemplo, GitHub, repositorios de Git local o secundaria) y seguir siendo capaces de conectarse a él y obtener el código como punto de partida de la canalización de CI de DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-visual-studio-team-services-and-docker"></a>Paso 3: Compilación, CI, integrar y probar con Visual Studio Team Services y Docker

Elemento de configuración ha surgido como un estándar para las pruebas de software moderno y entrega. La solución de Docker mantiene una separación clara de intereses entre los equipos de desarrollo y las operaciones. La inmutabilidad de imágenes de Docker garantiza una implementación repetible entre lo que ha desarrollado, probado a través de los elementos de configuración y ejecutadas en producción. Motor de docker se implementa en los equipos portátiles de desarrollador e infraestructura de prueba hace que los contenedores portátil a través de entornos.

En este momento, una vez que un sistema de control de versiones con el código correcto enviado, necesita un *crear servicio* para recoger el código y ejecutar la compilación global y las pruebas.

El flujo de trabajo interno para este paso (elemento de configuración, compilación, prueba) consiste en la construcción de una canalización de elemento de configuración que consta de su repositorio de código (Git, etc.), el servidor de compilación (Visual Studio Team Services), el motor de Docker y un registro de Docker.

Puede usar Visual Studio Team Services como base para compilar las aplicaciones y la configuración de la canalización de elemento de configuración y para publicar los integrada "artefactos" a un "repositorio de artefactos", que se explica en el paso siguiente.

Al usar Docker para la implementación, los "artefactos finales" para implementar imágenes de Docker con sus aplicaciones o servicios incrustadas dentro de ellos. Las imágenes se insertan o se publican en un *Docker registro* (un repositorio privado como los que puede tener en el registro de contenedor de Azure o una pública como registro de Docker Hub, que se utiliza normalmente para las imágenes base oficiales).

Este es el concepto básico: elementos de configuración de la canalización será iniciado desactivada por una confirmación a un repositorio de control de código fuente como Git. La confirmación hará que Visual Studio Team Services ejecutar un trabajo de compilación dentro de un contenedor de Docker y, en la realización correcta de ese trabajo, insertar una imagen de Docker en el registro de Docker, como se muestra en la figura 5-2.

![](./media/image2.png)

Figura 5-2: los pasos necesarios para el elemento de configuración

Estos son los pasos de flujo de trabajo de elementos de configuración básicos con Docker y Visual Studio Team Services:

1.  El desarrollador inserta una confirmación a un repositorio de control de código fuente (Git o Visual Studio Team Services, GitHub, etcetera).

2.  Si usa Visual Studio Team Services o Git, CI está integrada, lo que significa que es tan sencilla como activar una casilla de verificación en Visual Studio Team Services. Si usas un SCC externo (por ejemplo, GitHub), un *webhook* va a notificar a Visual Studio Team Services de la actualización o inserción en Git y GitHub.

3.  Visual Studio Team Services extrae el repositorio de control de código fuente, incluidos el DockerFile que describen la imagen, así como el código de aplicación y prueba.

4.  Visual Studio Team Services genera una imagen de Docker y etiquetas con un número de compilación.

5.  Visual Studio Team Services crea el contenedor de Docker en el Host Docker aprovisionado y ejecuta las pruebas adecuadas.

6.  Si las pruebas son correctas, la imagen se primero vuelve a etiquetar a un nombre descriptivo para que sepa que es una "compilación designada" (como "/ 1.0.0" o cualquier otra etiqueta) y, a continuación, inserta en el registro de Docker (Docker Hub, registro de contenedor de Azure, DTR, etcetera.)

### <a name="implementing-the-ci-pipeline-with-visual-studio-team-services-and-the-docker-extension-for-visual-studio-team-services"></a>Implementar la canalización de integración continua con Visual Studio Team Services y la extensión Docker para Visual Studio Team Services

El [extensión de Visual Studio Team Services Docker](https://aka.ms/vstsdockerextension) agrega una tarea a la canalización de elemento de configuración con el que puede crear imágenes de Docker, insertar imágenes de Docker en un registro de Docker autenticado, ejecutar imágenes de Docker o ejecutar otras operaciones que ofrece el CLI de docker. También agrega una tarea Docker Compose que puede usar para crear, insertar y ejecutar aplicaciones de Docker multicontainer o ejecutar otras operaciones que ofrece la CLI de redacción de Docker, tal como se muestra en la figura 5-3.

![](./media/image3.png)

Figura 5-3: la canalización de elemento de configuración de Docker en Visual Studio Team Services

La extensión Docker puede usar los puntos de conexión de servicio para los hosts de Docker y de contenedor o registros de la imagen. El valor predeterminado de tareas para utilizar un host Docker local si está disponible (Esto requiere actualmente un agente de Visual Studio Team Services personalizado); en caso contrario, requiere que se proporcione una conexión a host Docker. Las acciones que dependen de que se va a autenticar con un registro de Docker, como la inserción de una imagen, requieren que se proporcione a una Docker conexión del registro.

La extensión de Visual Studio Team Services Docker instala los componentes siguientes en su cuenta de Visual Studio Team Services:

-   Un extremo de servicio para conectarse a un registro de Docker

-   Un extremo de servicio para conectarse a un Host de contenedor de Docker

-   Una tarea de Docker para hacer lo siguiente:

-   Crear una imagen

-   Insertar una imagen o un repositorio para un registro

-   Ejecutar una imagen en un contenedor

-   Ejecutar un comando de Docker

-   Una tarea para ejecutar un comando Docker Compose Docker Compose

Con estas tareas de Visual Studio Team Services, una compilación de Docker de Linux/máquina virtual de Host aprovisionado en Azure y el registro de Docker preferido (registro de contenedor de Azure, Docker Hub, privada DTR de Docker o cualquier otro registro de Docker) puede ensamblar la canalización de elemento de configuración de Docker en un forma muy coherente.

***Requisitos:***

-   Visual Studio Team Services, o para las instalaciones locales, Team Foundation Server 2015 Update 3 o posterior.

-   Un agente de Visual Studio Team Services que contenga los archivos binarios de Docker.

Una manera fácil de crear una de ellas es usar Docker para ejecutar un contenedor en función de la imagen de Docker de agente de Visual Studio Team Services.

**Obtener más información** para leer más acerca de cómo ensamblar un CI de Visual Studio Team Services Docker de canalización y para ver los tutoriales, visiten los siguientes sitios:

Ejecuta un agente de Visual Studio Team Services como un contenedor de Docker: [ https://hub.docker.com/r/\ vsts-agente/microsoft /](https://hub.docker.com/r/microsoft/vsts-agent/)

Extensión de Docker de VSTS: <https://aka.ms/vstsdockerextension>

Creación de imágenes de .NET Core Linux Docker con Visual Studio Team Services: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Creación de una máquina de compilación basado en Linux, el servicio del equipo de Visual Studio con el soporte técnico de Docker: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Integrar, probar y validar las aplicaciones de Docker multicontainer

Normalmente, la mayoría de las aplicaciones de Docker se compone de varios contenedores en lugar de un único contenedor. Un buen ejemplo es una aplicación orientada a servicios de microservicios para el que tendría un contenedor por microservicio. Sin embargo, incluso sin seguir estrictamente los patrones de enfoque microservicios, es muy probable que la aplicación de Docker podría estar compuesta de varios contenedores o servicios.

Por lo tanto, después de compilar los contenedores de la aplicación en la canalización de elemento de configuración, también debe implementar, integrar y probar la aplicación como un todo con todos sus contenedores dentro de un host de Docker de integración o incluso en un clúster de prueba a los que son los contenedores distribuir.

Si usa un solo host, puede utilizar comandos de Docker como docker-crear para generar e implementar contenedores relacionados para probar y validar el entorno de Docker en una sola máquina virtual. Sin embargo, si está trabajando con un clúster de orchestrator como controlador de dominio/OS, Kubernetes o Docker Swarm, debe implementar los contenedores mediante un mecanismo diferente o orchestrator, dependiendo de su programador/clúster seleccionado.

Estos son varios tipos de pruebas que pueden ejecutar en contenedores de Docker:

-   Pruebas unitarias para contenedores de Docker

-   Grupos de prueba de aplicaciones interrelacionadas o microservicios

-   En las versiones "Canarias" y de producción de prueba

Lo importante es que cuando se ejecuta integración y pruebas funcionales, debe ejecutar las pruebas desde fuera de los contenedores. Pruebas no deben definirse y ejecutar dentro de los contenedores que se va a implementar, porque los contenedores se basan en las imágenes estáticas que deben ser exactamente iguales a los que va a implementar en producción.

Es una opción muy factible al probar los escenarios más avanzados como pruebas para varios clústeres (probar clúster, clúster de ensayo y producción clúster) publicar las imágenes a un registro para probar en varios clústeres.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Insertar la imagen de Docker de aplicación personalizada en el registro de Docker global

Una vez probadas y validar las imágenes de Docker, desea etiquetar y publíquelos en el registro de Docker. El registro de Docker es una pieza fundamental en el ciclo de vida de la aplicación de Docker porque es la ubicación central donde se almacenan sus pruebas personalizadas (también conocido como "designadas imágenes") para implementarse en entornos de producción y preguntas y respuestas.

De forma similar a cómo el código de aplicación almacenado en el repositorio de control de código fuente (Git, etc.) es el "origen de verdad", el registro de Docker es su "origen de verdad" para su aplicación binaria o bits para su implementación en los entornos de producción o de preguntas y respuestas.

Normalmente, desea tener sus repositorios privadas para las imágenes personalizadas en un repositorio privado en el registro de contenedor de Azure o en un registro local como registro de confianza de Docker o en un registro de la nube pública con acceso restringido (por ejemplo Docker Hub), aunque en este último caso, si el código no está abierto, debe confiar en seguridad del proveedor. En cualquier caso, el método por el que hacer esto es bastante similar y en última instancia en función del comando de inserción de docker, como se muestra en la figura 5-4.

![](./media/image4.png)

Figura 5-4: publicar imágenes personalizadas en el registro de Docker

Hay varias ofertas de los registros de Docker de proveedores de nube como registro de contenedor de Azure, registro de contenedor de Amazon Web Services, registro de contenedor de Google, del registro del muelle y así sucesivamente.

Utilice la extensión de Visual Studio Team Services Docker, puede insertar un conjunto de imágenes de servicio definido por un archivo de compose.yml de docker, con varias etiquetas, en un registro de Docker autenticado (por ejemplo, registro de contenedor de Azure), tal como se muestra en la figura 5-5.

![](./media/image5.png)

Figura 5-5: usar Visual Studio Team Services para publicación imágenes personalizadas a un registro de Docker

**Obtener más información** para obtener más acerca de la extensión Docker para Visual Studio Team Services, vaya a <https://aka.ms/vstsdockerextension>. Para obtener más información acerca del registro de contenedor de Azure, vaya a <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Paso 4: CD, implementar

La inmutabilidad de imágenes de Docker garantiza una implementación repetible con lo que ha desarrollado, probado a través de los elementos de configuración y ejecutadas en producción. Una vez que las imágenes de Docker de la aplicación publicadas en el registro de Docker (privado o público), se pueden implementar en varios entornos de los que es posible que tenga (producción, preguntas y respuestas, almacenamiento provisional, etc.) de la canalización de CD mediante el uso de Visual Studio Team Services tareas de canalización o Visual Studio Team Services Release Management.

Sin embargo, en este punto depende de qué tipo de aplicación de Docker que va a implementar. Implementar una aplicación simple (de una composición y la implementación de punto de vista) como un monolítico que comprenden unos contenedores o servicios de aplicación e implementada a unos servidores o máquinas virtuales es muy diferente de la implementación de una aplicación más compleja como una aplicación orientada a microservicios con capacidades de hiperescalar. Estos dos escenarios se explican en las secciones siguientes.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Implementación compuesto por las aplicaciones de Docker para varios entornos de Docker

Echemos un vistazo primero en el escenario menos complejo: la implementación en hosts de Docker simples (máquinas virtuales o servidores) en un entorno único o en varios entornos (QA, ensayo y producción). En este escenario, la canalización de CD puede utilicen internamente docker-crear (de las tareas de implementación de Visual Studio Team Services) para implementar las aplicaciones de Docker con su conjunto relacionado de contenedores o servicios, como se muestra en la figura 5-6.

![](./media/image6.png)

Figura 5-6: implementar contenedores de aplicaciones en el registro de los entornos de host de Docker simple

Figura 5-7 se destaca cómo puede conectarse el elemento de configuración de compilación a los entornos de prueba/QA a través de Visual Studio Team Services, haga clic en Docker Compose en el cuadro de diálogo Agregar tarea. Sin embargo, cuando se implementa en entornos de ensayo o de producción, normalmente usaría varios entornos de control de características de administración de versión (al igual que preguntas y respuestas, ensayo y producción). Si va a implementar en hosts de Docker únicos, que está usando Visual Studio Team Services tarea "Docker Compose" (que está invocando el docker-crear comando bajo el paraguas). Si va a implementar en un servicio de contenedor de Azure, utiliza la tarea de implementación de Docker, como se explica en la sección siguiente.

![](./media/image7.png)

Figura 5-7: agregar una tarea de Docker Compose en una canalización de Visual Studio Team Services

Cuando se crea una versión de Visual Studio Team Services, tiene un conjunto de artefactos de entrada. Éstos están pensados para ser inmutable durante toda la duración de la versión en varios entornos. Cuando se introducen contenedores, los artefactos de entrada identifican imágenes en un registro para implementar. Dependiendo de cómo se identifican, no se garantiza que siguen siendo los mismos a lo largo de la duración de la versión, el caso más obvio que se va a cuando se hace referencia "myimage:latest" desde un archivo docker-compose.

La extensión Docker para Visual Studio Team Services proporciona resúmenes de la capacidad de generar los artefactos de compilación que contienen la imagen específica del registro que se garantiza para identificar de forma única la misma imagen binaria. Se trata de lo que realmente desea utilizar como entrada para una versión.

### <a name="managing-releases-to-docker-environments-by-using-visual-studio-team-services-release-management"></a>Administración de versiones para entornos de Docker mediante Visual Studio Team Services Release Management

A través de las extensiones de Visual Studio Team Services, puede crear una nueva imagen, publicarlo en un registro de Docker, ejecutarla en hosts de Linux o Windows y utilizar comandos como docker-crear para implementar varios contenedores como una aplicación completa, todo ello a través del objeto Visual Capacidades de administración de versiones de Team Services Studio destinadas a varios entornos, como se muestra en la figura 5-8.

![](./media/image8.png)

Figura 5-8: configurar tareas de Visual Studio Team Services Docker Compose desde Visual Studio Team Services Release Management

Sin embargo, tenga en cuenta que el escenario se muestra en la figura 5-6 y se implementa en la figura 5-8 es bastante básico (se está implementando en hosts de Docker simples y máquinas virtuales, y habrá un único contenedor o una instancia por imagen) y probablemente se debe usar solo para desarrollo o prueba sc Router. En la mayoría de los escenarios de producción empresarial, desearía tener alta disponibilidad (HA) y fácil de administrar la escalabilidad mediante Equilibrio de carga entre varios nodos, servidores y las máquinas virtuales, además de "inteligente las conmutaciones por error" así que si un servidor o un nodo produce un error, sus servicios y los contenedores se moverán a otro servidor de host o máquina virtual. En ese caso, necesita las tecnologías más avanzadas como clústeres de contenedor, orchestrators y programadores. Por lo tanto, la manera de implementar en esos clústeres es precisamente a través de los escenarios avanzados que se explica en la sección siguiente.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Implementar aplicaciones complejas de Docker para clústeres de Docker (controlador de dominio/OS, Kubernetes y Docker Swarm)

La naturaleza de las aplicaciones distribuidas requiere recursos de proceso que también se distribuyen. Para tener capacidades de escala de producción, debe tener la agrupación en clústeres capacidades que proporcionan una gran escalabilidad y alta disponibilidad en función de los recursos agrupados.

Puede implementar contenedores manualmente en esos clústeres desde una herramienta CLI como Docker Swarm (como el uso de [crear servicio docker](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) o una interfaz de usuario web como [Mesosphere maratón](https://mesosphere.github.io/marathon/docs/marathon-ui.html) para DC/OS clústeres, pero debe reservar sólo para pruebas de implementación punctual o para propósitos de administración como el escalamiento horizontal o con fines de supervisión.

Desde un punto de vista de CD y Visual Studio Team Services en concreto, puede ejecutar tareas de implementación especialmente realizadas desde los entornos de Visual Studio Team Services Release Management que se va a implementar las aplicaciones en contenedores a los clústeres distribuidos en Servicio de contenedor, como se muestra en la figura 5-9.

![](./media/image9.png)

Figura 5-9: implementación de aplicaciones distribuidas en servicio de contenedor

En principio, cuando se implementa en ciertos clústeres o orchestrators, tradicionalmente usaría scripts de implementación específicos y mecanismos por cada orchestrator (es decir, Mesosphere DC/OS o Kubernetes tienen permisos para los diferentes mecanismos de Docker y Docker Swarm) en lugar de la más sencilla y fácil de usar docker-redacción herramienta basada en el archivo de definición de compose.yml de docker. Sin embargo, gracias a la tarea de Microsoft Visual Studio Team Services Docker implementar, se muestra en la figura 5-10, ahora también puede implementar en DC/OS usando solo el archivo compose.yml de docker familiar porque Microsoft realiza esa "traducción" automáticamente (desde el archivo compose.yml de docker a otros formatos necesita DC/OS).

![](./media/image10.png)

Figura 5-10: agregar la tarea de implementación de Docker a su entorno de RM

Figura 5-11 muestra cómo puede modificar la tarea de implementación de Docker y especificar el tipo de destino (contenedor de servicio DC/SO Azure, en este caso), el archivo de redacción de Docker y la conexión del registro de Docker (por ejemplo, registro de contenedor de Azure o Docker Hub). Esto es donde la tarea recuperará las imágenes del Docker personalizadas listos para usar para implementarse como contenedores en el clúster de DC/OS.

![](./media/image11.png)

Implementación de la figura 5-11: Docker implementar tarea definición para el servicio de contenedor de Azure DC/OS

**Obtener más información** para obtener más información acerca de la canalización de CD con Visual Studio Team Services y Docker, visite los siguientes sitios:

Extensión de Visual Studio Team Services para Docker y el servicio de contenedor de Azure: [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Servicio de contenedor de Azure: <https://aka.ms/azurecontainerservice>

Controlador de dominio mesosphere/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Paso 5: Ejecutar y administrar

Dado que ejecutar y administrar aplicaciones en producción enterprise nivel es un asunto principal en y de sí mismo y por el tipo de operaciones y personas que trabajan en ese nivel (operaciones de TI), así como la amplia gama de esta área, nos hemos dedicado toda la matriz junto capítulo a explicarlo.

## <a name="step-6-monitor-and-diagnose"></a>Paso 6: Supervisar y diagnosticar

En este tema también se trata en el capítulo siguiente como parte de las tareas que realiza las operaciones de TI en sistemas de producción; Sin embargo, es importante resaltar que debe suministrar la información obtenida en este paso hacia el equipo de desarrollo para que la aplicación se ha mejorado la constantemente. Desde ese punto de vista, también forma parte de DevOps, aunque normalmente se realizan las tareas y operaciones por TI.

Solo cuando la supervisión y diagnóstico está al 100% en el dominio Kerberos de DevOps son los procesos de supervisión y análisis realizadas por el equipo de desarrollo en entornos de pruebas o beta. Esto se realiza mediante la realización de pruebas de carga o simplemente mediante la supervisión de la versión beta o entornos de preguntas y respuestas, donde los evaluadores de beta están tratando de las nuevas versiones.

>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (.. /Run-Manage-Monitor-docker-Environments/index.MD)
