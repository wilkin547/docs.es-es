---
title: Implementar aplicaciones de .NET existentes como contenedores de Windows
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Implementar aplicaciones de .NET existentes como contenedores de Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 829f33aba14d79d7d9003d1ac7472a19060d401a
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Implementar aplicaciones de .NET existentes como contenedores de Windows

Las implementaciones que se basan en los contenedores de Windows son aplicables a aplicaciones optimizada para la nube y aplicaciones de nube nativo.

Sin embargo, en esta guía y especialmente en las siguientes secciones, se centra principalmente en con contenedores de Windows para *optimizada para la nube* aplicaciones donde no es necesario cambie la arquitectura de la aplicación.

## <a name="what-are-containers-linux-or-windows"></a>¿Cuáles son los contenedores? (Linux o Windows)

Los contenedores son una manera para envolver una aplicación en su propio paquete aislado. En su contenedor, la aplicación no se ve afectada por las aplicaciones o procesos que existen fuera del contenedor. Todo lo que la aplicación depende para ejecutar correctamente como un proceso que se encuentra en el contenedor. Donde puede mover el contenedor, los requisitos de la aplicación siempre se respetan, en términos de dependencias directas, porque se incluye todo lo que necesita para ejecutar (dependencias de biblioteca, tiempos de ejecución y así sucesivamente).

La característica principal de un contenedor es que realice el entorno de la misma a través de las distintas implementaciones porque el propio contenedor incluye todas las dependencias que necesita. Puede depurar la aplicación en su equipo y, a continuación, implementarlo en otro equipo, con el mismo entorno garantizado.

Un contenedor es una instancia de una imagen de contenedor. Una imagen de contenedor es una manera de empaquetar una aplicación o servicio (por ejemplo, una instantánea) y, a continuación, implementarlo de forma confiable y reproducible. Podría decir que Docker no es que solo una tecnología-it también una filosofía y un proceso.

Contenedores diariamente se vuelven más comunes, se están convirtiendo en un sector "unidad de implementación".

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>Ventajas de contenedores (motor de Docker en Linux o Windows)

Creación de aplicaciones mediante el uso de contenedores, que también puede ser definido como ofertas de bloques de creación ligeros un aumento significativo en agilidad para generar, envío y ejecutar cualquier aplicación, a través de cualquier infraestructura.

Con los contenedores, puede tomar cualquier aplicación de desarrollo a producción con pocos o ningún cambio de código, gracias a la integración de Docker a través de la nube, sistemas operativos y herramientas de programadores de Microsoft.

Cuando se implementa en máquinas virtuales sin formato, probablemente ya tiene un método en su lugar para la implementación de aplicaciones ASP.NET en las máquinas virtuales. Sin embargo, es probable, que el método implica varios pasos manuales o complejos procesos automatizados mediante una herramienta de implementación como Puppet o una herramienta similar. Debe realizar tareas, como modificar los elementos de configuración, copiar el contenido de la aplicación entre los servidores y ejecutar programas de instalación interactiva basados en las configuraciones de MSI, seguidos de pruebas. Todos los pasos de la implementación agregan tiempo y los riesgos a implementaciones. Se producen errores cada vez que una dependencia no está presente en el entorno de destino.

En los contenedores de Windows, el proceso de empaquetado de aplicaciones está totalmente automatizado. Contenedores de Windows se basa en la plataforma Docker, que ofrece actualizaciones automáticas y reversiones para las implementaciones de contenedor. La principal mejora que obtendrá de usar el motor de Docker es crear imágenes, que son similares a las instantáneas de la aplicación, con todas sus dependencias. Las imágenes son imágenes de Docker (en este caso, una imagen de contenedor Windows). Las imágenes que se ejecutan las aplicaciones ASP.NET en ellos, sin tener que volver al código fuente. La instantánea de contenedor se convierte en la unidad de implementación.

Muchas organizaciones containerizing aplicaciones monolíticas existentes por los motivos siguientes:

