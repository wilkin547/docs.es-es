---
title: Implementación de aplicaciones .NET existentes como contenedores de Windows
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Implementación de aplicaciones .NET existentes como contenedores de Windows
ms.date: 12/21/2020
ms.openlocfilehash: f3f164ca0578d5358f2c5365fd5a1d2e8e22d8c5
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025361"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Implementación de aplicaciones .NET existentes como contenedores de Windows

Las implementaciones basadas en contenedores de Windows se aplican a aplicaciones optimizadas para la nube y aplicaciones nativas en la nube.

Sin embargo, en esta guía y especialmente en las secciones siguientes, se centra principalmente en el uso de contenedores de Windows para aplicaciones *optimizadas para la nube* en las que no es necesario rediseñar la aplicación.

## <a name="what-are-containers-linux-or-windows"></a>¿Qué son los contenedores? (Linux o Windows)

Los contenedores son una manera de encapsular una aplicación en su propio paquete aislado. En su contenedor, la aplicación no se ve afectada por las aplicaciones o procesos que existen fuera del contenedor. Todo de lo que depende la aplicación para que se ejecute correctamente, ya que un proceso está dentro del contenedor. Siempre que el contenedor pueda moverse, se cumplirán los requisitos de la aplicación, en términos de dependencias directas, porque se incluye todo lo que necesita para ejecutarse (dependencias de biblioteca, tiempos de ejecución, etc.).

La característica principal de un contenedor es que hace que el entorno sea el mismo en las distintas implementaciones porque el propio contenedor incluye todas las dependencias que necesita. Puede depurar la aplicación en la máquina y, a continuación, implementarla en otra máquina con el mismo entorno garantizado.

Un contenedor es una instancia de una imagen de contenedor. Una imagen de contenedor es una manera de empaquetar una aplicación o un servicio (como una instantánea) y, después, implementarla de forma confiable y reproducible. Podría decirse que Docker no solo es una tecnología, sino también una filosofía y un proceso.

A medida que los contenedores son cada vez más comunes, se están convirtiendo en una "unidad de implementación" en todo el sector.

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Ventajas de los contenedores (motor de Docker en Linux o Windows)

La creación de aplicaciones mediante contenedores, que también podrían definirse como bloques de creación ligeros, ofrece un aumento significativo en la agilidad para crear, enviar y ejecutar cualquier aplicación, en cualquier infraestructura.

Con los contenedores, puede llevar cualquier aplicación del desarrollo a la producción con pocos cambios en el código, e incluso ninguno, gracias a la integración de Docker entre las herramientas de desarrollo de Microsoft, los sistemas operativos y la nube.

Cuando se implementa en máquinas virtuales convencionales, es probable que ya tenga un método para implementar aplicaciones de ASP.NET en las máquinas virtuales. Sin embargo, es probable que el método implique varios pasos manuales o complejos procesos automatizados mediante una herramienta de implementación como Puppet o una herramienta similar. Es posible que necesite realizar tareas como la modificación de elementos de configuración, la copia de contenido de la aplicación entre servidores y la ejecución de programas de instalación interactiva basados en configuraciones .msi, seguidos de pruebas. Todos estos pasos de la implementación agregan tiempo y riesgo a las implementaciones. Obtendrá errores cada vez que una dependencia no esté presente en el entorno de destino.

En los contenedores de Windows, el proceso de empaquetado de aplicaciones está totalmente automatizado. Los contenedores de Windows se basan en la plataforma Docker, que ofrece actualizaciones automáticas y reversiones para implementaciones de contenedores. La mejora principal que obtiene al usar el motor de Docker es que crea imágenes, que son como las instantáneas de la aplicación, con todas sus dependencias. Las imágenes son imágenes de Docker (una imagen de contenedor de Windows, en este caso). Las imágenes ejecutan aplicaciones de ASP.NET en contenedores, sin volver al código fuente. La instantánea de contenedor se convierte en la unidad de implementación.

Muchas organizaciones incluyen en contenedores aplicaciones monolíticas existentes por las siguientes razones:

