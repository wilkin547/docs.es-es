---
title: Implementación de aplicaciones .NET existentes como contenedores de Windows
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Implementar aplicaciones .NET existentes como contenedores de Windows
ms.date: 04/29/2018
ms.openlocfilehash: 77d10867573765a7e86a9827825e1313de7a3035
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643753"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Implementación de aplicaciones .NET existentes como contenedores de Windows

Las implementaciones basadas en contenedores de Windows son aplicables a las aplicaciones optimizadas para la nube y aplicaciones nativas de nube.

Sin embargo, en esta guía y especialmente en las secciones siguientes, se centra principalmente en el uso de contenedores de Windows para *optimizada para la nube* aplicaciones donde no es necesario rediseñar la aplicación.

## <a name="what-are-containers-linux-or-windows"></a>¿Qué son los contenedores? (Linux o Windows)

Los contenedores son una manera de encapsular una aplicación en su propio paquete aislado. En su contenedor, la aplicación no se ve afectada por las aplicaciones o procesos que existen fuera del contenedor. Todo lo que la aplicación depende de sesión para ejecutar correctamente como un proceso está dentro del contenedor. Siempre puede mover el contenedor, los requisitos de la aplicación siempre se cumplirá, en términos de dependencias directas, ya que se incluye con todo lo que necesita para ejecutar (dependencias de biblioteca, los tiempos de ejecución etc.).

La característica principal de un contenedor es que hace el entorno de la misma entre las distintas implementaciones porque el propio contenedor incluye todas las dependencias necesarias. Puede depurar la aplicación en el equipo y, a continuación, implementarla en otro equipo, con el mismo entorno garantizado.

Un contenedor es una instancia de una imagen de contenedor. Una imagen de contenedor es una manera de empaquetar una aplicación o servicio (por ejemplo, una instantánea) y, a continuación, implementarlo de forma confiable y reproducible. Podría decir que Docker no es que sólo una TI tecnología también una filosofía y un proceso.

Como contenedores diariamente se vuelven más comunes, se están convirtiendo en un sector "unidad de implementación".

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Ventajas de los contenedores (motor de Docker en Linux o Windows)

Creación de aplicaciones mediante el uso de contenedores, lo que también puede ser definido como ofertas de bloques de creación ligeras un aumento significativo en agilidad para compilar, enviar y ejecutar cualquier aplicación, a través de cualquier infraestructura.

Con contenedores, puede aprovechar cualquier aplicación desde el desarrollo a producción con pocos o ningún cambio de código, gracias a la integración de Docker a través de herramientas de desarrollo de Microsoft, los sistemas operativos y en la nube.

Cuando se implementa en máquinas virtuales sin formato, probablemente ya tiene un método en su lugar para implementar aplicaciones ASP.NET a las máquinas virtuales. Sin embargo, es probable, que su método implica varios pasos manuales o procesos automatizados complejos mediante el uso de una herramienta de implementación, como Puppet, u otra herramienta similar. Es posible que deba realizar tareas como la modificación de los elementos de configuración, copiar contenido entre servidores de la aplicación y ejecutar programas de instalación interactiva basados en las instalaciones de .msi, seguidas de las pruebas. Todos estos pasos en la implementación agregan tiempo y los riesgos para las implementaciones. Se producen errores cada vez que una dependencia no está presente en el entorno de destino.

En los contenedores de Windows, el proceso de empaquetado de aplicaciones está totalmente automatizado. Contenedores de Windows se basa en la plataforma Docker, que ofrece actualizaciones automáticas y reversiones de implementaciones de contenedor. La principal mejora que obtendrá de usar con el motor de Docker es la creación de imágenes, que son como las instantáneas de la aplicación, con todas sus dependencias. Las imágenes son imágenes de Docker (en este caso, una imagen de contenedor Windows). Las imágenes de que las aplicaciones de ASP.NET se ejecutan en contenedores, sin tener que volver al código fuente. La instantánea del contenedor se convierte en la unidad de implementación.

