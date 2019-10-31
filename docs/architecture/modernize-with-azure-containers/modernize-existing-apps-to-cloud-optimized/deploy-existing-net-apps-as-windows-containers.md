---
title: Implementación de aplicaciones .NET existentes como contenedores de Windows
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Implementación de aplicaciones .NET existentes como contenedores de Windows
ms.date: 04/29/2018
ms.openlocfilehash: 28568ca363bfc8100f78b100f8a7f0242c4f04c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089556"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Implementación de aplicaciones .NET existentes como contenedores de Windows

Las implementaciones basadas en contenedores de Windows se aplican a aplicaciones optimizadas para la nube y aplicaciones nativas en la nube.

Sin embargo, en esta guía y especialmente en las secciones siguientes, se centra principalmente en el uso de contenedores de Windows para aplicaciones *optimizadas para la nube* donde no es necesario rediseñar la aplicación.

## <a name="what-are-containers-linux-or-windows"></a>¿Qué son los contenedores? (Linux o Windows)

Los contenedores son una manera de encapsular una aplicación en su propio paquete aislado. En su contenedor, la aplicación no se ve afectada por las aplicaciones o procesos que existen fuera del contenedor. Todo lo que depende la aplicación para que se ejecute correctamente cuando un proceso está dentro del contenedor. Siempre que el contenedor pueda moverse, se cumplirán los requisitos de la aplicación, en términos de dependencias directas, porque se incluye todo lo que necesita para ejecutarse (dependencias de biblioteca, tiempos de ejecución, etc.).

La característica principal de un contenedor es que hace que el entorno sea el mismo en las distintas implementaciones porque el propio contenedor incluye todas las dependencias que necesita. Puede depurar la aplicación en la máquina y, a continuación, implementarla en otra máquina, con el mismo entorno garantizado.

Un contenedor es una instancia de una imagen de contenedor. Una imagen de contenedor es una manera de empaquetar una aplicación o un servicio (como una instantánea) y, a continuación, implementarla de forma confiable y reproducible. Podría decir que Docker no es solo una tecnología, sino también una filosofía y un proceso.

A medida que los contenedores son cada vez más comunes, se están convirtiendo en una "unidad de implementación" en todo el sector.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Ventajas de los contenedores (motor de Docker en Linux o Windows)

Compilar aplicaciones mediante contenedores, que también podrían definirse como bloques de creación ligeros, ofrece un aumento significativo en la agilidad para crear, enviar y ejecutar cualquier aplicación, en cualquier infraestructura.

Con los contenedores, puede realizar cualquier aplicación desde el desarrollo hasta la producción con poco o ningún cambio de código, gracias a la integración de Docker entre las herramientas de desarrollo de Microsoft, los sistemas operativos y la nube.

Cuando se implementa en máquinas virtuales sin formato, es probable que ya tenga un método para implementar aplicaciones de ASP.NET en las máquinas virtuales. Sin embargo, es probable que el método implique varios pasos manuales o complejos procesos automatizados mediante una herramienta de implementación como posición libre o una herramienta similar. Es posible que necesite realizar tareas como la modificación de elementos de configuración, la copia de contenido de la aplicación entre servidores y la ejecución de programas de instalación interactiva basados en configuraciones. msi, seguidos de pruebas. Todos los pasos de la implementación agregan tiempo y riesgo a las implementaciones. Obtendrá errores cada vez que una dependencia no esté presente en el entorno de destino.

En los contenedores de Windows, el proceso de empaquetado de aplicaciones está totalmente automatizado. Los contenedores de Windows se basan en la plataforma Docker, que ofrece actualizaciones automáticas y reversiones para implementaciones de contenedores. La mejora principal que obtiene al usar el motor de Docker es que crea imágenes, que son como las instantáneas de la aplicación, con todas sus dependencias. Las imágenes son imágenes de Docker (una imagen de contenedor de Windows, en este caso). Las imágenes ejecutan aplicaciones de ASP.NET en contenedores, sin volver al código fuente. La instantánea de contenedor se convierte en la unidad de implementación.

Muchas organizaciones están contenedores de aplicaciones monolíticas existentes por las siguientes razones:

