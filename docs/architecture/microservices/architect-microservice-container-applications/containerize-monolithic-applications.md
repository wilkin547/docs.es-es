---
title: Incluir en un contenedor aplicaciones monolíticas
description: Incluir en un contenedor aplicaciones monolíticas, aunque no obtenga todos los beneficios de la arquitectura de microservicios, tiene ventajas importantes de implementación que se pueden entregar inmediatamente.
ms.date: 01/30/2020
ms.openlocfilehash: 0e6f7504a91d2b1a89193471746168fc34f50956
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503281"
---
# <a name="containerizing-monolithic-applications"></a>Incluir en un contenedor aplicaciones monolíticas

Puede compilar una aplicación o un servicio web único, implementado de forma monolítica, e implementarlo como un contenedor. La propia aplicación podría no ser internamente monolítica, sino estructurada en forma de varias bibliotecas, componentes o incluso capas (nivel de aplicación, capa de dominio, capa de acceso a datos, etc.). Pero, externamente, es un contenedor único, un proceso único, una aplicación web única o un servicio único.

Para administrar este modelo, debe implementar un único contenedor para representar la aplicación. Para aumentar la capacidad, deberá escalar horizontalmente, es decir, solo tiene que agregar más copias con un equilibrador de carga delante. La simplicidad proviene de administrar una única implementación en un solo contenedor o máquina virtual.

![Diagrama que muestra los componentes de una aplicación en contenedor monolítica.](./media/containerize-monolithic-applications/monolithic-containerized-application.png)

**Figura 4-1**. Ejemplo de la arquitectura de una aplicación monolítica en contenedores

Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 4-1. Una aplicación en contenedor monolítica tiene la mayor parte de su funcionalidad en un solo contenedor, con capas internas o bibliotecas, y escala horizontalmente mediante la clonación del contenedor en varios servidores o máquinas virtuales. Con todo, este patrón monolítico puede entrar en conflicto con el principio de contenedor "un contenedor realiza una acción y lo hace en un proceso", pero podría ser correcto en algunos casos.

El inconveniente de este enfoque se vuelve evidente si la aplicación aumenta y debe escalarse. Si puede escalar toda la aplicación, no es realmente un problema. Sin embargo, en la mayoría de los casos, solo unos pocos elementos de la aplicación son los puntos de obstrucción que deben escalarse, mientras que otros componentes se usan menos.

Por ejemplo, en una aplicación típica de comercio electrónico, es probable que deba escalar el subsistema de información del producto, dado que muchos más clientes examinan los productos en lugar de comprarlos. Más clientes usan la cesta en lugar de usar la canalización de pago. Menos clientes publican comentarios o consultan su historial de compras. Y es posible que solo un grupo reducido de empleados deba administrar el contenido y las campañas de marketing. Si escala el diseño monolítico, todo el código para estas distintas tareas se implementa varias veces y se escala al mismo nivel.

Hay varias formas de escalar una aplicación: duplicación horizontal, división de diferentes áreas de la aplicación y partición de conceptos o datos empresariales similares. Pero, además del problema de escalar todos los componentes, para introducir cambios en un único componente se debe volver a probar por completo toda la aplicación e implementar por completo todas las instancias.

Sin embargo, el enfoque monolítico es común, porque el desarrollo de la aplicación es inicialmente más fácil que en el caso de los enfoques de microservicios. Por tanto, muchas organizaciones desarrollan con este enfoque arquitectónico. Mientras que algunas organizaciones han tenido resultados suficientemente buenos, otras solo llegan a los límites. Muchas organizaciones diseñaron sus aplicaciones mediante este modelo ya que, años atrás, crear arquitecturas orientadas a servicios (SOA) con infraestructura y herramientas resultaba demasiado difícil y no vieron la necesidad hasta que la aplicación creció.

Desde una perspectiva de la infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tener una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.

![Diagrama que muestra un host que ejecuta muchas aplicaciones en contenedores.](./media/containerize-monolithic-applications/host-multiple-apps-containers.png)

**Figura 4-2**. Enfoque monolítico: el host ejecuta varias aplicaciones, cada aplicación se ejecuta como un contenedor

