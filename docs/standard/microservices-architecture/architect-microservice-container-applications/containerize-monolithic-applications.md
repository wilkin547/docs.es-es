---
title: "Aplicaciones monolíticas containerizing"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Aplicaciones monolíticas containerizing"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 11e2c24403b9b61584e424696c844e00e5d34b03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="containerizing-monolithic-applications"></a>Aplicaciones monolíticas containerizing

Puede compilar una aplicación web único, monolithically implementado o servicio e implementarlo como un contenedor. La propia aplicación podría no ser internamente monolítica pero había estructurado como varias bibliotecas, componentes o incluso las capas (nivel de aplicación, el nivel de dominio, capa de acceso a datos, etcetera). Externamente, sin embargo, es un contenedor único, un proceso único, una sola aplicación web o un servicio único.

Para administrar este modelo, implementa un único contenedor para representar la aplicación. Para escalar verticalmente, solo tiene que agregar más copias con un equilibrador de carga en la parte frontal. La simplicidad proviene de administrar una única implementación en un único contenedor o la máquina virtual.

![](./media/image1.png)

**Figura 4-1**. Ejemplo de la arquitectura de una aplicación monolítica en contenedores

Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 4-1. Sin embargo, este patrón monolítico puede entrar en conflicto con el principio de contenedor "un contenedor realiza una acción y no en un proceso", pero podrían ser correcta para algunos de los casos.

El inconveniente de este enfoque se vuelve evidente si aumenta la aplicación, que requiere una ampliación. Si puede escalar toda la aplicación, no es realmente un problema. Sin embargo, en la mayoría de los casos, unos pocos elementos de la aplicación son los puntos de retracción que necesidad de ajuste de escala, mientras que otros componentes son utiliza menos.

Por ejemplo, en una aplicación típica de comercio electrónico, es probable que deba escalar el subsistema de información de producto, dado que muchos clientes más examinar productos de adquirirlas. Más clientes utilice su cesta de usar la canalización de pago. Los clientes menos agreguen comentarios o ver su historial de compras. Y es posible que tenga solo un conjunto de empleados, que necesita para administrar el contenido y las campañas de marketing. Si ajusta el diseño monolítico, todo el código para estas tareas se implementa varias veces y escalar en el mismo nivel.

Hay varias formas de escalar una aplicación: duplicación horizontal, división de diferentes áreas de la aplicación y partición conceptos similares de negocio o sus datos. Pero, además del problema de ajuste de escala en todos los componentes, requieren cambios en un único componente al volver a examinar completa de toda la aplicación y una implementación completa de todas las instancias.

Sin embargo, el enfoque monolítico es común, porque el desarrollo de la aplicación es inicialmente más fácil que para microservicios enfoques. Por lo tanto, muchas organizaciones desarrollan con este enfoque de arquitectura. Mientras que algunas organizaciones han tenido bueno suficientes resultados, otros están alcanzando límites. Muchas organizaciones diseñado sus aplicaciones mediante este modelo ya infraestructura y herramientas de hecho demasiado difícil compilar el servicio orientada a servicios (SOA) de arquitecturas hace años, y no verán la necesidad, hasta que la aplicación ha crecido.

Desde una perspectiva de la infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tienen una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.

![](./media/image2.png)

**Figura 4-2**. Enfoque monolítico: Host ejecuta varias aplicaciones, cada aplicación se ejecuta como un contenedor