- **Mejore la agilidad a través de una implementación mejorada**. Los contenedores ofrecen un contrato de implementación coherente entre el desarrollo y las operaciones. Cuando se usan contenedores, no se escucha a los desarrolladores, por ejemplo, "funciona en mi máquina, ¿por qué no se encuentra en producción?" Pueden decir "que se ejecuta como un contenedor, por lo que se ejecutará en producción". La aplicación empaquetada, con todas sus dependencias, se puede ejecutar en cualquier entorno basado en contenedor compatible. Se ejecutará la forma en que se diseñó para ejecutarse en todos los destinos de implementación (dev, QA, staging, producción). Los contenedores eliminan la mayoría de las fricción cuando pasan de una fase a la siguiente, lo que mejora en gran medida la implementación, y se puede enviar más rápidamente.

- **Reducción de costos**. Los contenedores conducen a costos reducidos, ya sea por la consolidación y la eliminación de hardware existente, o desde aplicaciones en ejecución a una densidad superior por unidad de hardware.

- **Portabilidad**. Los contenedores son modulares y portátiles. Los contenedores de Docker se admiten en cualquier sistema operativo de servidor (Linux y Windows), en cualquier nube pública principal (Microsoft Azure, Amazon AWS, Google, IBM) y en entornos de nube locales y privados o híbridos.

- **Control**. Los contenedores ofrecen un entorno flexible y seguro que se controla en el nivel de contenedor. Un contenedor se puede proteger, aislar e incluso limitar estableciendo directivas de restricción de ejecución en el contenedor. Tal como se detalla en la sección acerca de los contenedores de Windows, los contenedores de Windows Server 2016 y Hyper-V ofrecen opciones adicionales de soporte técnico empresarial.

En última instancia, las mejoras significativas en la agilidad, la portabilidad y el control conducen a importantes reducciones de costos cuando se usan contenedores para desarrollar y mantener aplicaciones.

## <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) que automatiza la implementación de aplicaciones como contenedores portátiles y autosuficientes que se pueden ejecutar en la nube o de forma local. Docker es también una [empresa](https://www.docker.com/) que promueve esta tecnología y la hace evolucionar. La compañía trabaja en colaboración con proveedores de nube, Linux y Windows, incluido Microsoft.

