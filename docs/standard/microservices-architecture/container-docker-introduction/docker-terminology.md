---
title: Terminología de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Terminología de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 9bbeff8c467e762e682fdaf99c8a11851b291db8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="docker-terminology"></a>Terminología de Docker

En esta sección se enumeran los términos y las definiciones que debe conocer antes de profundizar en el uso de Docker. Para obtener más definiciones, lea el amplio [glosario](https://docs.docker.com/glossary/) que Docker proporciona.

**Imagen de contenedor**: un paquete con todas las dependencias y la información necesarias para crear un contenedor. Una imagen incluye todas las dependencias (por ejemplo, los marcos), así como la configuración de implementación y ejecución que usará el runtime de un contenedor. Normalmente, una imagen se deriva de varias imágenes base que son capas que se apilan unas encima de otras para formar el sistema de archivos del contenedor. Una vez que se crea una imagen, esta es inmutable.

**Contenedor**: una instancia de una imagen de Docker. Un contenedor representa la ejecución de una sola aplicación, proceso o servicio. Está formado por el contenido de una imagen de Docker, un entorno de ejecución y un conjunto estándar de instrucciones. Al escalar un servicio, crea varias instancias de un contenedor a partir de la misma imagen. O bien, un proceso por lotes puede crear varios contenedores a partir de la misma imagen y pasar parámetros diferentes a cada instancia.

**Etiqueta**: una marca o una etiqueta que se puede aplicar a las imágenes para que se puedan identificar diferentes imágenes o versiones de la misma imagen (según el número de versión o el entorno de destino).

**Archivo Docker**: un archivo de texto que contiene instrucciones sobre cómo crear una imagen de Docker.

**Compilación**: la acción de crear una imagen de contenedor basada en la información y el contexto que proporciona su archivo Docker, así como archivos adicionales en la carpeta en que se crea la imagen. Puede crear imágenes con el comando de compilación de acoplador de Docker.

**Repositorio**: una colección de imágenes de Docker relacionadas, etiquetadas con una etiqueta que indica la versión de la imagen. Algunos repositorios contienen varias variantes de una imagen específica, como una imagen que contiene SDK (más pesada), una imagen que solo contiene runtimes (más ligera), etcétera. Estas variantes se pueden marcar con etiquetas. Un repositorio único puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.

**Registro**: servicio que proporciona acceso a los repositorios. El registro predeterminado para la mayoría de las imágenes públicas es [Docker Hub](https://hub.docker.com/) (propiedad de Docker como una organización). Normalmente, un registro contiene repositorios procedentes de varios equipos. Las empresas suelen tener registros privados para almacenar y administrar imágenes que han creado. Azure Container Registry es otro ejemplo.

**Docker Hub**: registro público para cargar imágenes y trabajar con ellas. Docker Hub proporciona hospedaje de imágenes de Docker, registros públicos o privados, desencadenadores de compilación y enlaces web e integración con GitHub y Bitbucket.

**Azure Container Registry**: recurso público para trabajar con imágenes de Docker y sus componentes en Azure. Esto proporciona un registro cercano a las implementaciones en Azure que le proporciona control sobre el acceso, lo que le permite usar los grupos y los permisos de Active Directory.

**Docker Trusted Registry (DTR)**: servicio del registro de Docker (ofrecido por Docker) que se puede instalar de forma local, por lo que se encuentra en el centro de datos y la red de la organización. Es ideal para imágenes privadas que deben administrarse dentro de la empresa. Docker Trusted Registry se incluye como parte del producto Docker Datacenter. Para más información, vea [Docker Trusted Registry (DTR)](https://docs.docker.com/docker-trusted-registry/overview/).

**Docker Community Edition (CE)**: herramientas de desarrollo para Windows y MacOS para compilar, ejecutar y probar contenedores localmente. Docker CE para Windows proporciona entornos de desarrollo para contenedores de Windows y Linux. El host de Docker de Linux en Windows se basa en una máquina virtual [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx). El host para los contenedores de Windows se basa directamente en Windows. Docker CE para Mac se basa en el marco del hipervisor de Apple y el [hipervisor xhyve](https://github.com/mist64/xhyve), lo que proporciona una máquina virtual de host de Docker de Linux en Mac OS X. Docker CE para Windows y para Mac sustituye a Docker Toolbox, que se basaba en Oracle VirtualBox.

**Docker Enterprise Edition (EE)**: versión a escala empresarial de las herramientas de Docker para el desarrollo de Linux y Windows.

**Compose**: herramienta de línea de comandos y formato de archivo YAML con metadatos para definir y ejecutar aplicaciones de varios contenedores. Primero se define una sola aplicación basada en varias imágenes con uno o más archivos .yml que pueden invalidar los valores según el entorno. Después de crear las definiciones, puede implementar toda la aplicación de varios contenedores con un solo comando (composición de docker) que crea un contenedor por imagen en el host de Docker.

**Clúster**: colección de hosts de Docker que se expone como si fuera un solo host de Docker virtual, de manera que la aplicación se puede escalar a varias instancias de los servicios repartidos entre varios hosts del clúster. Los clústeres de Docker se pueden crear con Docker Swarm, Mesosphere DC/OS, Kubernetes y Azure Service Fabric. (Cuando se usa Docker Swarm para administrar un clúster, se suele hacer referencia al clúster como un *conjunto* en lugar de un clúster).

**Orquestador**: herramienta que simplifica la administración de clústeres y hosts de Docker. Los orquestadores permiten administrar las imágenes, los contenedores y los hosts a través de una interfaz de línea de comandos (CLI) o una interfaz gráfica de usuario. Puede administrar las redes de contenedor, las configuraciones, el equilibrio de carga, la detección de servicios, la alta disponibilidad, la configuración del host de Docker y muchas cosas más. Un orquestador se encarga de ejecutar, distribuir, escalar y reparar las cargas de trabajo a través de una colección de nodos. Normalmente, los productos del orquestador son los mismos que proporcionan infraestructura de clúster, como Mesosphere DC/OS, Kubernetes, Docker Swarm y Azure Service Fabric.


>[!div class="step-by-step"]
[Previous] (docker-defined.md) [Next] (docker-containers-images-registries.md)
