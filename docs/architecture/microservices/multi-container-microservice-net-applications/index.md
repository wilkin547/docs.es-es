---
title: Diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Descripción de la arquitectura externa para diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios
ms.date: 10/02/2018
ms.openlocfilehash: 8c2f828e9913a0efcdf580371124b0f624daeffe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "70295232"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a>Diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios

*Si desarrolla aplicaciones de microservicios en contenedor significa que está compilando aplicaciones de varios contenedores. Pero una aplicación de varios contenedores también podría ser más sencilla (por ejemplo, una aplicación de tres niveles) y podría no compilarse con una arquitectura de microservicios.*

Anteriormente se planteó la pregunta "¿Se necesita Docker para compilar una arquitectura de microservicios?". La respuesta es un no rotundo. Docker es un habilitador y puede proporcionar grandes ventajas, pero los contenedores y Docker no son un requisito imprescindible para los microservicios. Por ejemplo, podría crear una aplicación basada en microservicios con o sin Docker al usar Azure Service Fabric, que es compatible con los microservicios que se ejecutan como procesos simples o como contenedores de Docker.

Pero si sabe cómo diseñar y desarrollar una aplicación basada en microservicios que también se base en contenedores de Docker, podrá diseñar y desarrollar cualquier modelo de aplicación más sencillo. Por ejemplo, podría diseñar una aplicación de tres niveles que también requiera un enfoque de varios contenedores. Debido a eso, y dado que las arquitecturas de microservicios son una tendencia importante en el mundo de los contenedores, esta sección se centra en la implementación de una arquitectura de microservicios con contenedores de Docker.

>[!div class="step-by-step"]
>[Anterior](../docker-application-development-process/docker-app-development-workflow.md)
>[Siguiente](microservice-application-design.md)
