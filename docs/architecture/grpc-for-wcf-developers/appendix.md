---
title: Apéndice-gRPC para desarrolladores de WCF
description: Explicación de las transacciones distribuidas y su implementación en arquitecturas de microservicios modernas.
ms.date: 09/02/2019
ms.openlocfilehash: 9931681727f921e007c2f80852ad0e69cd7288de
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711467"
---
# <a name="appendix-a---transactions"></a>Apéndice A: transacciones

Windows Communication Foundation (WCF) admite transacciones distribuidas, lo que le permite realizar operaciones atómicas en varios servicios. Esta funcionalidad se basa en [Microsoft Coordinador de transacciones distribuidas](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85)).

En el panorama de microservicios más reciente, no es posible este tipo de procesamiento automatizado de transacciones distribuidas. Hay demasiadas tecnologías diferentes, como las bases de datos relacionales, los almacenes de datos NoSQL y los sistemas de mensajería. También puede haber una combinación de sistemas operativos, lenguajes de programación y marcos de trabajo en uso en un solo entorno.

La transacción distribuida de WCF es una implementación de lo que se conoce como [confirmación en dos fases (2pc)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol). Puede implementar transacciones 2PC manualmente mediante la coordinación de mensajes entre servicios, la creación de transacciones abiertas dentro de cada servicio y el envío de mensajes de confirmación o reversión, dependiendo de si se ha realizado correctamente o no. Sin embargo, la complejidad implicada en la administración de 2PC puede aumentar exponencialmente a medida que evolucionan los sistemas. Las transacciones abiertas contienen bloqueos de base de datos que pueden afectar negativamente al rendimiento o, lo que es peor, causan interbloqueos entre servicios.

Si es posible, es mejor evitar todas las transacciones distribuidas. Si dos elementos de datos están vinculados como para requerir actualizaciones atómicas, considere la posibilidad de controlarlas ambos con el mismo servicio. Aplique esos cambios atómicos mediante una única solicitud o mensaje a ese servicio.

Si eso no es posible, una alternativa es usar el [patrón saga](https://microservices.io/patterns/data/saga.html). En un saga de actualización, las actualizaciones se procesan de forma secuencial. cuando cada actualización se realiza correctamente, se desencadena la siguiente. Estos desencadenadores se pueden propagar de un servicio a otro o ser administrados por un coordinador o un orquestador de saga. Si se produce un error en una actualización en cualquier momento durante el proceso, los servicios que ya han completado sus actualizaciones aplican una lógica específica para invertirlas.

Otra opción es usar el diseño controlado por dominios (DDD) y la segregación de responsabilidad de comandos y consultas (CQRS), tal como se describe en el [libro electrónico de microservicios de .net](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/). En concreto, el uso de eventos de dominio o de [orígenes de eventos](https://martinfowler.com/eaaDev/EventSourcing.html) puede ayudar a garantizar que las actualizaciones sean coherentes, si no se aplican inmediatamente.

>[!div class="step-by-step"]
>[Anterior](application-performance-management.md)
