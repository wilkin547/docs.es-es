---
title: Control de errores parciales
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Control de errores parciales
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7d16acf3de2d395da70e8f46e59c129dec24f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="handling-partial-failure"></a>Control de errores parciales

En los sistemas distribuidos a las aplicaciones basadas en microservicios, hay un riesgo de error parcial omnipresente. Por ejemplo, un único contenedor/microservicio puede producir un error o podría no estar disponible para responder durante un breve período, o se puede bloquear una única máquina virtual o servidor. Puesto que los clientes y servicios son procesos independientes, es posible que un servicio no pueda responder de forma oportuna a solicitud del cliente. El servicio podría estar sobrecargadas y responde muy lentamente a las solicitudes de, o simplemente no está accesible durante un breve tiempo debido a problemas de red.

Por ejemplo, considere la posibilidad de la página de detalles de pedido desde el eShopOnContainers aplicación de ejemplo. Si la ordenación microservicio deja de responder cuando el usuario intenta enviar un pedido, una implementación incorrecta del proceso del cliente (la aplicación web MVC), por ejemplo, si el código de cliente usara RPC sincrónica sin tiempo de espera, se bloquea los subprocesos indefinidamente Esperando una respuesta. Además de crear una experiencia de usuario incorrectos, consume cada espera no responde o a un subproceso bloquea y subprocesos son muy valiosos en aplicaciones muy escalables. Si hay demasiados subprocesos bloqueados, finalmente en tiempo de ejecución de la aplicación puede quedarse sin subprocesos. En ese caso, la aplicación puede tornarse más global que no responde en lugar de simplemente parcialmente no responde, tal como se muestra en la figura 10-1.

![](./media/image1.png)

**Figura 10-1**. Errores parciales debido a las dependencias que afectan la disponibilidad de subprocesos de servicio

En una aplicación basada en microservicios grande, puede se amplifique cualquier error parcial, especialmente si la mayor parte de la interacción de microservicios interno se basa en las llamadas sincrónicas de HTTP (que se considera un antipatrón). Piense en un sistema que recibe millones de llamadas entrantes al día. Si el sistema tiene un diseño incorrecto que se basa en cadenas largas de las llamadas sincrónicas de HTTP, estas llamadas entrantes podrían producir muchos millones de más de las llamadas salientes (supongamos que una proporción 1:4) al docenas de microservicios interno como dependencias sincrónicas. Esta situación se muestra en la figura 10-2, especialmente dependencia \#3.

![](./media/image2.png)

**Figura 10-2**. El impacto de tener un diseño incorrecto que incluye cadenas largas de solicitudes HTTP

Error intermitente es prácticamente garantizada en distribuida y en la nube en función de sistema, aunque cada dependencia sí tiene una disponibilidad excelente. Debe ser un hecho que debe tener en cuenta.

Si no diseñar e implementar técnicas para asegurar la tolerancia a errores, pueden ampliarse incluso pequeños tiempos de inactividad. Por ejemplo, 50 dependencias con 99,99% de disponibilidad se crearán varias horas de tiempo de inactividad cada mes debido a este efecto dominó. Cuando se produce un error en una dependencia de microservicio al controlar un gran volumen de solicitudes, dicho error puede saturar todos los subprocesos de solicitud disponible en cada servicio rápidamente y se bloqueará toda la aplicación.

![](./media/image3.png)

**Figura 10-3**. Error parcial ampliado por microservicios con cadenas largas de las llamadas sincrónicas de HTTP

Para minimizar este problema, en la sección "*microservicio asincrónica integración exigir la autonomía de microservicio*" (en el capítulo sobre arquitectura), se recomienda usar la comunicación asincrónica entre interno microservicios. Brevemente explicamos más en la sección siguiente.

Además, es fundamental que diseña las aplicaciones cliente y microservicios para controlar los errores parciales, es decir, crear microservicios resistente y cliente de aplicaciones.


>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (partial-error-strategies.md)