Muchas organizaciones están incluir en un contenedor aplicaciones monolíticas existentes por las razones siguientes:

- **Versión agilidad a través de implementación mejoradas**. Los contenedores ofrecen un contrato de la implementación coherente entre el desarrollo y operaciones. Cuando se usa contenedores, no escuchará a los desarrolladores dicen, "Funciona en mi equipo, ¿por qué no en producción?" Puede decir, "se ejecuta como un contenedor, para que se ejecute en producción." La aplicación empaquetada, con todas sus dependencias, se puede ejecutar en cualquier entorno compatible con basadas en contenedores. Se ejecutará la manera en que estaba pensado para ejecutarse en todos los destinos de implementación (desarrollo, control de calidad, ensayo y producción). Contenedores eliminan la mayoría de fricción cuando pasan de una fase a la siguiente, lo que mejora considerablemente la implementación, y se pueden enviar con mayor rapidez.

- **Reducciones de costos**. Contenedores de dar lugar a reducir los costes, ya sea mediante la consolidación y la eliminación del hardware existente, o mediante la ejecución de aplicaciones en una mayor densidad por unidad de hardware.

- **Portabilidad**. Los contenedores son modulares y portátil. Se admiten contenedores de docker en cualquier sistema operativo (Windows y Linux), en cualquier nube pública principal (Microsoft Azure, Amazon AWS, Google, IBM) en un entorno local y privada o entornos de nube híbrida.

- **Control**. Los contenedores ofrecen un entorno flexible y seguro que se controla en el nivel de contenedor. Un contenedor puede protegido, aislado y limitado incluso estableciendo directivas de restricción de ejecución en el contenedor. Como se detalla en la sección acerca de los contenedores de Windows, los contenedores de Hyper-V y Windows Server 2016 ofrecen opciones de soporte técnico de enterprise adicionales.

Mejoras considerables en agilidad, portabilidad y control en última instancia, produzcan reducciones considerables del costo al usar contenedores para desarrollar y mantener aplicaciones.

## <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) que automatiza la implementación de aplicaciones como contenedores portátiles y autosuficientes que se pueden ejecutar en la nube o local. Docker es también una [empresa](https://www.docker.com/) que promueve esta tecnología y la hace evolucionar. La compañía trabaja en colaboración con la nube, Linux y los proveedores de Windows, incluido Microsoft.

![](./media/image6.png)

> **Figura 4-6.** Docker implementa contenedores en todas las capas de la nube híbrida

Para alguien familiarizado con las máquinas virtuales, contenedores podrían parecer muy similar. Un contenedor ejecuta un sistema operativo, tiene un sistema de archivos y puede obtenerse a través de una red, al igual que un sistema de equipo físico o virtual. Sin embargo, la tecnología y los conceptos de los contenedores son considerablemente diferentes de las máquinas virtuales. Desde un punto de vista del desarrollador, un contenedor debe tratarse más como un único proceso. De hecho, un contenedor tiene un único punto de entrada para un proceso.

Contenedores de docker (por motivos de simplicidad, *contenedores*) puede ejecutar de forma nativa en Linux y Windows. Al ejecutar contenedores normales, los contenedores de Windows sólo pueden ejecutarse en hosts de Windows (un servidor host o una máquina virtual) y contenedores de Linux solo pueden ejecutarse en hosts de Linux. Sin embargo, en las versiones recientes de los contenedores de Hyper-V y Windows Server, un contenedor de Linux también puede ejecutar forma nativa en Windows Server mediante la tecnología de aislamiento de Hyper-V que actualmente está disponible solo en contenedores de Windows Server.

En un futuro próximo, entornos mixtos que tienen contenedores de Linux y Windows será posible e incluso habitual.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Ventajas de los contenedores de Windows para las aplicaciones .NET existentes

Las ventajas de utilizar contenedores de Windows son fundamentalmente las mismas ventajas que obtendrá de contenedores en general. Uso de contenedores de Windows consiste en lo que mejora significativamente la agilidad, portabilidad y el control.

