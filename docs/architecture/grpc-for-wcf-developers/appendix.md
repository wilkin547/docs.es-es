---
title: Apéndice-gRPC para desarrolladores de WCF
description: Explicación de las transacciones distribuidas y su implementación en arquitecturas de microservicios modernas.
ms.date: 09/02/2019
ms.openlocfilehash: 061aef016fd0e4303e1bbcbf0e73cec2b0c54f74
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968215"
---
# <a name="appendix-a---transactions"></a>Apéndice A: transacciones

Windows Communication Foundation (WCF) admiten las transacciones distribuidas, lo que permite realizar operaciones atómicas en varios servicios. Esta funcionalidad se basó en [Microsoft Coordinador de transacciones distribuidas](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85)).

En el panorama moderno de microservicios, este tipo de procesamiento automatizado de transacciones distribuidas no es posible. Hay demasiadas tecnologías diferentes en juego, incluidas las bases de datos relacionales, los almacenes de datos NoSQL y los sistemas de mensajería, no para mencionar la combinación de sistemas operativos, lenguajes de programación y marcos que se pueden usar en un solo entorno.

La transacción distribuida de WCF es una implementación de lo que se conoce como [confirmación en dos fases (2pc)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol). Es posible implementar transacciones de 2PC manualmente mediante la coordinación de mensajes en los servicios, la creación de transacciones abiertas dentro de cada servicio y el envío de mensajes de "confirmación" o "reversión" dependiendo de si se ha realizado correctamente o no. Sin embargo, la complejidad implicada en la administración de 2PC puede aumentar exponencialmente a medida que los sistemas evolucionen, y las transacciones abiertas conservan bloqueos de base de datos que pueden afectar negativamente al rendimiento o, lo que es peor, causan interbloqueos entre servicios.

Si es posible, es mejor evitar todas las transacciones distribuidas. Si dos elementos de datos están vinculados como para requerir actualizaciones atómicas, considere la posibilidad de controlarlas ambos con el mismo servicio y aplicar esos cambios atómicos con una única solicitud o mensaje a ese servicio.

Si eso no es posible, una alternativa es usar el [patrón saga](https://microservices.io/patterns/data/saga.html). En un saga de actualización, las actualizaciones se procesan secuencialmente. cuando cada actualización se realiza correctamente, se desencadena la siguiente. Estos desencadenadores se pueden propagar de un servicio a otro o ser administrados por un coordinador de saga o un "orquestador". Si se produce un error en una actualización en cualquier momento durante el proceso, los servicios que ya han completado sus actualizaciones aplican una lógica específica para invertirlas.

Otra opción es usar el diseño controlado por dominios (DDD) y la segregación de responsabilidad de comandos y consultas (CQRS), tal como se describe en el [libro electrónico de microservicios de .net](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/). En concreto, el uso de eventos de dominio o de [orígenes de eventos](https://martinfowler.com/eaaDev/EventSourcing.html) puede ayudar a garantizar que las actualizaciones sean coherentes&mdash;si no&mdash;aplican inmediatamente.

>[!div class="step-by-step"]
>[Anterior](application-performance-management.md)
