---
title: Terminología de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 853474a18e5c7253b88db7fb651ee447242bb9f2
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="docker-terminology"></a>Terminología de Docker

Esta sección enumeran términos y definiciones con la que debería familiarizarse con antes de profundizar un poco más en Docker (para obtener más definiciones, vea el amplio [glosario](https://docs.docker.com/glossary/) proporcionada por Docker en <https://docs.docker.com/glossary/>:

-   **Imagen de contenedor** un paquete con todas las dependencias y la información necesaria para crear un contenedor. Una imagen incluye todas las dependencias (por ejemplo, marcos) además de implementación y configuración que se usará en tiempo de ejecución de un contenedor. Normalmente, una imagen se deriva de varias imágenes de base que se capas apilan uno sobre otro para formar el sistema de archivos del contenedor. Una imagen es inmutable después de que se ha creado.

-   **Contenedor** una instancia de una imagen de Docker. Un contenedor representa un tiempo de ejecución para una sola aplicación, proceso o servicio. Está formada por el contenido de una imagen de Docker, un entorno en tiempo de ejecución y un conjunto estándar de instrucciones. Al escalar un servicio, crea varias instancias de un contenedor a partir de la misma imagen. O bien, un proceso por lotes puede crear varios contenedores de la misma imagen, pasar parámetros diferentes para cada instancia.

-   **Etiqueta** una marca o una etiqueta que se puede aplicar a las imágenes para que se pueden identificar los diferentes imágenes o las versiones de la misma imagen (según el número de versión o el entorno de destino).

-   **Dockerfile** un archivo de texto que contiene instrucciones sobre cómo crear una imagen de Docker.

-   **Generar** la acción de creación de una imagen de contenedor en función de la información y el contexto proporcionado por su Dockerfile, así como los archivos adicionales en la carpeta donde se crea la imagen. Puede crear imágenes mediante el comando de compilación de docker de Docker.

-   **Repositorio (también conocido como repositorio)** una colección de imágenes de Docker relacionadas con la etiqueta con una etiqueta que indica la versión de la imagen. Algunos repositorios contienen varias variantes de una imagen específica, como una imagen que contiene SDK (más compleja), una imagen que contiene solo los runtimes (más claros), y así sucesivamente. Estas variantes se pueden marcar con etiquetas. Un solo repositorio puede contener las variantes de la plataforma, como una imagen de Linux y una imagen de Windows.

-   **Registro** un servicio que proporciona acceso a los repositorios. El registro predeterminado para la mayoría de las imágenes públicas es [Docker Hub](https://hub.docker.com/) (propiedad de Docker como una organización). Normalmente, un registro contiene repositorios procedentes de varios equipos. Las empresas suelen tengan registros privados para almacenar y administrar imágenes que hayan creado. *Registro de contenedor Azure* es otro ejemplo.

-   **Centro de docker** un registro público para cargar imágenes y trabajar con ellos. Docker Hub proporciona hospedaje de imágenes de Docker, registros públicos o privados, desencadenadores de compilación y enlaces web e integración con GitHub y Bitbucket.

-   **Registro de contenedor Azure** un recurso público para trabajar con imágenes de Docker y sus componentes en Azure. Esto proporciona un registro cercano a las implementaciones en Azure que le proporciona control sobre el acceso, lo que le permite usar los grupos y los permisos de Active Directory.

-   **Registro de confianza de docker (DTR)** servicio de registro de Docker A (a través de Docker) que se puede instalar en local para que se encuentra en el centro de datos y la red de la organización. Es ideal para imágenes privadas que deben administrarse dentro de la empresa. Docker Trusted Registry se incluye como parte del producto Docker Datacenter. Para obtener más información, vaya a [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker Community Edition (CE)** herramientas de desarrollo para Windows y Mac OS para compilar, ejecutar y probar contenedores localmente. Docker CE para Windows proporciona entornos de desarrollo para contenedores de Windows y Linux. El host de Linux Docker en Windows se basa en un [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) máquina virtual. El host para los contenedores de Windows se basa directamente en Windows. Docker CE para Mac se basa en el marco de trabajo de hipervisor de Apple y la [xhyve hipervisor](https://github.com/mist64/xhyve), lo que proporciona una máquina virtual del host de Linux Docker en Mac OS X. Docker CE para Windows y para Mac reemplaza el cuadro de herramientas de Docker, que se basa en Oracle VirtualBox.

-   **Docker Enterprise Edition (EE)** una versión de escala empresarial de herramientas de Docker para el desarrollo de Linux y Windows.

-   **Crear** una herramienta de línea de comandos y YAML formato con metadatos para definir y ejecutar aplicaciones multicontainer de archivo. Primero se define una sola aplicación basada en varias imágenes con uno o más archivos .yml que pueden invalidar los valores según el entorno. Después de crear las definiciones, puede implementar toda la aplicación multicontainer mediante un único comando (docker-crear una) que crea un contenedor por imagen en el host de Docker.

-   **Clúster** una colección de hosts de Docker que se exponen como si fueran un único host virtual de Docker para que la aplicación se puede adaptar a varias instancias de los servicios se reparten entre varios hosts del clúster. Puede crear clústeres de Docker mediante Docker Swarm, Mesosphere DC/OS, Kubernetes y Azure Service Fabric. (Cuando se usa Docker Swarm para administrar un clúster, se suele hacer referencia al clúster como un *conjunto* en lugar de un clúster).

-   **Orchestrator** una herramienta que simplifica la administración de clústeres y hosts de Docker. Orchestrators puede administrar sus imágenes, los contenedores y los hosts a través de una CLI o una interfaz gráfica de usuario. Puede administrar las redes de contenedor, las configuraciones, el equilibrio de carga, la detección de servicios, la alta disponibilidad, la configuración del host de Docker y muchas cosas más. Un orquestador se encarga de ejecutar, distribuir, escalar y reparar las cargas de trabajo a través de una colección de nodos. Normalmente, los productos del orquestador son los mismos que proporcionan infraestructura de clúster, como Mesosphere DC/OS, Kubernetes, Docker Swarm y Azure Service Fabric.


>[!div class="step-by-step"]
[Anterior] (what-es-docker.md) [siguiente] (docker-contenedores-imágenes-y-registries.md)
