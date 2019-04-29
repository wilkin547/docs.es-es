---
title: Aplicaciones monolíticas
description: Comprender los conceptos básicos para incluir en un contenedor aplicaciones monolíticas.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e7454100b09f602e1e103c38685609e1dab62fe9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644986"
---
# <a name="monolithic-applications"></a>Aplicaciones monolíticas

En este escenario, está creando una aplicación web único y monolítico o servicio e implementarlo como un contenedor. Dentro de la aplicación, la estructura no puede ser monolítica; puede constar de varias bibliotecas, componentes o incluso capas (nivel de aplicación, capa de dominio, capa de acceso a datos, etcetera). Externamente, es un contenedor único, como un único proceso, aplicación web única o servicio único.

Para administrar este modelo, debe implementar un único contenedor para representar la aplicación. Para ajustar la escala, solo tiene que agregar unas cuantas más copias con un equilibrador de carga delante. La simplicidad proviene de administrar una única implementación de un único contenedor o la máquina virtual (VM).

Después de la entidad de seguridad que realiza una acción solo un contenedor y lo hace en un proceso, el patrón monolítico está en conflicto. Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 4-1.

![Una aplicación monolítica tiene todos o la mayoría de su funcionalidad en un único proceso o contenedor y está dividida en componentes en capas internas o bibliotecas.](./media/image1.png)

**Figura 4-1.** Un ejemplo de arquitectura de aplicaciones monolíticas

La desventaja de este enfoque aparece si o cuando la aplicación aumenta y debe escalarse. Si se escala toda la aplicación, realmente no es un problema. Sin embargo, en la mayoría de los casos, algunas partes de la aplicación son los puntos de obstrucción que requieren el ajuste de escala, mientras que otros componentes se usan menos.

En el ejemplo típico de comercio electrónico, lo que probablemente necesite es escalar el componente de información de producto. Hay muchos más clientes que buscan productos de los que los compran. Más clientes usan la cesta en lugar de usar la canalización de pago. Menos clientes publican comentarios o consultan su historial de compras. Y es probable que tenga solo un grupo reducido de empleados, en una sola región, lo que necesita para administrar el contenido y campañas de marketing. Al escalar el diseño monolítico, todo el código se implementa varias veces.

Además el "escalado-todo" problema, los cambios en un único componente requieren volver a probar completa de toda la aplicación, así como una reimplementación completa de todas las instancias.

El enfoque monolítico es habitual y muchas organizaciones son desarrollar con este método de arquitectura. Muchos bien disfrutan suficientes resultados, mientras que otros límites de encontrar. Muchas diseñaron sus aplicaciones en este modelo, ya que la infraestructura y herramientas resultaba demasiado difíciles de SOA de compilación, y no vieron la necesidad, hasta que la aplicación creció.

Desde una perspectiva de infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tener una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.

![Un único host puede ejecutar varias aplicaciones en contenedores diferentes.](./media/image2.png)

**Figura 4-2.** Un host que ejecuta varias aplicaciones o contenedores

Por último, desde una perspectiva de disponibilidad, las aplicaciones monolíticas deben implementarse como un todo; Esto significa que, en caso de que debe *detener e iniciar*, toda la funcionalidad y todos los usuarios se verán afectados durante el período de implementación. En determinadas situaciones, el uso de Azure y contenedores puede minimizar estas situaciones y reducir la probabilidad de que el tiempo de inactividad de la aplicación, como se aprecia en la figura 4-3.

Puede implementar las aplicaciones monolíticas en Azure mediante el uso de máquinas virtuales dedicadas para cada instancia. Uso de [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), puede escalar fácilmente las máquinas virtuales.

