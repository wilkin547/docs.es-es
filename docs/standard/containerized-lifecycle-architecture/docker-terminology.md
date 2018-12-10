---
title: Terminología de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 1efb2fa567bd452f0a0a5ee5afb6f759511e4145
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151321"
---
# <a name="docker-terminology"></a>Terminología de Docker

Esta sección enumeran los términos y definiciones con la que debería familiarizarse con antes de profundizar más en Docker (para obtener más definiciones, lea el amplio [glosario](https://docs.docker.com/glossary/) proporcionada por Docker en <https://docs.docker.com/glossary/>:

-   **Imagen de contenedor** un paquete con todas las dependencias y la información necesaria para crear un contenedor. Una imagen incluye todas las dependencias (por ejemplo, los marcos) además de implementación y configuración que se utilizará en tiempo de ejecución de un contenedor. Normalmente, una imagen se deriva de varias imágenes bases que son capas apiladas uno encima de la otra para formar el sistema de archivos del contenedor. Una imagen es inmutable después de que se ha creado.

-   **Contenedor** una instancia de una imagen de Docker. Un contenedor representa un tiempo de ejecución para una sola aplicación, proceso o servicio. Está formado por el contenido de una imagen de Docker, un entorno en tiempo de ejecución y un conjunto estándar de instrucciones. Al escalar un servicio, crea varias instancias de un contenedor a partir de la misma imagen. O bien, un trabajo por lotes puede crear varios contenedores de la misma imagen, pasar parámetros diferentes para cada instancia.

-   **Etiqueta** una marca o una etiqueta que se puede aplicar a las imágenes, por lo que se puedan identificar diferentes imágenes o versiones de la misma imagen (según el número de versión o el entorno de destino).

-   **Dockerfile** un archivo de texto que contiene instrucciones sobre cómo crear una imagen de Docker.

-   **Compilar** la acción de la creación de una imagen de contenedor en función de la información y el contexto proporcionado por su Dockerfile, así como los archivos adicionales en la carpeta donde se crea la imagen. Puede compilar las imágenes mediante el comando de compilación de docker de Docker.

-   **Repositorio (también conocido como repositorio)** una colección de imágenes de Docker relacionadas con la etiqueta con una etiqueta que indica la versión de la imagen. Algunos repositorios contienen varias variantes de una imagen específica, como una imagen que contiene SDK (más pesada), una imagen que contiene solo los runtimes (más ligera), y así sucesivamente. Estas variantes se pueden marcar con etiquetas. Un único repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.

-   **Registro** un servicio que proporciona acceso a los repositorios. El registro predeterminado para la mayoría de las imágenes públicas es [Docker Hub](https://hub.docker.com/) (propiedad de Docker como una organización). Normalmente, un registro contiene repositorios procedentes de varios equipos. Las empresas suelen tener registros privados para almacenar y administrar las imágenes que hayan creado. *Azure Container Registry* es otro ejemplo.

-   **Docker Hub** un registro público para cargar imágenes y trabajar con ellos. Docker Hub proporciona hospedaje de imágenes de Docker, registros públicos o privados, desencadenadores de compilación y enlaces web e integración con GitHub y Bitbucket.

-   **Azure Container Registry** un recurso público para trabajar con imágenes de Docker y sus componentes en Azure. Esto proporciona un registro cercano a las implementaciones en Azure que le proporciona control sobre el acceso, lo que le permite usar los grupos y los permisos de Active Directory.

-   **Docker Trusted Registry (DTR)** servicio de registro de Docker A (de Docker) que se puede instalar de forma local para que se encuentra dentro de centros de datos y la red de la organización. Es ideal para imágenes privadas que deben administrarse dentro de la empresa. Docker Trusted Registry se incluye como parte del producto Docker Datacenter. Para obtener más información, vaya a [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker Community Edition (CE)** herramientas de desarrollo para Windows y macOS para compilar, ejecutar y probar contenedores localmente. Docker CE para Windows proporciona entornos de desarrollo para contenedores de Windows y Linux. El host de Linux Docker en Windows se basa en un [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) máquina virtual. El host para los contenedores de Windows se basa directamente en Windows. Docker CE para Mac se basa en el marco del hipervisor de Apple y la [hipervisor xhyve](https://github.com/mist64/xhyve), que proporciona una máquina virtual del host de Docker de Linux en el sistema operativo de Mac Docker de X. CE para Windows y para Mac sustituye a Docker Toolbox, que se basaba en Oracle VirtualBox.

-   **Docker Enterprise Edition (EE)** una versión a escala empresarial de las herramientas de Docker para el desarrollo de Linux y Windows.

-   **Redactar** una herramienta de línea de comandos y YAML formato de archivo con metadatos para definir y ejecutar aplicaciones de varios contenedores. Primero se define una sola aplicación basada en varias imágenes con uno o más archivos .yml que pueden invalidar los valores según el entorno. Después de haber creado las definiciones, puede implementar toda la aplicación de varios contenedores mediante el uso de un solo comando (docker-compose seguridad) que crea un contenedor por imagen en el host de Docker.

-   **Clúster** una colección de hosts de Docker expuestas como si fueran un único host virtual de Docker para que la aplicación puede escalar a varias instancias de los servicios repartidos entre varios hosts del clúster. Puede crear clústeres de Docker mediante el uso de Docker Swarm, Mesosphere DC/OS, Kubernetes y Azure Service Fabric. (Cuando se usa Docker Swarm para administrar un clúster, se suele hacer referencia al clúster como un *conjunto* en lugar de un clúster).

-   **Orchestrator** una herramienta que simplifica la administración de clústeres y hosts de Docker. Con orquestadores, puede administrar sus imágenes, los contenedores y los hosts a través de un CLI o una interfaz gráfica de usuario. Puede administrar las redes de contenedor, las configuraciones, el equilibrio de carga, la detección de servicios, la alta disponibilidad, la configuración del host de Docker y muchas cosas más. Un orquestador se encarga de ejecutar, distribuir, escalar y reparar las cargas de trabajo a través de una colección de nodos. Normalmente, los productos del orquestador son los mismos que proporcionan infraestructura de clúster, como Mesosphere DC/OS, Kubernetes, Docker Swarm y Azure Service Fabric.

>[!div class="step-by-step"]
>[Anterior](what-is-docker.md)
>[Siguiente](docker-containers-images-and-registries.md)