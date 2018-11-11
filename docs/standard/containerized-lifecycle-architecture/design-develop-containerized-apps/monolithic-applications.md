---
title: Aplicaciones monolíticas
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: a2fe2c325377ec49f89199ad2e36c950ebab6a24
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50757353"
---
# <a name="monolithic-applications"></a>Aplicaciones monolíticas

En este escenario, se crear una aplicación web único y monolítico o un servicio e implementarla como un contenedor. Dentro de la aplicación, la estructura no puede ser monolítica; puede constar de varias bibliotecas, componentes o incluso capas (nivel de aplicación, capa de dominio, capa de acceso a datos, etcetera). Externamente, es un contenedor único, como un único proceso, aplicación web única o servicio único.

Para administrar este modelo, debe implementar un único contenedor para representar la aplicación. Para ajustar la escala, solo tiene que agregar unas cuantas más copias con un equilibrador de carga delante. La simplicidad proviene de administrar una única implementación de un único contenedor o la máquina virtual (VM).

Después de la entidad de seguridad que realiza una acción solo un contenedor y lo hace en un proceso, el patrón monolítico está en conflicto. Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 4-1.

![](./media/image1.png)

Figura 4-1: un ejemplo de arquitectura de aplicaciones monolíticas

La desventaja de este enfoque aparece si o cuando la aplicación aumenta y debe escalarse. Si se escala toda la aplicación, realmente no es un problema. Sin embargo, en la mayoría de los casos, algunas partes de la aplicación son los puntos de obstrucción que requieren el ajuste de escala, mientras que otros componentes se usan menos.

En el ejemplo típico de comercio electrónico, lo que probablemente necesite es escalar el componente de información de producto. Hay muchos más clientes que buscan productos de los que los compran. Más clientes usan la cesta en lugar de usar la canalización de pago. Menos clientes publican comentarios o consultan su historial de compras. Y es probable que tenga solo un grupo reducido de empleados, en una sola región, lo que necesita para administrar el contenido y campañas de marketing. Al escalar el diseño monolítico, todo el código se implementa varias veces.

Además el "escalado-todo" problema, los cambios en un único componente requieren volver a probar completa de toda la aplicación, así como una reimplementación completa de todas las instancias.

El enfoque monolítico es habitual y muchas organizaciones son desarrollar con este método de arquitectura. Muchos bien disfrutan suficientes resultados, mientras que otros límites de encontrar. Muchas diseñaron sus aplicaciones en este modelo, ya que la infraestructura y herramientas resultaba demasiado difíciles de SOA de compilación, y no vieron la necesidad, hasta que la aplicación creció.

Desde una perspectiva de infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tener una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.

![](./media/image2.png)

Figura 4-2: un host que ejecuta varias aplicaciones o contenedores

Puede implementar las aplicaciones monolíticas en Azure mediante el uso de máquinas virtuales dedicadas para cada instancia. Uso de [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), puede escalar fácilmente las máquinas virtuales. [Azure App Services](https://azure.microsoft.com/services/app-service/) puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales. Desde 2016, Azure App Services puede ejecutar instancias únicas de contenedores de Docker, así, lo que simplifica la implementación. Y uso de Docker, puede implementar una sola máquina virtual como un host de Docker y ejecutar varias instancias. Con el equilibrador de Azure, como se muestra en la figura 4-3, puede administrar el escalado.

![](./media/image3.png)

Figura 4-3: varios hosts escalar horizontalmente una sola aplicación aplicaciones/contenedores de Docker

Puede administrar la implementación en los distintos hosts a través de técnicas de implementación tradicionales. Puede administrar los hosts de Docker mediante el uso de comandos como `docker run` manualmente, mediante la automatización, como las canalizaciones de entrega continua (CD), que se explican más adelante en este libro electrónico.

## <a name="monolithic-application-deployed-as-a-container"></a>Una aplicación monolítica implementada como un contenedor

Hay ventajas derivadas del uso de contenedores para administrar implementaciones monolíticas. Escalar las instancias de los contenedores es mucho más rápido y fácil que implementar máquinas virtuales adicionales. Aunque VM Scale Sets son una excelente característica para escalar máquinas virtuales, que son necesarios para hospedar los contenedores de Docker, tardan tiempo en configurar. Cuando se implementa como instancias de aplicación, la configuración de la aplicación se administra como parte de la máquina virtual.

Implementar las actualizaciones como imágenes de Docker es mucho más rápido y eficaz en la red. Las instancias de Vn pueden configurarse en los mismos hosts que las instancias de Vn-1, lo que elimina los costos adicionales de máquinas virtuales adicionales. Las imágenes de docker normalmente se inician en segundos, lo que acelera las implementaciones. Anular una instancia de Docker es tan sencillo como invocar el `docker stop` comando, normalmente se completa en menos de un segundo.

Dado que los contenedores son intrínsecamente inmutables, por diseño, nunca debe preocuparse por máquinas virtuales dañadas porque olvidó un script de actualización para tener en cuenta alguna configuración concreta o archivo restante en el disco.

Aunque las aplicaciones monolíticas pueden beneficiarse de Docker, tocamos en sólo las sugerencias de las ventajas. Las mayores ventajas de administrar contenedores proceden de implementar con orquestadores de contenedores que administran las distintas instancias y ciclo de vida de cada instancia del contenedor. Separar la aplicación monolítica en subsistemas que se pueden escalar, desarrollar e implementar de forma individual es el punto de entrada al reino de los microservicios.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>Publicación de una sola aplicación de contenedor de Docker en Azure App Service

Ya sea porque desea obtener una validación rápida de un contenedor implementado en Azure o porque la aplicación es simplemente una aplicación de contenedor único, Azure App Services proporciona una excelente manera de proporcionar servicios escalables destinados a contenedor único.

Con Azure App Service es intuitivo y puede ponerse en y ejecute rápidamente porque proporciona excelente Git integración para que el código, compilarlo en Microsoft Visual Studio e implementarlo directamente en Azure. Pero, tradicionalmente (con ningún Docker), si necesitaba otras capacidades, marcos o dependencias que no son compatibles con servicios de aplicaciones, es necesario que esperar hasta que el equipo de Azure actualiza esas dependencias en App Service o cambiar a otros servicios como Service Fabric, servicios en la nube o máquinas virtuales incluso simples, que tiene más control y puede instalar un componente necesario o un marco para la aplicación.

Ahora, sin embargo, (que se anunció en Microsoft Connect 2016 en noviembre de 2016) y como se muestra en figura 4‑4, cuando se usa Visual Studio 2017, compatibilidad con contenedores en Azure App Service le ofrece la posibilidad de incluir lo que desea en su entorno de aplicación. Si agrega una dependencia a la aplicación, porque se está ejecutando en un contenedor, obtenga la capacidad de incluir esas dependencias en la imagen de Docker o Dockerfile.

![](./media/image4.png)

Figura 4-4: publicación de un contenedor en Azure App Service desde aplicaciones o contenedores de Visual Studio

Figura 4-4 también muestra que el flujo de publicación inserta una imagen a través de un registro de contenedor, que puede ser Azure Container Registry (un registro de cerca a las implementaciones en Azure y protege las cuentas y grupos de Azure Active Directory) o cualquier otro registro de Docker al igual que los registros de Docker Hub o en el entorno local.


>[!div class="step-by-step"]
[Anterior](common-container-design-principles.md)
[Siguiente](state-and-data-in-docker-applications.md)
