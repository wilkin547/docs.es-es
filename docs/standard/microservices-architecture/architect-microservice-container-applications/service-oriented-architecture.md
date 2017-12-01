---
title: Arquitectura orientada a servicios
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Arquitectura orientada a servicios
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a>Arquitectura orientada a servicios 

Arquitectura orientada a servicios (SOA) era un término sobreutilizado y objetivo cosas diferentes a distintas personas. Pero como denominador común, SOA significa estructurar la aplicación por descomponer en varios servicios (normalmente como servicios HTTP) que se pueden clasificar como tipos diferentes, como subsistemas o niveles.

Dichos servicios ahora se pueden implementar como contenedores de Docker, que resuelve los problemas de implementación, puesto que todas las dependencias se incluyen en la imagen del contenedor. Sin embargo, cuando necesite ampliar aplicaciones SOA, es posible que tenga la escalabilidad y desafíos de disponibilidad si va a implementar en función de los hosts de Docker únicos. Esto es donde Docker software de clústeres u organizador le ayudará a, como se explica en secciones posteriores donde se describen los enfoques de implementación para microservicios.

Contenedores de docker son útiles (pero no son necesarios) para las arquitecturas orientadas a servicios tradicionales y las arquitecturas de microservicios más avanzadas.

Microservicios se derivan de SOA, pero es diferente de la arquitectura de microservicios SOA. Características como el big corredores de bolsa centrales, orchestrators centrales en el nivel de organización y el [Bus de servicio de empresa (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) son típicos de SOA. Pero en la mayoría de los casos, estos son antipatrones en la Comunidad de microservicio. De hecho, algunas personas argumentan que "la arquitectura de microservicio es SOA bien."

Esta guía se centra en microservicios, dado que un enfoque SOA es menos descriptiva de los requisitos y las técnicas que se utilizan en una arquitectura de microservicio. Si sabe cómo crear una aplicación basada en microservicio, sabrá cómo crear una aplicación orientada a servicios más sencilla.




>[!div class="step-by-step"]
[Anterior] (docker-aplicaciones-estado-data.md) [siguiente] (microservicios architecture.md)
