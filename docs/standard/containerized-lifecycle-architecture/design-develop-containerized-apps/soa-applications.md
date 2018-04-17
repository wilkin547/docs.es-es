---
title: Aplicaciones SOA
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 48dc0f038cee8ddc9555881f2143b566df223a04
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="soa-applications"></a>Aplicaciones SOA

SOA era un término sobreutilizado y su fin tantas cosas diferentes a distintas personas. Pero como mínimo y como denominador común, SOA, o la orientación al servicio, Media que conforman la arquitectura de la aplicación, descomponiendo en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en diferentes tipos como subsistemas o bien, en otros casos, como niveles.

Hoy en día, puede implementar estos servicios como contenedores de Docker, que soluciona problemas relacionados con la implementación, ya que todas las dependencias se incluyen dentro de la imagen del contenedor. Sin embargo, cuando necesite escalabilidad SOA, podría encontrar desafíos si va a implementar en función de instancias únicas. Esto es donde una Docker software de clústeres o orchestrator le ayudará a. Echemos un vistazo esto con más detalle en la sección siguiente cuando se examinan microservicios enfoques.

Al final del día, las soluciones de agrupación en clústeres de contenedor son útiles para ambas una arquitectura SOA tradicional o para una arquitectura de microservicios más avanzada en la que cada microservicio posee su modelo de datos. Y, gracias a varias bases de datos, también puede horizontal el nivel de datos en lugar de trabajar con bases de datos monolíticos compartidas por los servicios SOA. Sin embargo, la discusión sobre cómo dividir los datos es puramente sobre la arquitectura y diseño.


>[!div class="step-by-step"]
[Anterior] (state-and-data-in-docker-applications.md) [siguiente] (orquestar-alta-escalabilidad-availability.md)
