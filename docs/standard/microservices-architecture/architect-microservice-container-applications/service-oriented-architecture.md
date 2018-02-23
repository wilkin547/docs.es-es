---
title: Arquitectura orientada a servicios
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Arquitectura orientada a servicios
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a5f0f53f4208c9944adea33fe1aa3f35fed81ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="service-oriented-architecture"></a>Arquitectura orientada a servicios 

La arquitectura orientada a servicios (SOA) era un término sobreutilizado que significaba cosas diferentes para cada persona. Pero, como denominador común, SOA significa que se estructura una aplicación descomponiéndola en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en tipos diferentes, como subsistemas o niveles.

Estos servicios ahora se pueden implementar como contenedores de Docker, con lo que se resuelven los problemas de implementación, puesto que todas las dependencias se incluyen en la imagen de contenedor. Pero cuando se necesita escalar verticalmente aplicaciones SOA, es posible que tenga problemas de escalabilidad y disponibilidad si va a efectuar la implementación en función de hosts de Docker únicos. Aquí es donde le ayudará el software de agrupación en clústeres de Docker, o un orquestador, como se explica en secciones posteriores, donde se describen los enfoques de implementación para microservicios.

Los contenedores de Docker son útiles (pero no obligatorios) para las arquitecturas orientadas a servicios tradicionales y las arquitecturas de microservicios más avanzadas.

Los microservicios se derivan de SOA, pero SOA no es lo mismo que la arquitectura de microservicios. Características como los grandes agentes centrales, los orquestadores centrales en el nivel de organización y el [Bus de servicio empresarial (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) son habituales en SOA. Pero en la mayoría de los casos son antipatrones en la comunidad de microservicios. De hecho, hay quien argumenta que "la arquitectura de microservicios es SOA bien hecho".

Esta guía se centra en los microservicios, puesto que los enfoques SOA son menos prescriptivos que los requisitos y técnicas empleados en una arquitectura de microservicios. Si sabe cómo crear una aplicación basada en microservicios, también sabrá cómo crear una aplicación orientada a servicios más sencilla.




>[!div class="step-by-step"]
[Anterior] (docker-application-state-data.md) [Siguiente] (microservices-architecture.md)
