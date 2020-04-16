---
title: Aplicaciones monolíticas
description: Descripción de los conceptos básicos para incluir en un contenedor aplicaciones monolíticas.
ms.date: 02/15/2019
ms.openlocfilehash: 3c186f6a300588816916886927f93e0c06ebd6bc
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988991"
---
# <a name="monolithic-applications"></a>Aplicaciones monolíticas

En este escenario, compilará una aplicación o un servicio web único y monolítico y lo implementará como un contenedor. La estructura de la aplicación podría no ser monolítica, sino incluir varias bibliotecas, componentes o incluso capas (nivel de aplicación, capa de dominio, capa de acceso a datos, etc.). Externamente es un contenedor único, como un proceso único, una aplicación web única o un servicio único.

Para administrar este modelo, debe implementar un único contenedor para representar la aplicación. Para escalarlo, solo tiene que agregar unas pocas copias más con un equilibrador de carga delante. La simplicidad proviene de administrar una única implementación en un solo contenedor o máquina virtual.

Al seguir el principio de que un contenedor realiza una sola acción y lo hace en un proceso, el patrón monolítico entra en conflicto. Puede incluir varios componentes, bibliotecas o capas internas en cada contenedor, como se muestra en la figura 4-1.

![Diagrama que muestra una aplicación monolítica que se escala horizontalmente mediante la clonación de la aplicación.](./media/monolithic-applications/monolithic-application-architecture-example.png)

**Figura 4-1.** Ejemplo de arquitectura de aplicaciones monolíticas

Una aplicación monolítica tiene todas o la mayoría de sus funcionalidades en un único proceso o contenedor y está formada por capas internas o bibliotecas. El inconveniente de este enfoque aparece cuando la aplicación aumenta y debe escalarse. Si se escala toda la aplicación, realmente no es un problema. Aun así, en la mayoría de los casos, solo unos pocos elementos de la aplicación son los puntos de obstrucción que deben escalarse, mientras que otros componentes se usan menos.

En el ejemplo típico de comercio electrónico, lo que probablemente necesite es escalar el componente de información del producto. Hay muchos más clientes que buscan productos de los que los compran. Más clientes usan la cesta en lugar de usar la canalización de pago. Menos clientes publican comentarios o consultan su historial de compras. Y es probable que solo cuente con un grupo reducido de empleados, en una única región, que tenga que administrar las campañas de contenido y marketing. Al escalar el diseño monolítico, todo el código se implementa varias veces.

Además del problema de "escalarlo todo", los cambios en un único componente requieren volver a probar por completo toda la aplicación e implementar por completo todas las instancias.

El enfoque monolítico es habitual y muchas organizaciones realizan el desarrollo con este método de diseño. Muchas disfrutan de resultados bastante buenos, mientras que otras se enfrentan a algunos límites. Muchas diseñaron sus aplicaciones con este modelo, ya que crear arquitecturas orientadas a servicios (SOA) con infraestructura y herramientas resultaba demasiado difícil, y no vieron la necesidad hasta que la aplicación creció.

Desde la perspectiva de la infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tener una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.

![Diagrama que muestra un host con varias aplicaciones en contenedores independientes.](./media/monolithic-applications/host-with-multiple-apps-containers.png)

**Figura 4-2.** Host que ejecuta varias aplicaciones o contenedores

Por último, desde la perspectiva de la disponibilidad, las aplicaciones monolíticas deben implementarse como un conjunto. Esto significa que, en caso de que deba *detener e iniciar*, todas las funcionalidades y todos los usuarios se verán afectados durante el período de implementación. En determinadas situaciones, el uso de Azure y de contenedores puede minimizar estas situaciones y reducir la probabilidad de tiempo de inactividad en la aplicación, como se aprecia en la figura 4-3.

Las aplicaciones monolíticas pueden implementarse en Azure con máquinas virtuales dedicadas para cada instancia. Con [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), las máquinas virtuales se pueden escalar fácilmente.

