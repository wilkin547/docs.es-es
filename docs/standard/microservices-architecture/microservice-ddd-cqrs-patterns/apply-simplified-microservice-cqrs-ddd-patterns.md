---
title: Aplicar los patrones CQRS y DDD simplificados en un microservicio
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Aplicar los patrones CQRS y DDD simplificados en un microservicio
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 99fd7ce32039742e23f8e01aa4c33cddd7a9f698
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>Aplicar los patrones CQRS y DDD simplificados en un microservicio

CQRS es un modelo de arquitectura que separa los modelos para leer y escribir datos. El término relacionado [comando consulta separación (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) se definió originalmente por Bertrand Meyer en su libro *la construcción de Software orientadas a objetos*. La idea básica es que puede dividir las operaciones del sistema en dos categorías claramente separados:

-   Consultas. Estas devuelven un resultado y no cambian el estado del sistema, y tienen la posibilidad de los efectos secundarios.

-   Comandos. Éstas cambian el estado de un sistema.

CQS es un concepto simple: se trata de métodos dentro del mismo objeto que se va a consultas o comandos. Cada método devuelve el estado o estado, pero no ambos transforma. Incluso un objeto de patrón de repositorio único puede cumplir CQS. CQS puede considerarse un principio fundamental para CQRS.

[Comando y la segregación de responsabilidad de consulta (CQRS)](https://martinfowler.com/bliki/CQRS.html) se introdujo por Greg Young y promocionan fuertemente Udi Dahan y otros. Se basa en el principio CQS, aunque es más detallado. Se puede considerar un modelo basado en eventos y comandos plus opcionalmente en mensajes asincrónicos. En muchos casos, CQRS está relacionado con los escenarios más avanzados, como tener otra base de datos físico para lecturas (consultas) que para operaciones de escritura (actualizaciones). Además, podría implementar un sistema CQRS más evolved [eventos de origen (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/) para la base de datos de las actualizaciones, lo que se podrían solo almacenar eventos en el modelo de dominio en lugar de almacenar los datos de estado actual. Sin embargo, esto no es el enfoque usado en esta guía; Estamos utilizando el enfoque más sencillo CQRS, que consta de simplemente separar las consultas de los comandos.

El aspecto de separación de CQRS se logra mediante la agrupación de las operaciones de consulta en una capa y comandos de otra capa. Cada capa tiene su propio modelo de datos (tenga en cuenta que decimos modelo, no necesariamente a una base de datos diferente) y se basa en su propia combinación de patrones y las tecnologías. Lo que es más importante, las dos capas pueden ser dentro del mismo nivel o microservicio, como en el ejemplo (ordenación microservicio) utilizado para esta guía. O bien, podría implementarse en diferentes microservicios o procesos para poder optimizados y escalar horizontalmente por separado sin que afecte a entre sí.

CQRS significa tener dos objetos para una operación de lectura/escritura que en otros contextos hay uno. Hay razones para tener una base de datos sin normalizar las lecturas, que puede obtener información acerca de en la literatura CQRS más avanzada. Pero no estamos utilizando ese método en este sentido, cuyo objetivo es tener más flexibilidad en las consultas en lugar de limitar las consultas con las restricciones de los patrones de DDD similares agregados.

Un ejemplo de este tipo de servicio es la ordenación microservicio desde la aplicación de referencia de eShopOnContainers. Este servicio implementa un microservicio basado en un enfoque simplificado de CQRS. Utiliza un único origen de datos o base de datos, pero dos modelos lógicos más patrones DDD para el dominio transaccional, tal como se muestra en la figura 9-2.

![](./media/image2.png)

**Figura 9-2**. Microservicio simplificada basada en DDD y CQRS

La capa de aplicación puede ser la propia API Web. El aspecto de diseño importante aquí es que divide el microservicio las consultas y ViewModels (modelos de datos creados especialmente para las aplicaciones cliente) de los comandos, modelo de dominio y las transacciones tras el patrón CQRS. Este enfoque mantiene las consultas independiente de las restricciones y las restricciones procedentes de los patrones DDD que solo tienen sentido para las transacciones y las actualizaciones, como se explica en secciones posteriores.


>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (eshoponcontainers-cqrs-ddd-microservice.md)
