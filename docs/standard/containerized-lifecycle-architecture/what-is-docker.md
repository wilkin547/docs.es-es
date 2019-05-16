---
title: ¿Qué es Docker?
description: Obtener un poco más en sus conocimientos de Docker, aquí una analogía simple puede ayudarle.
ms.date: 02/15/2019
ms.openlocfilehash: 7747c4985af27be0a073fad2f22622f697f4ce27
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644779"
---
# <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) para automatizar la implementación de aplicaciones como contenedores portátiles y autosuficientes que se pueden ejecutar en la nube o localmente. Docker es también una [empresa](https://www.docker.com/) que promueve e impulsa esta tecnología, en colaboración con proveedores de la nube, Linux y Windows, incluido Microsoft.

![Los contenedores de Docker se pueden ejecutar en cualquier lugar, a nivel local en el centro de datos de cliente, en un proveedor de servicios externo o en la nube, en Azure.](./media/image2.png)

**Figura 1-2**. Docker implementa contenedores en todas las capas de la nube híbrida

Los contenedores de imagen de Docker se pueden ejecutar de forma nativa en Linux y Windows. Sin embargo, las imágenes de Windows solo pueden ejecutarse en hosts de Windows y las imágenes de Linux pueden ejecutarse en hosts de Linux y hosts de Windows (con una máquina virtual Linux de Hyper-V, hasta el momento), donde host significa un servidor o una máquina virtual.

Los desarrolladores pueden usar entornos de desarrollo en Windows, Linux o macOS. En el equipo de desarrollo, el desarrollador ejecuta un host de Docker en que se implementan imágenes de Docker, incluidas la aplicación y sus dependencias. Los desarrolladores que trabajan en Linux o en el equipo Mac, use un host de Docker que está basado en Linux, y solo pueden crear imágenes para contenedores de Linux. (Los desarrolladores que trabajan en el equipo Mac pueden editar código o ejecutar la interfaz de línea de comandos (CLI) de Docker en macOS, pero cuando se redactó este documento, no se ejecutan los contenedores directamente en macOS). Los desarrolladores que trabajan en Windows pueden crear imágenes para contenedores de Windows o Linux.

Para hospedar contenedores en entornos de desarrollo y proporcionar herramientas de desarrollador adicionales, Docker entrega [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows o macOS. Estos productos instalan la máquina virtual necesaria (el host de Docker) para hospedar los contenedores. Docker también pone a disposición [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), que está diseñado para el desarrollo empresarial y se usa en los equipos de TI que crean, envían y ejecutan aplicaciones críticas para la empresa en producción.

Para ejecutar [contenedores de Windows](/virtualization/windowscontainers/about/), hay dos tipos de tiempos de ejecución:

- **Contenedores de Windows Server** ofrecen aislamiento de aplicaciones mediante tecnología de aislamiento de proceso y espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y con todos los contenedores que se ejecutan en el host.

- **Contenedores de Hyper-V** amplían el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host del contenedor no se comparte con los contenedores de Hyper-V, lo que proporciona un mejor aislamiento.

Las imágenes de estos contenedores se crean y funcionan de la misma manera. La diferencia radica en cómo se crea el contenedor de la imagen, la ejecución de un contenedor de Hyper-V requiere un parámetro adicional. Para más información, vea [Contenedores de Hyper-V](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Comparación de los contenedores de Docker con las máquinas virtuales

Figura 1-3 se muestra una comparación entre las máquinas virtuales y Docker contenedores.

![Para las máquinas virtuales, hay tres niveles de base en el servidor host, de manera ascendente: infraestructura, sistema operativo host y un hipervisor y, encima de todo eso, cada máquina virtual tiene su propio sistema operativo y todas las bibliotecas necesarias. Por otro lado, para Docker, el servidor host sólo tiene la infraestructura y el sistema operativo y en él, el motor de contenedor, que mantiene contenedor aislado pero el uso compartido de los servicios del sistema operativo bases.](./media/image3.png)

**Figura 1-3**. Comparación de las máquinas virtuales tradicionales con los contenedores de Docker

Dado que los contenedores requieren muchos menos recursos (por ejemplo, no necesitan un sistema operativo completo), se inician rápidamente y son fáciles de implementar. Esto permite tener una mayor densidad, lo que significa que se pueden ejecutar más servicios en la misma unidad de hardware, reduciendo así los costos.

Como efecto secundario de la ejecución en el mismo kernel, obtiene menos aislamiento que las máquinas virtuales.

El objetivo principal de una imagen es garantizar el mismo entorno (dependencias) entre las distintas implementaciones. Esto significa que puede depurarlo en su equipo y, a continuación, implementarla en otro equipo, el mismo entorno garantizado.

Una imagen de contenedor es una manera de empaquetar una aplicación o un servicio e implementarlo de forma confiable y reproducible. Podría decir que Docker no solo es una tecnología, sino también una filosofía y un proceso.

Al usar Docker, no escuchará a los desarrolladores decir "Si funciona en mi máquina, ¿por qué no en producción?". Puede mencionar solamente "Se ejecuta en Docker", porque se puede ejecutar la aplicación de Docker empaquetada en cualquier entorno de Docker de admitido y se ejecuta la manera en que se pretende en todos los destinos de implementación (por ejemplo, desarrollo, control de calidad, ensayo y producción).

## <a name="a-simple-analogy"></a>Una analogía simple

Quizás una analogía simple puede ayudar a entender el concepto básico de Docker.

Vamos a remontarnos a la década de 1950 por un momento. No había ningún procesadores de textos y el fotocopiadoras se usaron en todas partes (bueno, más).

Imagine que es responsable de enviar lotes de cartas, según proceda, para enviarlas por correo a los clientes en papel y sobres reales, que se entregarán físicamente en la dirección postal de cada cliente (entonces no existía el correo electrónico).

En algún momento, se da cuenta de que las letras no son más que una composición de un conjunto grande de párrafos, que se eligen y ordenan según proceda, según el propósito de la carga, por lo que diseña un sistema para emitir cartas rápidamente, esperando conseguir una increíble mejora.

El sistema es simple:

1. Comience con un conjunto de hojas transparentes que contienen un párrafo.

2. Para emitir un conjunto de cartas, elija las hojas con los párrafos necesarios, apílelas y alinéelas para que queden y se lean bien.

3. Por último, colóquelas en la fotocopiadora y presione inicio para producir tantas cartas como sean necesarias.

Por tanto, para simplificar, esa es la idea principal de Docker.

En Docker, cada capa es el conjunto resultante de los cambios que se producen en el sistema de archivos después de ejecutar un comando, como instalar un programa.

Por lo tanto, al "Examinar" el sistema de archivos después de que se ha copiado la capa, verá todos los archivos, incluida la capa cuando se instaló el programa.

Puede pensar en una imagen como un disco duro de solo lectura auxiliar listo para instalarse en un "equipo" donde el sistema operativo ya está instalado.

De forma similar, puede pensar en un contenedor como el "equipo" con el disco duro de imagen instalado. El contenedor, como un equipo, se puede apagar o desactivar.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](docker-terminology.md)
