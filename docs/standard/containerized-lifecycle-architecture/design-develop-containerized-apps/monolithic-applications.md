---
title: Aplicaciones monolíticas
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9be0ac088a90bd34bb93550925d2e0aee5b91a21
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="monolithic-applications"></a>Aplicaciones monolíticas

En este escenario, está creando una aplicación web simple y monolítico o el servicio e implementando como un contenedor. Dentro de la aplicación, la estructura no puede ser monolítica; podrían forman parte de varias bibliotecas, componentes o incluso las capas (nivel de aplicación, el nivel de dominio, capa de acceso a datos, etcetera). Externamente, es un único contenedor, como un proceso único, sola aplicación web o servicio único.

Para administrar este modelo, debe implementar un único contenedor para representar la aplicación. Para ajustar la escala, basta con agregar unas cuantas copias más con un equilibrador de carga en la parte frontal. La simplicidad proviene de administrar una única implementación de un único contenedor o la máquina virtual (VM).

Después de la entidad de seguridad que realiza una acción sólo un contenedor y lo hace en un proceso, el patrón monolítico está en conflicto. Puede incluir varios componentes/bibliotecas o capas internas dentro de cada contenedor, como se muestra en la figura 4-1.

![](./media/image1.png)

Figura 4-1: muestra un ejemplo de arquitectura de aplicaciones monolítico

El inconveniente de este método incluye si o cuando crece la aplicación, que requiere una ampliación. Si se escala toda la aplicación, realmente no es un problema. Sin embargo, en la mayoría de los casos, algunas partes de la aplicación son los puntos de retracción que requieren el ajuste de escala, mientras que otros componentes se utilizan menos.

Con el ejemplo de comercio electrónico típico, lo que es probable que necesita es escalar el componente de información de producto. Hay muchos más clientes que buscan productos de los que los compran. Más clientes usan la cesta en lugar de usar la canalización de pago. Menos clientes publican comentarios o consultan su historial de compras. Y es probable que tenga solo un conjunto de empleados, en una única región, que necesita para administrar el contenido y las campañas de marketing. Escalando el diseño monolítico, todo el código se implementa varias veces.

Además el "escala-todo" problema, los cambios en un único componente requieren al volver a examinar completa de toda la aplicación, así como una implementación completa de todas las instancias.

El enfoque monolítico es bastante habitual y muchas organizaciones están desarrollando con este método de arquitectura. Muchos bueno disfrutan suficientes resultados, mientras que otros usuarios encuentran límites. Muchos diseñarse sus aplicaciones en este modelo, ya que la infraestructura y herramientas eran demasiado difíciles de SOA de compilación y no verán la necesidad, hasta que la aplicación ha crecido.

Desde una perspectiva de la infraestructura, cada servidor puede ejecutar muchas aplicaciones dentro del mismo host y tienen una proporción aceptable de eficacia en el uso de recursos, como se muestra en la figura 4-2.

![](./media/image2.png)

Figura 4-2: un host que ejecuta varias aplicaciones o contenedores