También puede usar [Azure App Services](https://azure.microsoft.com/services/app-service/) para ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales. Azure App Services también puede ejecutar instancias únicas de contenedores de Docker, lo que simplifica la implementación.

Puede implementar varias máquinas virtuales como hosts de Docker y ejecutar cualquier número de contenedores por máquina virtual. Después, puede administrar el escalado mediante Azure Load Balancer, como se muestra en la figura 4-3.

![Diagrama que muestra una aplicación monolítica escalada horizontalmente en hosts diferentes.](./media/monolithic-applications/multiple-hosts-from-single-docker-container.png)

**Figura 4-3**. Varios hosts escalan horizontalmente una única aplicación de Docker

Puede administrar la implementación de los propios hosts mediante técnicas de implementación tradicionales.

Puede administrar contenedores de Docker desde la línea de comandos mediante el uso de comandos como `docker run` y `docker-compose up`. También puede automatizar el proceso en las canalizaciones de entrega continua (CD) y realizar la implementación en hosts de Docker desde Azure DevOps Services, por ejemplo.

## <a name="monolithic-application-deployed-as-a-container"></a>Una aplicación monolítica implementada como un contenedor

El uso de contenedores para administrar implementaciones monolíticas tiene una serie de ventajas. Escalar las instancias de los contenedores es mucho más rápido y fácil que implementar máquinas virtuales adicionales.

Implementar las actualizaciones como imágenes de Docker es mucho más rápido y eficaz en la red. Normalmente, los contenedores de Docker se inician en segundos, lo que acelera las implementaciones. Anular un contenedor de Docker es tan fácil como invocar el comando `docker stop`, que normalmente se completa en menos de un segundo.

Como por diseño los contenedores son intrínsecamente inmutables, no tendrá que preocuparse de que las máquinas virtuales resulten dañadas porque un script de actualización olvidó tener en cuenta alguna configuración concreta o archivo que se conserve en disco.

Si bien las aplicaciones monolíticas pueden beneficiarse de Docker, estamos examinando estos beneficios muy por encima. Las ventajas adicionales de administrar contenedores proceden de implementar con orquestadores de contenedor que administran las distintas instancias y el ciclo de vida de cada instancia del contenedor. Separar la aplicación monolítica en subsistemas que se pueden escalar, desarrollar e implementar de forma individual es el punto de entrada al reino de los microservicios.

Para obtener información sobre cómo migrar aplicaciones monolíticas con contenedores mediante lift-and-shift y cómo puede modernizar las aplicaciones, lea la guía adicional de Microsoft titulada [Modernización de las aplicaciones .NET existentes con la nube de Azure y contenedores de Windows](../../modernize-with-azure-containers/index.md), que también puede descargar como PDF desde <https://aka.ms/LiftAndShiftWithContainersEbook>.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Publicación de una única aplicación de contenedor de Docker en Azure App Service

Tanto si quiere obtener la validación rápida de un contenedor implementado en Azure como si la aplicación es simplemente una aplicación de un solo contenedor, Azure App Service ofrece una excelente manera de proporcionar servicios escalables de un solo contenedor.

El uso de Azure App Service es intuitivo, por lo que puede empezar a trabajar rápidamente. Gracias a su excelente integración con GIT, puede tomar el código, compilarlo en Microsoft Visual Studio e implementarlo directamente en Azure. Tradicionalmente (es decir, sin Docker), si necesitaba otras funcionalidades, marcos o dependencias que no son compatibles con App Service, debía esperar a que el equipo de Azure actualizase esas dependencias en App Service o cambiar a otros servicios como Service Fabric, Cloud Services o incluso simples máquinas virtuales, sobre las que tiene más control y en las que puede instalar un componente o un marco necesarios para la aplicación.

Ahora, como se muestra en la figura 4-4, al usar Visual Studio 2017, la compatibilidad con contenedores en Azure App Service le ofrece la capacidad de incluir todo lo que quiera en el entorno de aplicación. Si agregó una dependencia en la aplicación porque la ejecuta en un contenedor, podrá incluir esas dependencias en la imagen de Docker o en el archivo Dockerfile.

![Captura de pantalla del cuadro de diálogo Crear servicio de aplicaciones que muestra una instancia de Container Registry.](./media/monolithic-applications/publish-azure-app-service-container.png)

**Figura 4-4**. Publicación de un contenedor en Azure App Service desde aplicaciones o contenedores de Visual Studio

En la figura 4-4 también puede verse que el flujo de publicación inserta una imagen a través de un registro de contenedor, que puede ser Azure Container Registry (un registro cercano a las implementaciones en Azure y protegido por las cuentas y los grupos de Azure Active Directory) o cualquier otro registro de Docker, como Docker Hub o registros locales.

>[!div class="step-by-step"]
>[Anterior](common-container-design-principles.md)
>[Siguiente](state-and-data-in-docker-applications.md)