Las aplicaciones .NET existentes hacen referencia a las aplicaciones que se crearon con .NET Framework. Por ejemplo, que pueden las aplicaciones web ASP.NET tradicionales-no usan .NET Core, que es más reciente y se ejecuta entre plataformas en Linux, Windows y MacOS.

La dependencia en .NET Framework principal es Windows. También tiene dependencias secundarias, como IIS y System.Web en ASP.NET tradicional.

Una aplicación de .NET Framework debe ejecutar en Windows, período. Si desea incluir las aplicaciones existentes de .NET Framework y no puede o no desea invertir en una migración a .NET Core ("si funciona correctamente, no mígrela"), es la única opción que tiene para los contenedores se usan contenedores de Windows.

Por lo tanto, una de las principales ventajas de los contenedores de Windows es que le ofrecen una manera de modernizar las aplicaciones existentes de .NET Framework que se ejecutan en Windows a través de contenedores. En última instancia, los contenedores de Windows obtiene los beneficios que buscan mediante el uso de contenedores de agilidad, portabilidad y un mejor control.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Elegir un destino con sistema operativo. Contenedores basados en red

Dada la diversidad de sistemas operativos que son compatibles con Docker, así como las diferencias entre .NET Framework y .NET Core, debe dirigirse un sistema operativo específico y versiones específicas según el marco de trabajo que está usando.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (como IIS frente a un servidor web autohospedado como Kestrel) que podrían ser necesarios en las aplicaciones de .NET Framework o .NET Core.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

Figura 4-7 muestra las versiones del sistema operativo que puede usar como destino, según la versión de la aplicación de .NET Framework.

![](./media/image7.png)

> **Figura 4-7.** Sistemas operativos de destino basándose en la versión de .NET Framework

En escenarios de migración para las aplicaciones existentes o heredadas que se basan en las aplicaciones de .NET Framework, las dependencias principales están en Windows e IIS. La única opción es usar imágenes de Docker basadas en Windows Server Core y .NET Framework.

Cuando se agrega el nombre de la imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión mediante el uso de una etiqueta, como se muestra en los siguientes ejemplos de imágenes de contenedor de .NET Framework en Windows:

> | **Tag** | **Versión del sistema y** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x en Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4.x con personalización de ASP.NET adicionales, en Windows Server Core |

Para .NET Core (multiplataforma para Linux y Windows), las etiquetas tendrá un aspecto similar al siguiente:

> | **Tag** | **Versión del sistema y**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET core 2.0 en tiempo de ejecución solo en Linux |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET core 2.0 en tiempo de ejecución solo en Windows Nano Server |

### <a name="multi-arch-images"></a>Imágenes multiarquitectura