- **Agilidad de las versiones mediante una implementación mejorada**. Un contenedor ofrece un contrato de implementación coherente entre el desarrollo y las operaciones. Cuando se utilizan los contenedores, no escuchará a los desarrolladores decir "Si funciona en mi máquina, ¿por qué no en producción?" Pueden decir "que se ejecuta como un contenedor, por lo que se ejecutará en producción". La aplicación empaquetada, con todas sus dependencias, se puede ejecutar en cualquier entorno basado en un contenedor compatible. Se ejecutará de la forma en que se pretendía que se ejecutara en todos los destinos de implementación (desarrollo, control de calidad, almacenamiento provisional, producción). Los contenedores eliminan la mayoría de las fricciones cuando pasan de una fase a la siguiente, lo que mejora en gran medida la implementación, y se puede enviar más rápidamente.

- **Reducción de costos**. Los contenedores permiten reducir los costos, ya sea mediante la consolidación y eliminación de hardware existente, o por la ejecución de aplicaciones a una densidad más alta por unidad de hardware.

- **Portabilidad**. Los contenedores son modulares y portátiles. Los contenedores de Docker se admiten en cualquier sistema operativo de servidor (Linux y Windows), en cualquier nube pública principal (Microsoft Azure, Amazon AWS, Google, IBM) y en entornos de nube locales y privados o híbridos.

- **Control**. Los contenedores ofrecen un entorno flexible y seguro que se controla en el nivel de contenedor. Un contenedor se puede proteger, aislar e incluso limitar mediante el establecimiento de directivas de restricción de ejecución en el contenedor. Tal como se detalla en la sección acerca de los contenedores de Windows, los contenedores de Windows Server 2016 y Hyper-V ofrecen opciones adicionales de soporte técnico empresarial.

En última instancia, las mejoras significativas en la agilidad, la portabilidad y el control conducen a importantes reducciones de costos cuando se usan contenedores para desarrollar y mantener aplicaciones.

## <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) que automatiza la implementación de aplicaciones como contenedores portátiles y autosuficientes que se pueden ejecutar en la nube o localmente. Docker es también una [empresa](https://www.docker.com/) que promueve esta tecnología y la hace evolucionar. La empresa funciona en colaboración con la nube, Linux y los proveedores de Windows, incluido Microsoft.

