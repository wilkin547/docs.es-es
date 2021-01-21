---
title: Tabla de decisiones. Versiones de .NET Framework para su uso con Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Tabla de decisiones, versiones de .NET Framework para su uso con Docker
ms.date: 01/13/2021
ms.openlocfilehash: 35f101b3f4030e081068677b3754363bf6cd8210
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188665"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabla de decisiones: versiones de .NET Framework para su uso con Docker

En la siguiente tabla de decisiones se resume si se debe usar .NET Framework o .NET 5. Recuerde que, para los contenedores de Linux, necesita hosts de Docker basados en Linux (máquinas virtuales o servidores) y, para los contenedores de Windows, necesita hosts de Docker basados en Windows Server (máquinas virtuales o servidores).

> [!IMPORTANT]
> Los equipos de desarrollo ejecutarán un host de Docker, ya sea Linux o Windows. Todos los microservicios relacionados que quiera ejecutar y probar juntos en una solución deberán ejecutarse en la misma plataforma de contenedor.

| Arquitectura/tipo de aplicación | Contenedores de Linux | Contenedores de Windows |
|-------------------------|------------------|--------------------|
| Microservicios en contenedores | .NET 5 | .NET 5 |
| Aplicación monolítica | .NET 5 | .NET Framework <br/> .NET 5 |
| Rendimiento y escalabilidad líderes | .NET 5 | .NET 5 |
| Migración de aplicación heredada de Windows Server ("brown-field") a contenedores | -- | .NET Framework |
| Nuevo desarrollo basado en contenedor ("green-field") | .NET 5 | .NET 5 |
| ASP.NET Core | .NET 5 | .NET 5 (recomendado) <br/> .NET Framework |
| ASP.NET 4 (MVC 5, API web 2 y formularios Web Forms) | -- | .NET Framework |
| Servicios SignalR | .NET Core 2.1 o versiones posteriores | .NET Framework <br/> .NET Core 2.1 o versiones posteriores |
| WCF, WF y otros marcos heredados | WCF en .NET Core (solo la biblioteca cliente) | .NET Framework <br/> WCF en .NET 5 (solo en la biblioteca de cliente) |
| Consumo de servicios de Azure | .NET 5 <br/> (finalmente, la mayoría de los servicios de Azure proporcionarán el SDK de cliente para .NET 5) | .NET Framework <br/> .NET 5 <br/> (finalmente, la mayoría de los servicios de Azure proporcionarán el SDK de cliente para .NET 5) |

>[!div class="step-by-step"]
>[Anterior](net-framework-container-scenarios.md)
>[Siguiente](net-container-os-targets.md)
