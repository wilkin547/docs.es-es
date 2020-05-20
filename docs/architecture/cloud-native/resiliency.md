---
title: Resistencia nativa en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Resistencia nativa en la nube
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613777"
---
# <a name="cloud-native-resiliency"></a>Resistencia nativa en la nube

La resistencia es la capacidad del sistema de reaccionar ante errores y seguir siendo funcional. No se trata de evitar los errores, sino de aceptar errores y construir los servicios nativos de la nube para responder a ellos. Desea volver a un estado totalmente funcional lo más rápido posible.

A diferencia de las aplicaciones monolíticas tradicionales, donde todo se ejecuta en un único proceso, los sistemas nativos en la nube adoptan una arquitectura distribuida, tal como se muestra en la figura 6-1:

![Entorno distribuido nativo en la nube](./media/distributed-cloud-native-environment.png)

**Figura 6-1.** Entorno distribuido nativo en la nube

En la ilustración anterior, todos los microservicios y los [servicios de respaldo](https://12factor.net/backing-services) basados en la nube se ejecutan en un proceso independiente, en la infraestructura del servidor, que se comunican a través de llamadas basadas en red.

Al funcionar en este entorno, un servicio debe ser sensible a muchos desafíos diferentes:

- Latencia de red inesperada: el tiempo de una solicitud de servicio para viajar al receptor y viceversa.

- Errores [transitorios](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) : errores de conectividad de red de corta duración.

- Bloqueo mediante una operación sincrónica de ejecución prolongada.

- Un proceso de host que se ha bloqueado y se está reiniciando o moviendo.

- Microservicio sobrecargado que no puede responder durante un breve período de tiempo.

- Operación de Orchestrator en curso, como una actualización gradual o el traslado de un servicio de un nodo a otro.

- Errores de hardware.

Las plataformas en la nube pueden detectar y mitigar muchos de estos problemas de infraestructura. Puede reiniciar, escalar horizontalmente e incluso redistribuir el servicio a un nodo diferente.  Sin embargo, para sacar el máximo partido de esta protección integrada, debe diseñar los servicios para reaccionar ante ellos y prosperar en este entorno dinámico.

En las secciones siguientes, exploraremos técnicas defensivas que el servicio y los recursos de nube administrados pueden aprovechar para minimizar el tiempo de inactividad y la interrupción.

>[!div class="step-by-step"]
>[Anterior](elastic-search-in-azure.md)
>[Siguiente](application-resiliency-patterns.md)