![Diagrama que muestra cómo Docker implementa contenedores en la nube híbrida.](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**Figura 4-6.** Docker implementa contenedores en todas las capas de la nube híbrida

Para alguien familiarizado con las máquinas virtuales, es posible que los contenedores parezcan bastante similares. Un contenedor ejecuta un sistema operativo, tiene un sistema de archivos y se puede acceder a él a través de una red, al igual que un equipo físico o virtual. Dicho esto, la tecnología y los conceptos relacionados con los contenedores son muy diferentes de las máquinas virtuales. Desde el punto de vista del desarrollador, el contenedor debe tratarse como un único proceso. De hecho, el contenedor tiene un único punto de entrada para un proceso.

Los contenedores de Docker (por simplicidad *contenedores*) se pueden ejecutar de forma nativa en Linux y Windows. Al ejecutar contenedores normales, los contenedores de Windows solo pueden ejecutarse en hosts de Windows (un servidor host o una máquina virtual) y los contenedores de Linux solo pueden ejecutarse en hosts de Linux. Pero en las versiones recientes de los contenedores de Windows Server e Hyper-V, también se puede ejecutar un contenedor de Linux de forma nativa en Windows Server mediante la tecnología de aislamiento de Hyper-V que actualmente está disponible solo en los contenedores de Windows Server.

En un futuro próximo, serán posibles, e incluso comunes, los entornos mixtos con contenedores de Linux y Windows.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Ventajas de los contenedores de Windows para las aplicaciones .NET existentes

Las ventajas de usar contenedores de Windows son fundamentalmente las mismas ventajas que se obtienen de los contenedores en general. El uso de contenedores de Windows trata de mejorar considerablemente la agilidad, la portabilidad y el control.

Las aplicaciones .NET existentes hacen referencia a las aplicaciones que se crearon con .NET Framework. Por ejemplo, puede tratarse de aplicaciones web de ASP.NET tradicionales; no usan .NET Core o .NET 5.0, que es más reciente y se ejecuta en varias plataformas en Linux, Windows y MacOS.

La dependencia principal en .NET Framework es Windows. También tiene dependencias secundarias, como IIS y System.Web en ASP.NET tradicional.

Una aplicación .NET Framework se debe ejecutar en Windows. Si quiere incluir en contenedores las aplicaciones de .NET Framework existentes y no puede o no quiere invertir en una migración a .NET Core o versiones posteriores ("si funciona correctamente, no se migra"), la única opción que tiene para los contenedores es usar contenedores de Windows.

Por lo tanto, una de las principales ventajas de los contenedores de Windows es que ofrecen una forma de modernizar las aplicaciones .NET Framework existentes que se ejecutan en Windows a través de la inclusión en contenedores. En última instancia, los contenedores de Windows le aportan las ventajas que está buscando mediante contenedores: agilidad, portabilidad y un mejor control.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Elección de un sistema operativo de destino con contenedores basados en .NET

Teniendo en cuenta la diversidad de sistemas operativos que son compatibles con Docker, así como las diferencias entre .NET Framework y .NET Core, debe escoger un sistema operativo de destino específico y versiones específicas basadas en la plataforma que utilice.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (como IIS frente a un servidor web autohospedado, como Kestrel) que las aplicaciones de .NET Framework o .NET podrían necesitar.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

En la figura 4-7 se muestran las versiones del sistema operativo a las que puede dirigirse, en función de la versión de la aplicación de .NET Framework.

![Diagrama que muestra el sistema operativo de destino en función de la versión de .NET Framework.](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**Figura 4-7.** Sistemas operativos de destino en función de la versión de .NET Framework

En los escenarios de migración de aplicaciones existentes o heredadas basadas en aplicaciones .NET Framework, las dependencias principales se encuentran en Windows e IIS. La única opción es usar imágenes de Docker basadas en Windows Server Core y en .NET Framework.

Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión mediante el uso de una etiqueta, como en los ejemplos siguientes para las imágenes de contenedores de Windows basadas en .NET Framework:

> | **Tag** | **Sistema y versión** |
> |---|---|
> | **mcr.microsoft.com/dotnet/framework/runtime:4.x-windowsservercore-20H2** | .NET Framework 4.x en Windows Server Core |
> | **mcr.microsoft.com/dotnet/framework/aspnet:4.x-windowsservercore-20H2** | .NET Framework 4.x con personalización ASP.NET adicional, en Windows Server Core |

Para .NET (multiplataforma para Linux y Windows), las etiquetas tendrían el aspecto siguiente:

> | **Tag** | **Sistema y versión**
> |---|---|
> | **mcr.microsoft.com/dotnet/runtime:5.0** | Entorno de ejecución de .NET solo en Linux |
> | **mcr.microsoft.com/dotnet/runtime:5.0-nanoserver-20H2** | Entorno de ejecución de .NET solo en Windows Nano Server |

### <a name="multi-arch-images"></a>Imágenes multiarquitectura

A partir de mediados de 2017, también puede usar una nueva característica de Docker llamada [imágenes multiarquitectura](https://github.com/moby/moby/issues/15866). Las imágenes de Docker de .NET pueden usar etiquetas multiarquitectura. Los archivos de Dockerfile ya no necesitan definir el sistema operativo de destino. La característica de multiarquitectura permite usar una sola etiqueta en varias configuraciones de máquina. Por ejemplo, con la multiarquitectura, puede usar una etiqueta común: **mcr.microsoft.com/dotnet/runtime:5.0**. Si extrae esa etiqueta de un entorno de contenedores de Linux, obtendrá la imagen basada en Debian. Si extrae esa etiqueta de un entorno de contenedor de Windows, obtendrá la imagen basada en Nano Server.

En el caso de las imágenes de .NET Framework, ya que .NET Framework tradicional solo admite Windows, no puede usar la característica de multiarquitectura.

## <a name="windows-container-types"></a>Tipos de contenedores de Windows

Como los contenedores de Linux, los contenedores de Windows Server se administran mediante el motor de Docker. A diferencia de los contenedores de Linux, los contenedores de Windows incluyen dos tipos diferentes de contenedores o entornos de ejecución: contenedores de Windows Server y aislamiento de Hyper-V.

**Contenedores de Windows Server**: ofrecen aislamiento de aplicaciones mediante la tecnología de aislamiento de proceso y de espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y con todos los contenedores que se ejecutan en el host. Estos contenedores no proporcionan un límite de seguridad hostil y no se deben usar para aislar el código que no es de confianza. Debido al espacio compartido del kernel, estos contenedores requieren la misma versión y configuración de kernel.

**Aislamiento de Hyper-V**: amplía el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host del contenedor no se comparte con otros contenedores del mismo host. Estos contenedores están diseñados para el hospedaje de varios inquilinos hostiles, con las mismas garantías de seguridad de una máquina virtual. Dado que estos contenedores no comparten el kernel con el host u otros contenedores en el host, pueden ejecutar los kernels con diferentes versiones y configuraciones (con versiones compatibles). Por ejemplo, todos los contenedores de Windows en Windows 10 usan el aislamiento de Hyper-V para utilizar la configuración y la versión del kernel de Windows Server.

Ejecutar un contenedor en Windows con o sin el aislamiento de Hyper-V es una decisión en tiempo de ejecución. Puede optar por crear inicialmente el contenedor con el aislamiento de Hyper-V y, en tiempo de ejecución, elegir ejecutarlo como un contenedor de Windows Server.

### <a name="additional-resources"></a>Recursos adicionales

- **Documentación sobre los contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Aspectos básicos de los contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infografía: Microsoft y contenedores**

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>El ecosistema de contenedores de Azure

En las secciones anteriores, se ha explicado cuáles son las ventajas de los contenedores de Docker, así como los detalles de las imágenes de contenedor específicas para aplicaciones .NET. Toda la información genérica es fundamental para desarrollar o incluir la aplicación en contenedores.
Sin embargo, al pensar en el entorno de implementación de producción o incluso en entornos de control de calidad y desarrollo y pruebas, Microsoft Azure proporciona una amplia variedad de opciones, un ecosistema de contenedores completo en la nube (que se muestra en el diagrama siguiente). En función de las necesidades específicas de la aplicación, debe elegir uno u otro producto de Azure.

![Diagrama del ecosistema de contenedores de Azure.](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**Figura 4-7.5.** El ecosistema de contenedores de Azure

Desde el ecosistema de contenedores de Azure, los siguientes productos admiten contenedores que se consideran infraestructura:

- **Azure Container Instances (ACI)**
- **Azure Virtual Machines** (con compatibilidad de contenedor)
- **Azure Virtual Machine Scale Sets** (con compatibilidad de contenedor)

En estos tres productos, ACI ofrece una gran ventaja, que es el hecho de que no es necesario mantener el sistema operativo subyacente y no es necesario actualizar o revisar; sin embargo, ACI todavía se coloca en el nivel de infraestructura, como se explica mejor en las próximas secciones de este libro.

Los productos de Azure que admiten contenedores que están al mismo tiempo y que se colocan más en el nivel de PaaS (plataforma como servicio) son:

- **Azure App Service**
- **Azure Kubernetes Service (AKS y ACS)**
- **Azure Batch**

A continuación, Azure Container Registry es un registro de contenedor muy escalable hospedado en Azure que puede usar desde todos los productos anteriores al registrar e implementar imágenes de contenedor personalizadas.

Además, desde los contenedores, puede consumir otros servicios administrados en Azure como Azure SQL Database, Azure Redis Cache, Azure Cosmos DB, etc. Además, hay soluciones y plataformas de terceros disponibles en Azure Marketplace, como Cloud Foundry y OpenShift, donde también puede usar contenedores en Azure.

En las secciones siguientes, puede explorar las recomendaciones de Microsoft sobre cuándo usar cada uno de estos productos y soluciones de Azure de forma específica al dirigirse a contenedores de Windows.

>[!div class="step-by-step"]
>[Anterior](what-about-cloud-native-applications.md)
>[Siguiente](when-not-to-deploy-to-windows-containers.md)
