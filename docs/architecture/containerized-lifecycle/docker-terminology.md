---
title: Terminología de Docker
description: Descubra la terminología básica que se usa habitualmente al trabajar con Docker.
ms.date: 01/06/2021
ms.openlocfilehash: 640c3481e271b8fe2b7d7eeb7d5eaeb02af1cc21
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970107"
---
# <a name="docker-terminology"></a>Terminología de Docker

En esta sección se enumeran los términos y las definiciones que debe conocer antes de profundizar en el uso de Docker. Para consultar más definiciones, lea el amplio [glosario](https://docs.docker.com/glossary/) que Docker proporciona.

**Imagen de contenedor**: un paquete con todas las dependencias y la información necesarias para crear un contenedor. Una imagen incluye todas las dependencias (por ejemplo, los marcos), así como la configuración de implementación y ejecución que usará el runtime de un contenedor. Normalmente, una imagen se deriva de varias imágenes base que son capas que se apilan unas encima de otras para formar el sistema de archivos del contenedor. Una vez que se crea una imagen, esta es inmutable.

**Dockerfile**: archivo de texto que contiene instrucciones sobre cómo compilar una imagen de Docker. Es como un script por lotes; la primera línea indica la imagen base con la que se comienza y, después, deben seguirse las instrucciones para instalar programas necesarios, copiar archivos, etc., hasta obtener el entorno de trabajo que se necesita.

**Compilación**: la acción de crear una imagen de contenedor basada en la información y el contexto que proporciona su Dockerfile, así como archivos adicionales en la carpeta en que se crea la imagen. Puede compilar imágenes con el siguiente comando de Docker:

```bash
docker build
```

**Contenedor**: una instancia de una imagen de Docker. Un contenedor representa la ejecución de una sola aplicación, proceso o servicio. Está formado por el contenido de una imagen de Docker, un entorno de ejecución y un conjunto estándar de instrucciones. Al escalar un servicio, crea varias instancias de un contenedor a partir de la misma imagen. O bien, un proceso por lotes puede crear varios contenedores a partir de la misma imagen y pasar parámetros diferentes a cada instancia.

**Volúmenes**: ofrece un sistema de archivos grabable que el contenedor puede usar. Puesto que las imágenes son de solo lectura pero la mayoría de los programas necesitan escribir en el sistema de archivos, los volúmenes agregan una capa grabable, encima de la imagen de contenedor, por lo que los programas tienen acceso a un sistema de archivos grabable. El programa no sabe que está accediendo a un sistema de archivos por capas, que no es más que el sistema de archivos habitual. Los volúmenes residen en el sistema host y los administra Docker.

**Etiqueta**: una marca o una etiqueta que se puede aplicar a las imágenes para que se puedan identificar diferentes imágenes o versiones de la misma imagen (según el número de versión o el entorno de destino).

**Compilación de varias fases**: es una característica, desde Docker 17.05 o versiones posteriores, que ayuda a reducir el tamaño de las imágenes finales. Por ejemplo, se puede usar una imagen base grande que contenga el SDK para compilar y publicar y una imagen base pequeña solo de tiempo de ejecución para hospedar la aplicación.

**Repositorio**: una colección de imágenes de Docker relacionadas, etiquetadas con una etiqueta que indica la versión de la imagen. Algunos repositorios contienen varias variantes de una imagen específica, como una imagen que contiene SDK (más pesada), una imagen que solo contiene runtimes (más ligera), etcétera. Estas variantes se pueden marcar con etiquetas. Un solo repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.

**Registro**: servicio que proporciona acceso a los repositorios. El registro predeterminado para la mayoría de las imágenes públicas es [Docker Hub](https://hub.docker.com/) (propiedad de Docker como una organización). Normalmente, un registro contiene repositorios procedentes de varios equipos. Las empresas suelen tener registros privados para almacenar y administrar imágenes que han creado. Azure Container Registry es otro ejemplo.

**Imagen multiarquitectura**: En el caso de la arquitectura múltiple, es una característica que simplifica la selección de la imagen adecuada, según la plataforma donde se ejecuta Docker. Por ejemplo, si un Dockerfile solicita una imagen base **FROM mcr.microsoft.com/dotnet/sdk:5.0** del Registro, en realidad obtendrá **5.0-nanoserver-20H2**, **5.0-nanoserver-2004** o **5.0-buster-slim**, según el sistema operativo en el que se ejecute Docker y la versión.

**Docker Hub**: registro público para cargar imágenes y trabajar con ellas. Docker Hub proporciona hospedaje de imágenes de Docker, registros públicos o privados, desencadenadores de compilación y enlaces web e integración con GitHub y Bitbucket.

**Azure Container Registry**: recurso público para trabajar con imágenes de Docker y sus componentes en Azure. Esto proporciona un registro cercano a las implementaciones en Azure que le proporciona control sobre el acceso, lo que le permite usar los grupos y los permisos de Azure Active Directory.

**Docker Trusted Registry (DTR)** : servicio del registro de Docker (ofrecido por Docker) que se puede instalar de forma local, por lo que se encuentra en el centro de datos y la red de la organización. Es ideal para imágenes privadas que deben administrarse dentro de la empresa. Docker Trusted Registry se incluye como parte del producto Docker Datacenter. Para más información, vea [Docker Trusted Registry (DTR)](https://www.docker.com/sites/default/files/Docker%20Trusted%20Registry.pdf).

**Docker Community Edition (CE)** : herramientas de desarrollo para Windows y MacOS para compilar, ejecutar y probar contenedores localmente. Docker CE para Windows proporciona entornos de desarrollo para contenedores de Windows y Linux. El host de Docker de Linux en Windows se basa en una máquina virtual [Hyper-V](https://www.microsoft.com/cloud-platform/server-virtualization). El host para los contenedores de Windows se basa directamente en Windows. Docker CE para Mac se basa en el marco del hipervisor de Apple y el [hipervisor xhyve](https://github.com/mist64/xhyve), lo que proporciona una máquina virtual de host de Docker de Linux en Mac OS X. Docker CE para Windows y para Mac sustituye a Docker Toolbox, que se basaba en Oracle VirtualBox.

**Docker Enterprise Edition (EE)** : versión a escala empresarial de las herramientas de Docker para el desarrollo de Linux y Windows.

**Compose**: herramienta de línea de comandos y formato de archivo YAML con metadatos para definir y ejecutar aplicaciones de varios contenedores. Primero se define una sola aplicación basada en varias imágenes con uno o más archivos .yml que pueden invalidar los valores según el entorno. Después de crear las definiciones, puede implementar toda la aplicación de varios contenedores con un solo comando (docker-compose up) que crea un contenedor por imagen en el host de Docker.

**Clúster**: colección de hosts de Docker que se expone como si fuera un solo host de Docker virtual, de manera que la aplicación se puede escalar a varias instancias de los servicios repartidos entre varios hosts del clúster. Los clústeres de Docker se pueden crear con Kubernetes, Azure Service Fabric, Docker Swarm y Mesosphere DC/OS.

**Orquestador**: herramienta que simplifica la administración de clústeres y hosts de Docker. Los orquestadores permiten administrar las imágenes, los contenedores y los hosts a través de una interfaz de la línea de comandos (CLI) o una interfaz gráfica de usuario. Puede administrar las redes de contenedor, las configuraciones, el equilibrio de carga, la detección de servicios, la alta disponibilidad, la configuración del host de Docker y muchas cosas más. Un orquestador se encarga de ejecutar, distribuir, escalar y reparar las cargas de trabajo a través de una colección de nodos. Normalmente, los productos del orquestador son los mismos que proporcionan infraestructura de clúster, como Kubernetes y Azure Service Fabric, entre otras ofertas del mercado.

>[!div class="step-by-step"]
>[Anterior](what-is-docker.md)
>[Siguiente](docker-containers-images-and-registries.md)