También puede usar [Azure App Services](https://azure.microsoft.com/services/app-service/) para ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin tener que administrar las máquinas virtuales. Azure App Services puede ejecutar instancias únicas de contenedores de Docker, así, lo que simplifica la implementación.

Puede implementar varias máquinas virtuales como hosts de Docker y ejecutar cualquier número de contenedores por máquina virtual. A continuación, mediante el uso de un equilibrador de carga de Azure, como se muestra en la figura 4-3, puede administrar el escalado.

![Una aplicación monolítica puede ampliarse de forma horizontal a hosts diferentes, donde cada uno de ellos ejecuta la aplicación en contenedores.](./media/image3.png)

**Figura 4-3**. Escalar horizontalmente una sola aplicación aplicaciones/contenedores de Docker de varios hosts

Puede administrar la implementación de los mismos hosts a través de técnicas de implementación tradicionales.

Puede administrar contenedores de Docker desde la línea de comandos mediante el uso de comandos como `docker run` y `docker-compose up`, y también puede automatizarla en las canalizaciones de entrega continua (CD) e implementar en hosts de Docker desde servicios de Azure DevOps, por ejemplo.

## <a name="monolithic-application-deployed-as-a-container"></a>Una aplicación monolítica implementada como un contenedor

Hay ventajas derivadas del uso de contenedores para administrar implementaciones monolíticas. Escalar las instancias de los contenedores es mucho más rápido y fácil que implementar máquinas virtuales adicionales.

Implementar las actualizaciones como imágenes de Docker es mucho más rápido y eficaz en la red. Normalmente los contenedores de docker se inician en segundos, lo que acelera las implementaciones. Anular un contenedor de Docker es tan sencillo como invocar el `docker stop` comando, normalmente se completa en menos de un segundo.

Dado que los contenedores son intrínsecamente inmutables, por diseño, nunca debe preocuparse por máquinas virtuales dañadas porque olvidó un script de actualización para tener en cuenta alguna configuración concreta o archivo restante en el disco.

Aunque las aplicaciones monolíticas pueden beneficiarse de Docker, tocamos en sólo las sugerencias de las ventajas. Las mayores ventajas de administrar contenedores proceden de implementar con orquestadores de contenedores que administran las distintas instancias y ciclo de vida de cada instancia del contenedor. Separar la aplicación monolítica en subsistemas que se pueden escalar, desarrollar e implementar de forma individual es el punto de entrada al reino de los microservicios.

Para obtener información acerca de cómo "Levantar y mover" aplicaciones monolíticas con contenedores y cómo puede modernizar las aplicaciones, puede leer esta guía adicional de Microsoft, [modernizar aplicaciones .NET existentes con la nube de Azure y contenedores de Windows ](../../modernize-with-azure-and-containers/index.md), que también puede descargar como PDF desde <https://aka.ms/LiftAndShiftWithContainersEbook>.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Publicar una única aplicación de contenedor de Docker en Azure App Service

Ya sea porque desea obtener una validación rápida de un contenedor implementado en Azure o porque la aplicación es simplemente una aplicación de contenedor único, Azure App Services proporciona una excelente manera de proporcionar servicios escalables destinados a contenedor único.

Con Azure App Service es intuitivo y puede ponerse en y ejecute rápidamente porque proporciona excelente Git integración para que el código, compilarlo en Microsoft Visual Studio e implementarlo directamente en Azure. Pero, tradicionalmente (con ningún Docker), si necesitaba otras capacidades, marcos o dependencias que no son compatibles con servicios de aplicaciones, es necesario que esperar hasta que el equipo de Azure actualiza esas dependencias en App Service o cambiar a otros servicios como Service Fabric, servicios en la nube o máquinas virtuales incluso simples, que tiene más control y puede instalar un componente necesario o un marco para la aplicación.

Ahora, como se muestra en la figura 4-4, cuando se usa Visual Studio 2017, compatibilidad con contenedores en Azure App Service le ofrece la posibilidad de incluir lo que desea en su entorno de aplicación. Si agrega una dependencia a la aplicación, porque se está ejecutando en un contenedor, obtenga la capacidad de incluir esas dependencias en la imagen de Docker o Dockerfile.

![Vista del Asistente de Visual Studio para publicar en un servicio de aplicación de Azure, resaltando el selector para el registro de contenedor.](./media/image4.png)

**Figura 4-4**. Publicación de un contenedor en Azure App Service desde aplicaciones o contenedores de Visual Studio

Figura 4-4 también muestra que el flujo de publicación inserta una imagen a través de un registro de contenedor, que puede ser Azure Container Registry (un registro de cerca a las implementaciones en Azure y protege las cuentas y grupos de Azure Active Directory) o cualquier otro registro de Docker al igual que los registros de Docker Hub o en el entorno local.

>[!div class="step-by-step"]
>[Anterior](common-container-design-principles.md)
>[Siguiente](state-and-data-in-docker-applications.md)