A partir de mediados de 2017, también puede usar una nueva característica de Docker denominada [multiarquitectura](https://github.com/moby/moby/issues/15866) imágenes. Las imágenes de Docker de .NET core pueden usar etiquetas de varias arquitecturas. El Dockerfile archivos ya no necesidad de definir el sistema operativo que tiene como destino. La característica de varias arquitecturas permite una única etiqueta que se usará en varias configuraciones de máquina. Por ejemplo, con varias arquitecturas, puede usar una etiqueta común: **microsoft/dotnet:2.0.0-runtime**. Si extrae esa etiqueta desde un entorno de contenedor de Linux, obtendrá la imagen de Debian. Si extrae esa etiqueta desde un entorno de contenedor de Windows, obtendrá la imagen de Nano Server.

Para las imágenes de .NET Framework, porque el tradicional .NET Framework admite solo en Windows, no puede usar la característica de varias arquitecturas.

## <a name="windows-container-types"></a>Tipos de contenedores de Windows

Como los contenedores de Linux, contenedores de Windows Server se administran mediante el motor de Docker. A diferencia de los contenedores de Linux, contenedores de Windows incluyen dos tipos de contenedor diferente o ejecuten el aislamiento de Hyper-V y contenedores de veces Windows Server.

**Contenedores de Windows Server**: Proporciona el aislamiento de aplicaciones mediante tecnología de aislamiento de proceso y espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y todos los contenedores que se ejecutan en el host. Estos contenedores no proporcionan un límite de seguridad hostil y no deben usarse para aislar código no seguro. Debido al espacio de kernel compartido, estos contenedores requieren la misma versión de kernel y la configuración.

**Aislamiento de Hyper-V**: Expande el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host del contenedor no se comparte con otros contenedores en el mismo host. Estos contenedores están diseñados para hospedar varios inquilinos hostiles, con las mismas garantías de seguridad de una máquina virtual. Dado que estos contenedores no comparten el kernel con el host u otros contenedores en el host, se pueden ejecutar kernels con distintas versiones y configuraciones (con las versiones compatibles). Por ejemplo, todos los contenedores de Windows en Windows 10 utilice el aislamiento de Hyper-V para usar la versión del kernel de Windows Server y la configuración.

Ejecutar un contenedor en Windows con o sin aislamiento de Hyper-V es una decisión de tiempo de ejecución. Puede optar por crear inicialmente el contenedor con el aislamiento de Hyper-V y en tiempo de ejecución, elija Ejecutar como un contenedor de Windows Server.

### <a name="additional-resources"></a>Recursos adicionales

- **Documentación de contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Aspectos básicos de contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografía: Microsoft y contenedores**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>El ecosistema de contenedor en Azure

En las secciones anteriores, se ha explicado ¿cuáles son las ventajas de los contenedores de Docker, así como detalles sobre las imágenes de contenedor específico para las aplicaciones. NET. Información genérica todo lo que es fundamental para desarrollar o incluir una aplicación.
Sin embargo, al pensar en el entorno de implementación de producción o incluso los entornos de desarrollo y pruebas y control de calidad, Microsoft Azure proporciona una abierto y una amplia variedad de opciones, un ecosistema de contenedor completa en la nube (que se muestra en el diagrama siguiente). Según las necesidades de su aplicación en concreto, debe elegir uno u otro producto de Azure.

![](./media/image7.5.png)

> **Figura 4-7.5.** El ecosistema de contenedor en Azure

En el ecosistema de contenedor en Azure, los siguientes productos admiten los contenedores que se consideran infraestructura:
- **Azure Container Instances (ACI)**
- **Máquinas virtuales de Azure** (con el soporte técnico del contenedor)
- **Azure Virtual Machine Scale Sets** (con el soporte técnico del contenedor)

Entre esos tres, ACI ofrece una gran ventaja, que es el hecho de que no es necesario mantener el sistema operativo subyacente, no hay necesidad de actualizar/aplicar revisiones, etc. pero ACI todavía se coloca en el nivel de infraestructura, como se explica mejor en las próximas secciones de este libro.

Los productos en Azure contenedores auxiliares que están a la vez que coloca más en la PaaS (plataforma como servicio) niveles son:

- **Azure App Service**
- **Azure Kubernetes Service (AKS y ACS)**
- **Azure Service Fabric** 
- **Azure Batch** 

A continuación, Azure Container Registry es un registro de contenedor escalable alto hospedado en Azure que puede usar en todos los productos anteriores al registrar e implementar las imágenes de contenedor personalizado.

Además, de los contenedores, pueden consumir otros servicios administrados en Azure como Azure SQL Database, Azure Redis cache, Azure Cosmos DB, etcetera. Además, hay soluciones y plataformas de terceros en Azure Marketplace, como Cloud Foundry y OpenShift donde también puede usar contenedores dentro de Azure. 

En las secciones siguientes, puede explorar las recomendaciones de Microsoft sobre cuándo usar cada una de esas soluciones y productos de Azure, en concreto cuando el destino son contenedores de Windows.

>[!div class="step-by-step"]
>[Anterior](what-about-cloud-native-applications.md)
>[Siguiente](when-not-to-deploy-to-windows-containers.md)
