---
title: Direccionabilidad de microservicios y el Registro del servicio
description: Comprenda la función de los registros de imagen de contenedor en la arquitectura de microservicios.
ms.date: 01/13/2021
ms.openlocfilehash: 363a307d44d30125563863bbe3ebeb5f5b9ad2bc
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188418"
---
# <a name="microservices-addressability-and-the-service-registry"></a>Direccionabilidad de microservicios y el Registro del servicio

Cada microservicio tiene un nombre único (URL) que se usa para resolver su ubicación. El microservicio debe ser direccionable en cualquier lugar donde se ejecute. Si tiene que pensar en qué equipo se ejecuta un microservicio determinado, todo puede ir mal rápidamente. De la misma manera que DNS resuelve una URL para un equipo en particular, su microservicio debe tener un nombre único para que su ubicación actual sea reconocible. Los microservicios deben tener nombres direccionables que les permitan ser independientes de la infraestructura en que se ejecutan. Este enfoque implica que hay una interacción entre cómo se implementa el servicio y cómo se detecta, porque debe haber un [registro del servicio](https://microservices.io/patterns/service-registry.html). Del mismo modo, cuando se produce un error en un equipo, el servicio del Registro debe ser capaz de indicar que el servicio se está ejecutando.

El [patrón del Registro del servicio](https://microservices.io/patterns/service-registry.html) es una parte fundamental de la detección de servicios. El Registro es una base de datos que contiene las ubicaciones de red de las instancias del servicio. Un Registro del servicio debe estar muy disponible y actualizado. Los clientes podrían almacenar en caché las ubicaciones de red obtenidas del Registro del servicio. Sin embargo, esa información finalmente se queda obsoleta y los clientes ya no pueden detectar las instancias del servicio. Por tanto, un registro del servicio consta de un clúster de servidores que usan un protocolo de replicación para mantener su coherencia.

En algunos entornos de implementación de microservicios (denominados clústeres, de los cuales se hablará en una sección posterior), la detección de servicios está integrada. Por ejemplo, un entorno de Azure Container Service con Kubernetes (AKS) puede controlar el Registro y la anulación del Registro de la instancia del servicio. También ejecuta un proxy en cada host del clúster que desempeña el rol de enrutador de detección del lado servidor.

## <a name="additional-resources"></a>Recursos adicionales

- **Chris Richardson. Patrón: Registro de servicios** \
  <https://microservices.io/patterns/service-registry.html>

- **Auth0. El registro de servicios** \
  <https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/>

- **Gabriel Schenker. Detección de servicios** \
  <https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/>

>[!div class="step-by-step"]
>[Anterior](maintain-microservice-apis.md)
>[Siguiente](microservice-based-composite-ui-shape-layout.md)