![Diagrama que muestra cómo Docker implementa contenedores en la nube híbrida.](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**Figura 4-6.** Docker implementa contenedores en todas las capas de la nube híbrida

Para alguien familiarizado con las máquinas virtuales, es posible que los contenedores parezcan bastante similares. Un contenedor ejecuta un sistema operativo, tiene un sistema de archivos y se puede acceder a él a través de una red, al igual que un sistema de equipo físico o virtual. Sin embargo, la tecnología y los conceptos relacionados con los contenedores son muy diferentes de las máquinas virtuales. Desde el punto de vista del desarrollador, un contenedor se debe tratar más como un proceso único. De hecho, un contenedor tiene un único punto de entrada para un proceso.

Los contenedores de Docker (para simplificar, los *contenedores*) se pueden ejecutar de forma nativa en Linux y Windows. Al ejecutar contenedores normales, los contenedores de Windows solo pueden ejecutarse en hosts de Windows (un servidor host o una máquina virtual), y los contenedores de Linux solo pueden ejecutarse en hosts Linux. Sin embargo, en las versiones recientes de los contenedores de Windows Server y Hyper-V, un contenedor de Linux también se puede ejecutar de forma nativa en Windows Server mediante la tecnología de aislamiento de Hyper-V que actualmente está disponible solo en los contenedores de Windows Server.

En un futuro próximo, los entornos mixtos con contenedores de Linux y Windows serán posibles e incluso comunes.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Ventajas de los contenedores de Windows para las aplicaciones .NET existentes

Las ventajas de usar contenedores de Windows son fundamentalmente las mismas ventajas que se obtienen de los contenedores en general. El uso de contenedores de Windows consiste en mejorar considerablemente la agilidad, la portabilidad y el control.

Las aplicaciones .NET existentes hacen referencia a las aplicaciones que se crearon con el .NET Framework. Por ejemplo, puede tratarse de aplicaciones Web de ASP.NET tradicionales: no usan .NET Core, que es más reciente y se ejecuta en varias plataformas en Linux, Windows y MacOS.

La dependencia principal en el .NET Framework es Windows. También tiene dependencias secundarias, como IIS, y System. Web en ASP.NET tradicionales.

Una aplicación .NET Framework se debe ejecutar en Windows, period. Si desea incluir en un contenedor aplicaciones .NET Framework existentes y no puede o no desea invertir en una migración a .NET Core ("si funciona correctamente, no migrar"), la única opción que tiene para los contenedores es usar contenedores de Windows.

Por lo tanto, una de las principales ventajas de los contenedores de Windows es que ofrecen una manera de modernizar las aplicaciones .NET Framework existentes que se ejecutan en Windows a través de la inclusión en contenedores. En última instancia, los contenedores de Windows le aportan las ventajas que está buscando mediante contenedores: agilidad, portabilidad y un mejor control.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Elija un sistema operativo de destino. Contenedores basados en NET

Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker, así como las diferencias entre .NET Framework y .NET Core, debe tener como destino un sistema operativo específico y versiones específicas basadas en el marco de trabajo que usa.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (como IIS y un servidor Web autohospedado como Kestrel) que podrían ser necesarias para las aplicaciones de .NET Core o de .NET Framework.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

En la figura 4-7 se muestran las versiones del sistema operativo a las que puede dirigirse, en función de la versión de la aplicación del .NET Framework.

![Diagrama que muestra el sistema operativo al que se destina en función de la versión de .NET Framework.](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**Figura 4-7.** Sistemas operativos de destino en función de la versión de .NET Framework

En los escenarios de migración de aplicaciones existentes o heredadas basadas en .NET Framework aplicaciones, las dependencias principales se encuentran en Windows e IIS. La única opción es usar imágenes de Docker basadas en Windows Server Core y en el .NET Framework.

Al agregar el nombre de la imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión mediante una etiqueta, como en los ejemplos siguientes para imágenes de contenedor de Windows basadas en .NET Framework:

> | **Etiqueta** | **Sistema y versión** |
> |---|---|
> | **Microsoft/dotnet-Framework: 4. x-windowsservercore** | .NET Framework 4. x en Windows Server Core |
> | **Microsoft/ASPNET: 4. x-windowsservercore** | .NET Framework 4. x con personalización ASP.NET adicional, en Windows Server Core |

Para .NET Core (multiplataforma para Linux y Windows), las etiquetas tendrían el aspecto siguiente:

> | **Etiqueta** | **Sistema y versión**
> |---|---|
> | **Microsoft/dotnet: 2.0.0-Runtime** | Tiempo de ejecución de .NET Core 2,0: solo en Linux |
> | **Microsoft/dotnet: 2.0.0-Runtime-nanoserver** | .NET Core 2,0 Runtime solo en Windows nano Server |

### <a name="multi-arch-images"></a>Imágenes de múltiples sistemas

A partir de mediados de 2017, también puede usar una nueva característica de Docker denominada imágenes [de varios arcos](https://github.com/moby/moby/issues/15866) . Las imágenes de Docker de .NET Core pueden usar etiquetas multi-Arch. Los archivos de Dockerfile ya no necesitan definir el sistema operativo de destino. La característica multi-Arch permite usar una sola etiqueta en varias configuraciones de máquina. Por ejemplo, con multi-Arch, puede usar una etiqueta común: **Microsoft/dotnet: 2.0.0-Runtime**. Si extrae esa etiqueta de un entorno de contenedores de Linux, obtendrá la imagen basada en Debian. Si extrae esa etiqueta de un entorno de contenedor de Windows, obtendrá la imagen basada en nano Server.

En el caso de las imágenes de .NET Framework, ya que el .NET Framework tradicional solo admite Windows, no puede usar la característica de múltiples funciones.

## <a name="windows-container-types"></a>Tipos de contenedor de Windows

Como los contenedores de Linux, los contenedores de Windows Server se administran mediante el motor de Docker. A diferencia de los contenedores de Linux, los contenedores de Windows incluyen dos tipos diferentes de contenedores o tiempos de ejecución: los contenedores de Windows Server y el aislamiento de Hyper-V.

**Contenedores de Windows Server**: proporcionan aislamiento de aplicaciones a través de la tecnología de aislamiento de procesos y espacios de nombres. Un contenedor de Windows Server comparte un kernel con el host de contenedor y todos los contenedores que se ejecutan en el host. Estos contenedores no proporcionan un límite de seguridad hostil y no se deben usar para aislar el código que no es de confianza. Debido al espacio compartido del kernel, estos contenedores requieren la misma versión y configuración de kernel.

**Aislamiento de Hyper-V**: amplía el aislamiento proporcionado por los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host de contenedor no se comparte con otros contenedores en el mismo host. Estos contenedores están diseñados para el hospedaje de varios inquilinos hostiles, con las mismas garantías de seguridad de una máquina virtual. Dado que estos contenedores no comparten el kernel con el host u otros contenedores en el host, pueden ejecutar kernels con diferentes versiones y configuraciones (con versiones compatibles). Por ejemplo, todos los contenedores de Windows en Windows 10 usan el aislamiento de Hyper-V para usar la configuración y la versión del kernel de Windows Server.

Ejecutar un contenedor en Windows con o sin el aislamiento de Hyper-V es una decisión en tiempo de ejecución. Puede optar por crear el contenedor con el aislamiento de Hyper-V inicialmente y, en tiempo de ejecución, elegir ejecutarlo como un contenedor de Windows Server.

### <a name="additional-resources"></a>Recursos adicionales

- **Documentación de contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Aspectos básicos de los contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografía: Microsoft y contenedores**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>El ecosistema de contenedores en Azure

En las secciones anteriores, se ha explicado Cuáles son las ventajas de los contenedores de Docker, así como los detalles de las imágenes de contenedor específicas para aplicaciones .NET. Toda la información genérica es fundamental para desarrollar o incluir una aplicación en contenedores.
Sin embargo, al pensar en el entorno de implementación de producción o incluso en entornos de QA y desarrollo y pruebas, Microsoft Azure proporciona una amplia variedad de opciones, un ecosistema de contenedores completo en la nube (que se muestra en el diagrama siguiente). En función de las necesidades específicas de la aplicación, debe elegir uno u otro producto de Azure.

![Diagrama del ecosistema de contenedor en Azure.](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**Ilustración 4:7.5.** El ecosistema de contenedores en Azure

Desde el ecosistema de contenedores de Azure, los siguientes productos admiten contenedores que se consideran infraestructura:

- **Azure Container Instances (ACI)**
- **Azure virtual machines** (con soporte de contenedor)
- **Azure Virtual Machine Scale sets** (con soporte de contenedor)

Desde estos tres, ACI ofrece una gran ventaja, que es el hecho de que no es necesario mantener el sistema operativo subyacente, no es necesario actualizar o revisar, etc. sin embargo, el ACI todavía se coloca en el nivel de infraestructura, como se explica mejor en las próximas secciones de este libro.

Los productos de Azure que admiten contenedores que están al mismo tiempo y que se colocan más en el nivel de PaaS (plataforma como servicio) son:

- **Azure App Service**
- **Azure Kubernetes Service (AKS y ACS)**
- **Azure Batch**

A continuación, Azure Container Registry es un registro de contenedor de alto escalable hospedado en Azure que puede usar desde todos los productos anteriores al registrar e implementar imágenes de contenedor personalizadas.

Además, desde los contenedores, puede consumir otros servicios administrados en Azure como Azure SQL Database, Azure Redis cache, Azure Cosmos DB, etc. Además, hay soluciones y plataformas de terceros disponibles en Azure Marketplace, como Cloud Foundry y OpenShift, donde también puede usar contenedores en Azure.

En las secciones siguientes, puede explorar las recomendaciones de Microsoft sobre Cuándo usar cada uno de estos productos y soluciones de Azure de forma específica al dirigirse a contenedores de Windows.

>[!div class="step-by-step"]
>[Anterior](what-about-cloud-native-applications.md)
>[Siguiente](when-not-to-deploy-to-windows-containers.md)