-   **Agilidad a través de implementación mejoradas de la versión**. Los contenedores ofrecen un contrato de implementación coherente entre el desarrollo y las operaciones. Al usar contenedores, no digan a los desarrolladores, "Funciona en mi equipo, ¿por qué no en producción?" Puede decir, "Se ejecuta como un contenedor, para que se ejecute en producción." La aplicación empaquetada, con todas sus dependencias, se puede ejecutar en cualquier entorno compatible con contenedor. Se ejecutará la manera en que se ha diseñado para ejecutarse en todos los destinos de implementación (desarrollo, control de calidad, almacenamiento provisional, producción). Contenedores eliminan frictions mayoría cuando pasan de una fase a la siguiente, lo que mejora considerablemente la implementación, y puede distribuir con mayor rapidez.

-   **Una reducción de costes**. Contenedores de reducir los costes, ya sea mediante la consolidación y la eliminación del hardware existente, o mediante la ejecución de aplicaciones en una mayor densidad por unidad de hardware.

-   **Portabilidad**. Los contenedores son portátil y modular. Contenedores de docker se admiten en cualquier sistema operativo server (Linux y Windows), en cualquier nube pública principal (Microsoft Azure, AWS de Amazon, Google, IBM) y en el local y privada y entornos de nube híbrida.

-   **Control**. Los contenedores ofrecen un entorno flexible y seguro que se controla en el nivel de contenedor. Un contenedor se puede proteger, aislado e incluso limitado por la configuración de directivas de restricción de ejecución en el contenedor. Como se detalla en la sección acerca de los contenedores de Windows, los contenedores de Hyper-V y Windows Server 2016 ofrecen opciones de soporte técnico de enterprise adicionales.

Mejoras significativas en la agilidad y portabilidad, control en última instancia produzcan significativas reducciones de costos al usar contenedores para desarrollar y mantener aplicaciones.

## <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) que automatiza la implementación de aplicaciones como portátiles, autosuficientes contenedores que se pueden ejecutar en la nube o local. Docker es también una [empresa](https://www.docker.com/) que promueve esta tecnología y la hace evolucionar. La empresa funciona en colaboración con la nube, Linux y los proveedores de Windows, incluidos los de Microsoft.

![](./media/image6.png)

> **Figura 4-6.** Docker implementa contenedores en todas las capas de la nube híbrida

A otra persona pueden aparecer familiarizado con máquinas virtuales, los contenedores son muy similares. Un contenedor ejecuta un sistema operativo, tiene un sistema de archivos y puede tener acceso a través de una red, al igual que un sistema de equipo físico o virtual. Sin embargo, la tecnología y los conceptos relacionados con los contenedores son muy diferentes de las máquinas virtuales. Desde un punto de vista del desarrollador, un contenedor debe tratarse más parecida a un único proceso. De hecho, un contenedor tiene un único punto de entrada para un proceso.

Contenedores de docker (por motivos de simplicidad, *contenedores*) puede ejecutar de forma nativa en Windows y Linux. Cuando se ejecuta contenedores normales, los contenedores de Windows sólo pueden ejecutarse en hosts de Windows (un servidor de host o una máquina virtual) y contenedores de Linux sólo pueden ejecutarse en hosts de Linux. Sin embargo, en las versiones recientes de los contenedores de Hyper-V y Windows Server, un contenedor Linux también puede ejecuten de forma nativa en Windows Server mediante la tecnología de aislamiento de Hyper-V que actualmente solo está disponible en contenedores de Windows Server.

En un futuro próximo, entornos mixtos que tienen contenedores Linux y Windows será posible e incluso comunes.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>Ventajas de los contenedores de Windows para las aplicaciones de .NET existentes

Las ventajas de utilizar los contenedores de Windows son fundamentalmente las mismas ventajas que obtendrá de contenedores en general. Uso de contenedores de Windows es acerca de cómo mejorar en gran medida la agilidad, portabilidad y el control.

Las aplicaciones .NET existentes hacen referencia a las aplicaciones que se crearon con .NET Framework. Por ejemplo, podrían ser las aplicaciones web ASP.NET tradicionales-no usan .NET Core, que es más reciente y ejecuta multiplataforma en Linux, Windows y Mac OS.

