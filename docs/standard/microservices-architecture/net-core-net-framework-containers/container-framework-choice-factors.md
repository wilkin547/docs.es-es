---
title: Tabla de decisiones. Versiones de .NET Framework para su uso con Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Tabla de decisiones, versiones de .NET Framework para su uso con Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: c45fbb9f26e6cd315e1b623ba2c79d5d038a6919
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105305"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabla de decisiones: versiones de .NET Framework para su uso con Docker

A continuación se resume si se debe usar .NET Framework o .NET Core y los contenedores de Windows o de Linux. Recuerde que, para los contenedores de Linux, necesita hosts de Docker basados en Linux (máquinas virtuales o servidores) y, para los contenedores de Windows, necesita hosts de Docker basados en Windows Server (máquinas virtuales o servidores).

Hay varias características de la aplicación que afectan a su decisión. Debería sopesar la importancia de estas características a la hora de tomar una decisión.

> [!IMPORTANT]
> Los equipos de desarrollo ejecutarán un host de Docker, ya sea Linux o Windows. Todos los microservicios relacionados que quiera ejecutar y probar juntos en una solución deberán ejecutarse en la misma plataforma de contenedor.

* Su elección de arquitectura de aplicación es **Microservicios en contenedores**.
    - Su elección de implementación de .NET debería ser *.NET Core*.
    - Su elección de plataforma de contenedor puede ser *Contenedores de Linux* o *Contenedores de Windows*.
* Su elección de arquitectura de aplicación es una **aplicación monolítica**.
    - Su elección de implementación de .NET puede ser *.NET Core* o *.NET Framework*.
    - Si ha elegido *.NET Core*, su elección de plataforma de contenedor puede ser *Contenedores de Linux* o *Contenedores de Windows*.
    - Si ha elegido *.NET Framework*, su elección de plataforma de contenedor debe ser *Contenedores de Windows*.
* Su aplicación es un **nuevo desarrollo basado en contenedor ("green-field")**.
    - Su elección de implementación de .NET debería ser *.NET Core*.
    - Su elección de plataforma de contenedor puede ser *Contenedores de Linux* o *Contenedores de Windows*.
* Su aplicación es una **migración de aplicación heredada de Windows Server ("brown-field") a contenedores**
    - Su elección de implementación de .NET es *.NET Framework* en función de la dependencia de marco.
    - Su elección de plataforma de contenedor debe ser *Contenedores de Windows* debido a la dependencia de .NET Framework.
* El objetivo de diseño de su aplicación es el **mejor rendimiento y escalabilidad**.
    - Su elección de implementación de .NET debería ser *.NET Core*.
    - Su elección de plataforma de contenedor puede ser *Contenedores de Linux* o *Contenedores de Windows*.
* Compila la aplicación mediante **ASP.NET Core**.
    - Su elección de implementación de .NET debería ser *.NET Core*.
    - Puede usar la implementación de *.NET Framework* si tiene otras dependencias de marco.
    - Si ha elegido *.NET Core*, su elección de plataforma de contenedor puede ser *Contenedores de Linux* o *Contenedores de Windows*.
    - Si ha elegido *.NET Framework*, su elección de plataforma de contenedor debe ser *Contenedores de Windows*.
* Compila la aplicación mediante **ASP.NET 4 (MVC 5, Web API 2 y Web Forms)**.
    - Su elección de implementación de .NET es *.NET Framework* en función de la dependencia de marco.
    - Su elección de plataforma de contenedor debe ser *Contenedores de Windows* debido a la dependencia de .NET Framework.
* Su aplicación usa **servicios de SignalR**.
    - Su elección de implementación de .NET puede ser *.NET Framework* o *.NET Core 2.1 (cuando se publique) o una versión posterior*.
    - Su elección de plataforma de contenedor debe ser *Contenedores de Windows* si eligió la implementación de SignalR en .NET Framework.
    - Su elección de plataforma de contenedor puede ser Contenedores de Linux o Contenedores de Windows si eligió la implementación de SignalR en .NET Core 2.1 o una versión posterior (cuando se publique).  
    - Cuando los **servicios de SignalR** se ejecutan en *.NET Core*, puede usar *contenedores de Linux o de Windows*.
* Su aplicación usa **WCF, WF y otros marcos heredados**.
    - Su elección de implementación de .NET es *.NET Framework* o *.NET Core (en la hoja de ruta para una versión futura)*.
    - Su elección de plataforma de contenedor debe ser *Contenedores de Windows* debido a la dependencia de .NET Framework.
* Su aplicación comporta el **consumo de servicios de Azure**.
    - Su elección de implementación de .NET es *.NET Framework* o *.NET Core (con el tiempo, todos los servicios de Azure proporcionarán SDK de cliente para .NET Core)*.
    - Su elección de plataforma de contenedor debe ser *Contenedores de Windows* si usa API de cliente de .NET Framework.
    - Si usa API de cliente disponibles para *.NET Core*, también puede elegir los *contenedores de Linux o los contenedores de Windows*.

>[!div class="step-by-step"]
[Anterior](net-framework-container-scenarios.md)
[Siguiente](net-container-os-targets.md)
