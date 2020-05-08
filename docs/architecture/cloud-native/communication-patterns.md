---
title: Patrones de comunicación nativa en la nube
description: Más información sobre las principales preocupaciones sobre la comunicación de servicios en aplicaciones nativas en la nube
author: robvet
ms.date: 08/31/2019
ms.openlocfilehash: b3edc0817fb76ad99a1344b17d600eb747187f86
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895629"
---
# <a name="cloud-native-communication-patterns"></a>Patrones de comunicación nativa en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Al construir un sistema nativo en la nube, la comunicación se convierte en una decisión de diseño significativa. ¿Cómo se comunica una aplicación cliente front-end con un microservicio de back-end? ¿Cómo se comunican entre sí los microservicios de back-end? ¿Cuáles son los principios, patrones y procedimientos recomendados que se deben tener en cuenta al implementar la comunicación en aplicaciones nativas de la nube?

## <a name="communication-considerations"></a>Consideraciones de comunicación

En una aplicación monolítica, la comunicación es sencilla. Los módulos de código se ejecutan juntos en el mismo espacio ejecutable (proceso) en un servidor. Este enfoque puede tener ventajas de rendimiento, ya que todo se ejecuta en la memoria compartida, pero tiene como resultado un código estrechamente acoplado que resulta difícil de mantener, evolucionar y escalar.

Los sistemas nativos en la nube implementan una arquitectura basada en microservicios con muchos microservicios pequeños e independientes. Cada microservicio se ejecuta en un proceso independiente y normalmente se ejecuta dentro de un contenedor que se implementa en un *clúster*.

Un clúster agrupa un grupo de máquinas virtuales para formar un entorno de alta disponibilidad. Se administran con una herramienta de orquestación, que es responsable de implementar y administrar los microservicios en contenedores. En la figura 4-1 se muestra un clúster de [Kubernetes](https://kubernetes.io) implementado en la nube de Azure con [Azure Kubernetes Services](https://docs.microsoft.com/azure/aks/intro-kubernetes)totalmente administrado.

![Un clúster de Kubernetes en Azure](./media/kubernetes-cluster-in-azure.png)

**Figura 4-1**. Un clúster de Kubernetes en Azure

En el clúster, los microservicios se comunican entre sí a través de las API y las tecnologías de mensajería.

Aunque ofrecen muchas ventajas, los microservicios no son comer. Ahora, las llamadas a métodos locales en proceso entre componentes se reemplazan por llamadas de red. Cada microservicio debe comunicarse a través de un protocolo de red, lo que aumenta la complejidad del sistema:

- La congestión de la red, la latencia y los errores transitorios son un problema constante.

- La resistencia (es decir, el reintento de solicitudes con error) es fundamental.

- Algunas llamadas deben ser [idempotente](https://www.restapitutorial.com/lessons/idempotency.html) para mantener el estado coherente.

- Cada microservicio debe autenticar y autorizar las llamadas.

- Cada mensaje se debe serializar y, a continuación, deserializar, lo que puede ser caro.

- El cifrado/descifrado de mensajes es importante.

El libro [microservicios de .net: arquitectura para aplicaciones .net en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook), disponible de forma gratuita de Microsoft, proporciona una cobertura detallada de los patrones de comunicación para las aplicaciones de microservicios. En este capítulo, se proporciona información general de alto nivel de estos patrones junto con las opciones de implementación disponibles en la nube de Azure.

En este capítulo, primero abordaremos la comunicación entre las aplicaciones front-end y los microservicios de back-end. A continuación, veremos que los microservicios de back-end se comunican entre sí. Exploraremos la tecnología de comunicación up y gRPC. Por último, veremos nuevos patrones de comunicación innovadores con la tecnología de la malla de servicio. También veremos cómo la nube de Azure proporciona diferentes tipos de *servicios de respaldo* para admitir la comunicación nativa en la nube.

>[!div class="step-by-step"]
>[Anterior](other-deployment-options.md)
>[Siguiente](front-end-communication.md)