Monolíticas aplicaciones en Microsoft Azure se pueden implementar con máquinas virtuales dedicadas para cada instancia. Además, para usar [conjuntos de escalas de VM de Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), puede escalar fácilmente las máquinas virtuales. [Servicio de aplicaciones de Azure](https://azure.microsoft.com/services/app-service/) puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales. A partir de 2016, servicios de aplicaciones de Azure puede ejecuta instancias únicas de contenedores de Docker, simplificar la implementación.

Como un entorno de preguntas y respuestas o un entorno de producción limitado, puede implementar varios host de Docker las máquinas virtuales y equilibrar con el equilibrador de Azure, tal como se muestra en la figura 4-3. Esto le permite administrar escalado con un enfoque más generales, porque toda la aplicación reside dentro de un único contenedor.

![](./media/image3.png)

**Figura 4-3**. Ejemplo de varios hosts de escalado de una aplicación de contenedor único

Implementación a los distintos hosts puede administrarse con técnicas de implementación tradicionales. Docker hosts pueden administrarse con comandos como `docker run` o `docker-compose` lleva a cabo manualmente o a través de automatización como las canalizaciones de entrega continua (CD).

## <a name="deploying-a-monolithic-application-as-a-container"></a>Implementar una aplicación monolítica como un contenedor

Hay ventajas derivadas del uso de contenedores para administrar las implementaciones de aplicaciones monolítico. Ajuste de escala en instancias de contenedor es mucho más rápido y fácil de implementar máquinas virtuales adicionales. Incluso si usa conjuntos de escalas de máquina virtual, máquinas virtuales tardan tiempo en iniciarse. Cuando se implementa como instancias de aplicación tradicional en lugar de contenedores, la configuración de la aplicación se administra como parte de la máquina virtual, lo que no es ideal.

Implementación de actualizaciones como imágenes de Docker es mucho más rápido y eficaz de la red. Las imágenes de docker inician normalmente en segundos, lo que acelera la implementación. Anular una instancia de la imagen de Docker es tan fácil como emitir un `docker stop` de comandos y normalmente se completa en menos de un segundo.

Dado que los contenedores son inmutables por diseño, nunca necesite preocuparse sobre máquinas virtuales están dañadas. En cambio, las secuencias de comandos de actualización para una máquina virtual podrían olvidar para tener en cuenta algunas configuración específica o un archivo restante en el disco.

Mientras monolíticas aplicaciones pueden beneficiarse de Docker, nos estamos tocar solo en los beneficios. Ventajas adicionales de administración de contenedores de proceden de la implementación con orchestrators de contenedor, que administración las distintas instancias y ciclo de vida de cada instancia del contenedor. Es el punto de entrada en el dominio Kerberos de microservicios interrumpir la aplicación monolítico en subsistemas que se pueden escalar, desarrollar e implementar de forma individual.

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>Publicar una aplicación sencilla basada en contenedor al servicio de aplicaciones de Azure

Si desea obtener la validación de un contenedor de implementada en Azure o cuando una aplicación es simplemente una aplicación de contenedor único, servicio de aplicaciones de Azure proporciona una excelente manera de proporcionar servicios escalables destinados a sencilla basada en contenedor. Con el servicio de aplicación de Azure es sencillo. Proporciona integración excelente con Git que resulte sencillo tomar el código, se crean en Visual Studio e impleméntelo directamente en Azure.

![](./media/image4.png)

**Figura 4-4**. Publicar una aplicación de contenedor único al servicio de aplicaciones de Azure desde Visual Studio

Sin Docker, si necesita otras funcionalidades, marcos o dependencias que no son compatibles con el servicio de aplicación de Azure, se han tenido que esperar hasta que el equipo de Azure actualiza esas dependencias en el servicio de aplicaciones. O bien, tiene que cambiar a otros servicios como Azure Service Fabric, servicios en la nube o incluso las máquinas virtuales, donde había aún más control y podría instalar un componente necesario o el marco de trabajo para la aplicación.

Compatibilidad con el contenedor de 2017 de Visual Studio ofrece la capacidad para incluir todo lo que desees en el entorno de aplicación, tal como se muestra en la figura 4-4. Puesto que se está ejecutando en un contenedor, si agrega una dependencia a la aplicación, puede incluir la dependencia en la imagen de Dockerfile o Docker.

Como también se muestra en la figura 4-4, el flujo de publicación inserta una imagen a través de un registro de contenedor. Esto puede ser el registro de contenedor de Azure (en un registro de cierre a las implementaciones en Azure y protegido por las cuentas y grupos de Active Directory de Azure), o cualquier otro registro de Docker, como Docker Hub o un registro local.


>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (docker-aplicaciones-estado-data.md)