La principal dependencia en .NET Framework es Windows. También tiene dependencias secundarias, como IIS y System.Web en ASP.NET tradicional.

Una aplicación de .NET Framework debe ejecutar en Windows, período. Si desea que incluya las aplicaciones existentes de .NET Framework y no se puede o no desea invertir en una migración a .NET Core ("si funciona correctamente, no migrarlo"), la única opción que tiene para contenedores consiste en utilizar los contenedores de Windows.

Por lo tanto, una de las ventajas principales de los contenedores de Windows es que le ofrecen una manera para modernizar las aplicaciones existentes de .NET Framework que se ejecutan en Windows a través de la contenedorización. En última instancia, los contenedores de Windows obtiene los beneficios que desea obtener mediante el uso de contenedores agilidad y portabilidad, un mejor control.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>Elija un sistema operativo de destino para. Contenedores basados en red

Teniendo en cuenta la diversidad de sistemas operativos que son compatibles con Docker, así como las diferencias entre .NET Framework y .NET Core, debe tener como destino un sistema operativo específico y versiones específicas según el marco de trabajo que usa.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan características diferentes (por ejemplo, IIS frente a un servidor web hospedado por sí mismo como Kestrel) que podrían ser necesarios en las aplicaciones de .NET Framework o .NET Core.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

Figura 4-7 muestra las versiones de sistema operativo que puede tener como destino, dependiendo de la versión de la aplicación de .NET Framework.

![](./media/image7.png)

> **Figura 4-7.** Sistemas operativos se basa en la versión de .NET Framework de destino

En escenarios de migración para las aplicaciones existentes o heredadas que se basan en las aplicaciones de .NET Framework, las dependencias principales están en Windows e IIS. La única opción es usar imágenes de Docker basadas en .NET Framework y Windows Server Core.

Cuando se agrega el nombre de imagen en el archivo Dockerfile, puede seleccionar el sistema operativo y la versión mediante el uso de una etiqueta, como en los ejemplos siguientes para las imágenes de contenedor de Windows basadas en .NET Framework:

> | **Etiqueta** | **Sistema y la versión** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x en Windows Server Core |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4.x con personalización adicional de ASP.NET, en Windows Server Core |

Para .NET Core (multiplataforma para Linux y Windows), las etiquetas sería similar al siguiente:

> | **Etiqueta** | **Sistema y la versión**
> |---|---|
> | **Microsoft/dotnet:2.0.0-Runtime** | .NET core 2.0 solo en tiempo de ejecución en Linux |
> | **Microsoft/dotnet:2.0.0-Runtime-nanoserver** | .NET core 2.0 solo en tiempo de ejecución en Windows Nano Server |

### <a name="multi-arch-images"></a>Arch varias imágenes

