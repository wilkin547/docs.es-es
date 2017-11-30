---
title: "Tabla de decisiones. Versiones de .NET Framework que se usará para Docker"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Tabla de decisiones, versiones de .NET Framework que se usará para Docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4889662c4d887bebd320389e3ced6aae1c93133b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabla de decisiones: versiones de .NET Framework que se usará para Docker

A continuación, resumen si desea utilizar los contenedores de .NET Framework o .NET Core y Windows o Linux. Recuerde que para los contenedores de Linux, necesita los hosts basados en Linux Docker (máquinas virtuales o servidores) y para los contenedores de Windows necesita Windows Server en función de hosts de Docker (máquinas virtuales o servidores).

Hay varias características de la aplicación que afectan a su decisión. Debería sopesar la importancia de estas características cuando tome la decisión.

> [!IMPORTANT]
> Los equipos de desarrollo ejecutarán un host Docker, Linux o Windows. Microservicios relacionados que desea ejecutar y probar juntos en una única solución será necesario para que se ejecute en la misma plataforma de contenedor.

* La elección de la arquitectura de aplicación es **Microservicios en contenedores**.
    - Debe ser la opción de implementación de .NET *.NET Core*.
    - Su elección de plataforma de contenedor puede ser *contenedores Linux* o *contenedores de Windows*.
* La elección de la arquitectura de aplicación es un **aplicación monolítico**.
    - La opción de implementación de .NET puede ser *.NET Core* o *.NET Framework*.
    - Si ha elegido *.NET Core*, su elección de plataforma de contenedor puede ser *contenedores Linux* o *contenedores de Windows*.
    - Si ha elegido *.NET Framework*, su elección de plataforma de contenedor debe ser *contenedores de Windows*.
* La aplicación es un **nuevo desarrollo basado en el contenedor ("verde-field")**.
    - Debe ser la opción de implementación de .NET *.NET Core*.
    - Su elección de plataforma de contenedor puede ser *contenedores Linux* o *contenedores de Windows*.
* La aplicación es un **migración de aplicaciones heredadas ("brown-field") de Windows Server para contenedores**
    - La elección de la implementación de .NET es *.NET Framework* en función de la dependencia del marco.
    - Su elección de plataforma de contenedor debe ser *contenedores de Windows* debido a la dependencia de .NET Framework.
* Objetivo del diseño de su aplicación es **mejor rendimiento y escalabilidad**.
    - Debe ser la opción de implementación de .NET *.NET Core*.
    - Su elección de plataforma de contenedor puede ser *contenedores Linux* o *contenedores de Windows*.
* Compila la aplicación mediante **ASP.NET Core**.
    - Debe ser la opción de implementación de .NET *.NET Core*.
    - Puede usar el *.NET Framework* implementación, si tiene otras dependencias del marco.
    - Si ha elegido *.NET Core*, su elección de plataforma de contenedor puede ser *contenedores Linux* o *contenedores de Windows*.
    - Si ha elegido *.NET Framework*, su elección de plataforma de contenedor debe ser *contenedores de Windows*.
* Compila la aplicación mediante **4 de ASP.NET (MVC 5, Web API 2 y formularios Web Forms)**.
    - La elección de la implementación de .NET es *.NET Framework* en función de la dependencia del marco.
    - Su elección de plataforma de contenedor debe ser *contenedores de Windows* debido a la dependencia de .NET Framework.
* La aplicación usa **servicios SignalR**.
    - La opción de implementación de .NET puede ser *.NET Framework*, o *.NET Core 2.1 (cuando se publique) o una versión posterior*.
    - Su elección de plataforma de contenedor debe ser *contenedores de Windows* si eligió la implementación de SignalR en .NET Framework.
    - Su elección de plataforma de contenedor puede ser contenedores de Linux o contenedores de Windows si ha elegido la implementación de SignalR en .NET Core 2.1 o posterior (cuando se publique).  
    - Cuando **servicios SignalR** ejecutar en *.NET Core*, puede usar *Linux contenedores o los contenedores de Windows*.
* La aplicación usa **WCF, WF y otros marcos de trabajo heredados**.
    - La elección de la implementación de .NET es *.NET Framework*, o *.NET Core (en el plan para una versión futura)*.
    - Su elección de plataforma de contenedor debe ser *contenedores de Windows* debido a la dependencia de .NET Framework.
* La aplicación implica **servicios de consumo de Azure**.
    - La elección de la implementación de .NET es *.NET Framework*, o *.NET Core (servicios de Azure finalmente todos los proporcionará SDK de cliente para .NET Core)*.
    - Su elección de plataforma de contenedor debe ser *contenedores de Windows* si usa las API de cliente de .NET Framework.
    - Si utiliza el cliente API disponibles para *.NET Core*, también puede elegir entre *Linux contenedores y los contenedores de Windows*.

>[!div class="step-by-step"]
[Anterior] (net-framework-contenedor-scenarios.md) [siguiente] (net-contenedor-os-targets.md)