Puede implementar aplicaciones monolíticas en Azure mediante el uso de máquinas virtuales dedicadas para cada instancia. Usar [conjuntos de escalas de VM de Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), puede escalar fácilmente las máquinas virtuales. [Azure App Services](https://azure.microsoft.com/en-us/services/app-service/) puede ejecutar aplicaciones monolíticas y escalar fácilmente instancias sin necesidad de administrar las máquinas virtuales. A partir de 2016, servicios de aplicaciones de Azure puede ejecuta instancias únicas de contenedores de Docker, así, simplificar la implementación. Y con Docker, puede implementar una sola máquina virtual como un host Docker y ejecutar varias instancias. Con el equilibrador de Azure, como se muestra en la figura 4-3, puede administrar el ajuste de escala.

![](./media/image3.png)

Figura 4-3: varios hosts escalamiento una única aplicación aplicaciones/contenedores de Docker

Puede administrar la implementación a los distintos hosts a través de técnicas de implementación tradicionales. Puede administrar los hosts de Docker mediante el uso de comandos, como `docker run` manualmente, mediante la automatización, como las canalizaciones de entrega continua (CD), que se explican más adelante en este libro electrónico.

## <a name="monolithic-application-deployed-as-a-container"></a>Una aplicación monolítica implementada como un contenedor

Hay ventajas derivadas del uso de contenedores para administrar implementaciones monolíticas. Escalar las instancias de los contenedores es mucho más rápido y fácil que implementar máquinas virtuales adicionales. Aunque los conjuntos de escalas de VM son una característica excelente para escalar las máquinas virtuales, que son necesarios para alojar los contenedores de Docker, tardan tiempo en configurar. Cuando se implementa como instancias de aplicación, la configuración de la aplicación se administra como parte de la máquina virtual.

Implementar las actualizaciones como imágenes de Docker es mucho más rápido y eficaz en la red. Las instancias de Vn pueden configurarse en los mismos hosts que las instancias de Vn-1, lo que elimina los costos adicionales resultantes de máquinas virtuales adicionales. Imágenes de docker se inician normalmente en segundos, lo que acelera la implementación. Anular una instancia de Docker es tan sencillo como invocar el `docker stop` comando, normalmente se realizan en menos de un segundo.

Dado que los contenedores son intrínsecamente inmutables, por diseño, nunca necesite preocuparse sobre máquinas virtuales dañadas porque un script de actualización que se haya olvidado para tener en cuenta algunas configuración específica o un archivo restante en el disco.

Aunque monolíticas aplicaciones pueden beneficiarse de Docker, tocamos en sólo las sugerencias de las ventajas. Las mayores ventajas de administrar contenedores procede de la implementación con orchestrators de contenedor que administran las distintas instancias y ciclo de vida de cada instancia del contenedor. Separar la aplicación monolítica en subsistemas que se pueden escalar, desarrollar e implementar de forma individual es el punto de entrada al reino de los microservicios.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>Publicar una única aplicación de contenedor de Docker en el servicio de aplicaciones de Azure

Ya sea porque desea obtener una rápida validación de un contenedor de implementada en Azure o porque la aplicación está simplemente una aplicación de contenedor único, los servicios de aplicaciones de Azure proporciona una excelente manera de proporcionar servicios escalables destinados a single-container.

Con el servicio de aplicación de Azure es intuitivo y que pueda empezar a y ejecutando rápidamente porque proporciona gran Git integración tomar el código, genérelo en Microsoft Visual Studio y lo implementará directamente en Azure. Pero, tradicionalmente (con ningún Docker), si necesita otras funcionalidades, marcos o dependencias que no son compatibles con servicios de aplicaciones, deba esperar hasta que el equipo de Azure actualiza esas dependencias en el servicio de aplicaciones o ha cambiado a otros servicios como Service Fabric, servicios en la nube o máquinas virtuales incluso sin formato, para el que tiene más control y puede instalar un componente necesario o el marco de trabajo para la aplicación.

Ahora, sin embargo, (anunciadas en Microsoft Connect 2016 en noviembre de 2016) y como se muestra en la figura 4‑4, cuando se usa Visual Studio de 2017, compatibilidad con el contenedor en el servicio de aplicación de Azure ofrece la posibilidad de incluir todo lo que desees en el entorno de aplicación. Si agrega una dependencia a la aplicación, porque se está ejecutando en un contenedor, obtendrá la capacidad de incluir esas dependencias en la imagen de Dockerfile o Docker.

![](./media/image4.png)

Figura 4-4: publicación de un contenedor en servicio de aplicaciones de Azure de contenedores o aplicaciones de Visual Studio

Figura 4-4 también muestra que el flujo de publicación inserta una imagen a través de un registro de contenedor, que puede ser el registro del contenedor de Azure (en un registro de cerca a las implementaciones en Azure y protegido por las cuentas y grupos de Azure Active Directory) o cualquier otro registro de Docker al igual que los registros de Docker Hub o de forma local.


>[!div class="step-by-step"]
[Anterior] (común-contenedor-diseño-principles.md) [siguiente] (state-and-data-in-docker-applications.md)