A partir de mediados de 2017, también puede usar una nueva característica en Docker denominado [arch múltiples](https://github.com/moby/moby/issues/15866) imágenes. Imágenes de Docker de núcleo de .NET pueden usar varios arch etiquetas. El Dockerfile los archivos ya no es necesario definir el sistema operativo que tiene como destino. La característica varias arch permite una única etiqueta que se usará en varias configuraciones de máquina. Por ejemplo, con la arquitectura, puede usar una etiqueta común: **microsoft/dotnet:2.0.0-runtime**. Si pull esa etiqueta desde un entorno de contenedor de Linux, obtendrá la imagen de Debian. Si pull esa etiqueta desde un entorno de contenedor de Windows, se obtiene la imagen de Nano Server.

Para las imágenes de .NET Framework, porque la tradicional de .NET Framework admite sólo Windows, no puede usar la característica de múltiples arch.

## <a name="windows-container-types"></a>Tipos de contenedor de Windows

Como contenedores de Linux, contenedores de Windows Server se administran mediante el motor de Docker. A diferencia de los contenedores de Linux, contenedores de Windows incluyen dos tipos diferentes de contenedores o ejecutan contenedores de veces que Windows Server y el aislamiento de Hyper-V.

**Contenedores de Windows Server**: permite aislar la aplicación a través de la tecnología de aislamiento de proceso y espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y todos los contenedores que se ejecutan en el host. Estos contenedores no proporcionan un límite de seguridad hostil y no deben usarse para aislar el código de confianza. Debido al espacio de kernel compartido, estos contenedores requieren la misma versión de kernel y la configuración.

**Aislamiento de Hyper-V**: expande el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host del contenedor no se comparte con otros contenedores en el mismo host. Estos contenedores están diseñados para hospedar varios inquilinos hostil, con las mismas garantías de seguridad de una máquina virtual. Dado que estos contenedores no comparten el kernel con el host u otros contenedores en el host, se pueden ejecutar kernels con distintas versiones y las configuraciones (con las versiones compatibles). Por ejemplo, todos los contenedores de Windows en Windows 10 use el aislamiento de Hyper-V para usar la versión del kernel de Windows Server y la configuración.

La ejecución de un contenedor en Windows con o sin aislamiento de Hyper-V es una decisión de tiempo de ejecución. Puede optar por crear inicialmente el contenedor con el aislamiento de Hyper-V y en tiempo de ejecución, elija Ejecutar como un contenedor de Windows Server.

### <a name="additional-resources"></a>Recursos adicionales

-   **Documentación de contenedores de Windows**

    [https://docs.microsoft.com/virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Conceptos básicos de contenedores de Windows**

    [https://docs.microsoft.com/virtualization/windowscontainers/about/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **Infografía: Microsoft y los contenedores**

    [https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)


## <a name="the-container-ecosystem-in-azure"></a>El ecosistema de contenedores en Azure

En las secciones anteriores, se ha explicado ¿cuáles son las ventajas de los contenedores de Docker, así como obtener información detallada sobre las imágenes de contenedor específico para aplicaciones. NET. Información genérica todo lo que es fundamental para desarrollar o incluya una aplicación.
Sin embargo, al pensar en el entorno de implementación de producción o incluso en entornos QA y desarrollo/pruebas, Microsoft Azure proporciona una abierta y una amplia variedad de opciones, un ecosistema de contenedor completa en la nube (que se muestra en el diagrama siguiente). Según las necesidades de su aplicación en concreto, debe elegir uno u otro producto de Azure.

![](./media/image7.5.png)

> **Figura 4-7.5.** El ecosistema de contenedores en Azure

En el ecosistema de contenedores en Azure, los siguientes productos admiten contenedores que se consideran infraestructura:
-   **Instancias de contenedor de Azure (ACI)**
-   **Máquinas virtuales de Azure** (compatible con el del contenedor)
-   **Conjuntos de escalas de máquina Virtual de Azure** (compatible con el del contenedor)

Entre esos tres ACI proporciona una gran ventaja, que es el hecho de que no es necesario mantener el sistema operativo subyacente, no necesita actualización/revisión, etc. pero ACI todavía se coloca en el nivel de infraestructura, como se explica mejor en las próximas secciones de este libro.

Los productos en Azure contenedores auxiliares que están en el mismo tiempo que coloca más en la PaaS (plataforma como servicio) niveles son:

-   **Azure App Service**
-   **Servicio de Kubernetes de Azure (AKS y ACS)**
-   **Azure Service Fabric.** 
-   **Lote de Azure** 

A continuación, registro de contenedor de Azure es un registro de alta contenedor escalable hospedado en Azure que puede usar en todos los productos anteriores al registrar e implementar las imágenes de contenedor personalizadas.

Además, de los contenedores, puede consumir otros servicios administrados en Azure como Azure SQL Database, caché en Redis de Azure, base de datos de Azure Cosmos etcetera. Además, hay soluciones y plataformas de terceros en Azure Marketplace como Foundry en la nube y OpenShift donde también se puede utilizar contenedores dentro de Azure. 

En las secciones siguientes, puede explorar las recomendaciones de Microsoft sobre cuándo usar cada una de esas soluciones y productos de Azure, en concreto cuando el destino de los contenedores de Windows.


>[!div class="step-by-step"]
[Anterior](what-about-cloud-native-applications.md)
[Siguiente](when-not-to-deploy-to-windows-containers.md)
