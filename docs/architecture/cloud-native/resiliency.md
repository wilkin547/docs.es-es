---
title: Resistencia nativa en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Resistencia nativa en la nube
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781086"
---
# <a name="cloud-native-resiliency"></a>Resistencia nativa en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La resistencia es la capacidad del sistema de reaccionar ante errores y seguir siendo funcional. No se trata de evitar los errores. Pero se trata de aceptar que el error es inevitable en los sistemas basados en la nube y compilar la aplicación para responder a ella. El objetivo final de la resistencia es devolver la aplicación a un estado totalmente funcional después de un error.

A diferencia de las aplicaciones monolíticas tradicionales, donde todo se ejecuta en un único proceso, los sistemas nativos en la nube adoptan una arquitectura distribuida como se muestra en la figura 6-1:

![Entorno distribuido nativo en la nube](./media/distributed-cloud-native-environment.png)

**Figura 6-1.** Entorno distribuido nativo en la nube

En la ilustración anterior, observe cómo cada cliente, microservicio y [servicio de respaldo](https://12factor.net/backing-services) basado en la nube se ejecutan como un proceso independiente que se ejecuta en distintos servidores y se comunican a través de llamadas basadas en red.

¿Qué podría ir mal?

- [Latencia de red](https://www.techopedia.com/definition/8553/network-latency)inesperada.
- Errores [transitorios](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (errores de conectividad de red temporales).
- Bloqueo mediante una operación sincrónica de ejecución prolongada.
- Un proceso de host que se ha bloqueado y se está reiniciando o moviendo.
- Microservicio sobrecargado que no puede responder durante un breve período de tiempo.
- Operación DevOps en curso, como una operación de actualización o escalado.
- Operación de orquestador, como mover un servicio de un nodo a otro.
- Errores de hardware de hardware estándar.

Al implementar servicios distribuidos en una infraestructura basada en la nube, los factores de la lista anterior se vuelven muy reales y debe diseñarlos y desarrollarlos de forma defensiva para abordarlos.

En un sistema distribuido a pequeña escala, el error será menos frecuente, pero a medida que un sistema se escale verticalmente y horizontalmente, puede esperar experimentar más de estos problemas hasta un punto en el que el error parcial se convierte en un funcionamiento normal.

Por lo tanto, la aplicación y la infraestructura deben ser resistentes. En las secciones siguientes, exploraremos técnicas defensivas que puede Agregar a su aplicación y características integradas en la nube que puede aprovechar para ayudar a revisar la experiencia del usuario.

>[!div class="step-by-step"]
>[Anterior](elastic-search-in-azure.md)
>[Siguiente](application-resiliency-patterns.md)
