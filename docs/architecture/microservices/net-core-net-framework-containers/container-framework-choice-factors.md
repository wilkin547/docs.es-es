---
title: Tabla de decisiones. Versiones de .NET Framework para su uso con Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Tabla de decisiones, versiones de .NET Framework para su uso con Docker
ms.date: 09/11/2018
ms.openlocfilehash: 8ffe2b7bc0bee976d3a63b274994dbcc8aef0c61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628324"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabla de decisiones: versiones de .NET Framework para su uso con Docker

En la siguiente tabla de decisiones se resume si se debe usar .NET Framework o .NET Core. Recuerde que, para los contenedores de Linux, necesita hosts de Docker basados en Linux (máquinas virtuales o servidores) y, para los contenedores de Windows, necesita hosts de Docker basados en Windows Server (máquinas virtuales o servidores).

> [!IMPORTANT]
> Los equipos de desarrollo ejecutarán un host de Docker, ya sea Linux o Windows. Todos los microservicios relacionados que quiera ejecutar y probar juntos en una solución deberán ejecutarse en la misma plataforma de contenedor.

| Arquitectura/tipo de aplicación | Contenedores de Linux | Contenedores de Windows |
|-------------------------|------------------|--------------------|
| Microservicios en contenedores | Núcleo de .NET | .NET Core |
| Aplicación monolítica | .NET Core | .NET Framework <br/> .NET Core |
| Rendimiento y escalabilidad líderes | .NET Core | .NET Core |
| Migración de aplicación heredada de Windows Server ("brown-field") a contenedores | -- | .NET Framework |
| Nuevo desarrollo basado en contenedor ("green-field") | .NET Core | .NET Core |
| ASP.NET Core | .NET Core | .NET Core (recomendado) <br/> .NET Framework |
| ASP.NET 4 (MVC 5, API web 2 y formularios Web Forms) | -- | .NET Framework |
| Servicios SignalR | .NET Core 2.1 o versiones posteriores | .NET Framework <br/> .NET Core 2.1 o versiones posteriores |
| WCF, WF y otros marcos heredados | WCF en .NET Core (solo la biblioteca cliente) | .NET Framework <br/> WCF en .NET Core (solo la biblioteca cliente) |
| Consumo de servicios de Azure | .NET Core <br/> (finalmente, la mayoría de los servicios de Azure proporcionarán el SDK de cliente para .NET Core) | .NET Framework <br/> .NET Core <br/> (finalmente, la mayoría de los servicios de Azure proporcionarán el SDK de cliente para .NET Core) |

>[!div class="step-by-step"]
>[Anterior](net-framework-container-scenarios.md)
>[Siguiente](net-container-os-targets.md)
