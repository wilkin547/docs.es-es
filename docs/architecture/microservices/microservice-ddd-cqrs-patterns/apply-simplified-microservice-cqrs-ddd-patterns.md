---
title: Aplicar los patrones CQRS y DDD simplificados en un microservicio
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Información sobre la relación general entre patrones DDD y CQRS.
ms.date: 10/08/2018
ms.openlocfilehash: e4e36bafff39f5f30d6371ed7c113322a85c3362
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805594"
---
# <a name="apply-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>Aplicación de patrones CQRS y DDD simplificados en un microservicio

CQRS es un patrón de arquitectura que separa los modelos para leer y escribir datos. Bertrand Meyer definió originalmente el término relacionado [Separación de consultas y comandos (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) en su libro *Construcción de software orientada a objetos*. La idea básica es que puede dividir las operaciones de un sistema en dos categorías claramente diferenciadas:

- Consultas. Devuelven un resultado sin cambiar el estado del sistema y no tienen efectos secundarios.

- Comandos. Cambian el estado de un sistema.

CQS es un concepto simple: se trata de métodos dentro del mismo objeto que son consultas o comandos. Cada método devuelve o transforma el estado, pero no ambas cosas. Incluso un único objeto de patrón de repositorio puede cumplir con CQS. CQS puede considerarse un principio fundamental para CQRS.

Greg Young introdujo el concepto [Segregación de responsabilidad de consultas y comandos (CQRS)](https://martinfowler.com/bliki/CQRS.html), que también lo promocionaron mucho Udi Dahan y otros. Se basa en el principio CQS, aunque es más detallado. Se puede considerar un patrón basado en comandos y eventos y, opcionalmente, en mensajes asincrónicos. En muchos casos, CQRS está relacionado con escenarios más avanzados, como tener una base de datos física para operaciones de lectura (consultas) distinta que para operaciones de escritura (actualizaciones). Además, un sistema CQRS más evolucionado podría implementar [Event-Sourcing (ES)](https://martinfowler.com/eaaDev/EventSourcing.html) para la base de datos de las actualizaciones, de modo que solo almacenaría eventos en el modelo del dominio en lugar de almacenar los datos de estado actual. Sin embargo, este enfoque no se utiliza en esta guía. En esta guía se usa el enfoque CQRS más sencillo, que consiste simplemente en separar las consultas de los comandos.

La separación que CQRS persigue se consigue mediante la agrupación de las operaciones de consulta en una capa y de los comandos en otra. Cada capa tiene su propio modelo de datos (tenga en cuenta que decimos modelo, no necesariamente una base de datos diferente) y se basa en su propia combinación de patrones y tecnologías. Lo más importante es que las dos capas pueden estar dentro del mismo nivel o microservicio, como en el ejemplo (microservicio de pedidos) usado para esta guía. O pueden implementarse en diferentes microservicios o procesos para que se puedan optimizar y escalar horizontalmente por separado sin que una afecte a la otra.

CQRS significa tener dos objetos para una operación de lectura/escritura cuando en otros contextos solo hay uno. Hay razones para tener una base de datos para las operaciones de lectura sin normalizar, de la cual puede obtener información en la bibliografía sobre CQRS más avanzada. Pero aquí no vamos a usar ese enfoque, ya que el objetivo es tener más flexibilidad en las consultas en lugar de limitar las consultas con las restricciones de patrones de DDD como los agregados.

Un ejemplo de este tipo de servicio es el microservicio de pedidos de la aplicación de referencia de eShopOnContainers. Este servicio implementa un microservicio basado en un enfoque simplificado de CQRS. Usa un solo origen de datos o base de datos, pero dos modelos lógicos, además de patrones de DDD para el dominio transaccional, como se muestra en la figura 7-2.

![Diagrama que muestra un microservicio CQRS y DDD simplificado de alto nivel.](./media/apply-simplified-microservice-cqrs-ddd-patterns/simplified-cqrs-ddd-microservice.png)

**Figura 7-2**. Microservicio con CQRS simplificado y basado en DDD

El microservicio "Ordering" lógico incluye su base de datos Ordering, que puede estar, pero no tiene que estar, en el mismo host de Docker. La presencia de la base de datos en el mismo host de Docker es buena para el desarrollo, pero no para producción.

El nivel de aplicación puede ser la propia API web. Aquí, el aspecto de diseño importante es que el microservicio, siguiendo el patrón de CQRS, ha dividido las consultas y los ViewModels (modelos de datos creados especialmente para las aplicaciones cliente) de los comandos, del modelo del dominio y de las transacciones. Este enfoque mantiene las consultas independientes de las restricciones procedentes de los patrones DDD que solo tienen sentido para las transacciones y las actualizaciones, como se explica en secciones posteriores.

## <a name="additional-resources"></a>Recursos adicionales

- **Greg Young. Versioning in an Event Sourced System** (Control de versiones en un sistema con abastecimiento de eventos, libro electrónico en línea gratuito) \
   <https://leanpub.com/esversioning/read>

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](eshoponcontainers-cqrs-ddd-microservice.md)