Las aplicaciones monolíticas en Microsoft Azure se pueden implementar con máquinas virtuales dedicadas para cada instancia. Además, con los [conjuntos de escalado de máquinas virtuales de Azure](https://azure.microsoft.com/documentation/services/virtual-machine-scale-sets/), las máquinas virtuales se pueden escalar fácilmente. [Azure App Service](https://azure.microsoft.com/services/app-service/) también puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales. Además, desde 2016, Azure App Services puede ejecutar instancias únicas de contenedores de Docker, lo que simplifica la implementación.

Como un entorno de control de calidad o un entorno de producción limitado, puede implementar varias máquinas virtuales de host de Docker y equilibrarlas con el equilibrador de Azure, tal como se muestra en la figura 4-3. Esto le permite administrar el escalado con un enfoque más general, porque toda la aplicación reside dentro de un único contenedor.

![Diagrama que muestra varios hosts que ejecutan los contenedores de aplicaciones monolíticas.](./media/containerize-monolithic-applications/docker-infrastructure-monolithic-application.png)

**Figura 4-3**. Ejemplo de varios hosts que escalan verticalmente una sola aplicación de contenedor

La implementación en los distintos hosts puede administrarse con técnicas de implementación tradicionales. Los hosts de Docker pueden administrarse con comandos como `docker run` o `docker-compose` ejecutados manualmente o a través de automatización como las canalizaciones de entrega continua (CD).

## <a name="deploying-a-monolithic-application-as-a-container"></a>Implementar una aplicación monolítica como un contenedor

Usar contenedores para administrar las implementaciones de aplicaciones monolíticas tiene una serie de ventajas. Escalar las instancias de contenedor es mucho más rápido y fácil que implementar máquinas virtuales adicionales. Incluso si usa conjuntos de escalado de máquinas virtuales, las máquinas virtuales tardan tiempo en iniciarse. Cuando se implementa como instancias de aplicaciones tradicionales en lugar de contenedores, la configuración de la aplicación se administra como parte de la máquina virtual, lo que no es ideal.

Implementar las actualizaciones como imágenes de Docker es mucho más rápido y eficaz en la red. Normalmente, las imágenes de Docker se inician en segundos, lo que acelera los lanzamientos. Anular una instancia de la imagen de Docker es tan fácil como emitir un comando `docker stop` y, normalmente, se completa en menos de un segundo.

Dado que los contenedores son inmutables por diseño, nunca debe preocuparse por máquinas virtuales dañadas. En cambio, los scripts de actualización para una máquina virtual podrían olvidar tener en cuenta algún archivo o configuración concreto que se haya quedado en el disco.

Si bien las aplicaciones monolíticas pueden beneficiarse de Docker, estamos examinando estos beneficios muy por encima. Las ventajas adicionales de administrar contenedores proceden de implementar con orquestadores de contenedor, que administran las distintas instancias y el ciclo de vida de cada instancia del contenedor. Separar la aplicación monolítica en subsistemas que se pueden escalar, desarrollar e implementar de forma individual es el punto de entrada al reino de los microservicios.

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>Publicar una aplicación basada en un solo contenedor en Azure App Service

Tanto si quiere obtener la validación de un contenedor implementado en Azure o cuando una aplicación es simplemente una aplicación de un solo contenedor, Azure App Service proporciona una excelente manera de proporcionar servicios escalables basados en un solo contenedor. Usar Azure App Service es sencillo. Proporciona una integración excelente con Git para que resulte sencillo tomar el código, crearlo en Visual Studio e implementarlo directamente en Azure.

![Captura de pantalla del cuadro de diálogo Crear servicio de aplicaciones que muestra una instancia de Container Registry.](./media/containerize-monolithic-applications/publish-azure-app-service-container.png)

**Figura 4-4**. Publicación de una aplicación de contenedor único en Azure App Service desde Visual Studio 2019

Sin Docker, si necesitaba otras capacidades, marcos o dependencias que no fueran compatibles con Azure App Service, tenía que esperar a que el equipo de Azure actualizara esas dependencias en App Service. O tenía que cambiar a otros servicios como Azure Cloud Services o máquinas virtuales, en que tenía más control y podía instalar un componente o un marco necesario para la aplicación.

La compatibilidad con contenedores de Visual Studio 2017 y posteriores le ofrece la capacidad de incluir todo lo que quiera en el entorno de aplicación, tal como se muestra en la figura 4-4. Puesto que la está ejecutando en un contenedor, si agrega una dependencia a la aplicación, puede incluir la dependencia en Dockerfile o la imagen de Docker.

Como también se muestra en la figura 4-4, el flujo de publicación inserta una imagen a través de un registro de contenedor. Puede ser Azure Container Registry (un registro cercano a las implementaciones en Azure y protegido por las cuentas y los grupos de Azure Active Directory) o cualquier otro registro de Docker, como Docker Hub o un registro local.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](docker-application-state-data.md)
