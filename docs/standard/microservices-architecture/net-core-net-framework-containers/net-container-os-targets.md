---
title: "¿Qué sistema operativo al destino con contenedores de .NET"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | ¿Qué sistema operativo al destino con contenedores de .NET"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a>¿Qué sistema operativo al destino con contenedores de .NET

Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe tener como destino un sistema operativo específico y las versiones específicas según el marco de trabajo que usa. 

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web hospedado por sí mismo como Kestrel en Nano Server) que podrían ser necesarios en .NET Framework o .NET Core, respectivamente. 

Para Linux, varias distribuciones están disponibles y sea compatible con imágenes de Docker .NET oficiales (por ejemplo, Debian).

En la figura 3-1 puede ver la versión del SO posibles dependiendo de .NET framework que utiliza.

![](./media/image1.png)

**Figura 3-1.** Sistemas operativos en función de las versiones de .NET framework de destino

También puede crear su propia imagen de Docker en los casos donde desea utilizar una distribución de Linux diferente o donde quiere una imagen con las versiones no proporcionadas por Microsoft. Por ejemplo, podría crear una imagen con ASP.NET Core que se ejecutan en .NET Framework y Windows Server Core, que es un escenario no tan comunes para Docker tradicional.

Cuando se agrega el nombre de imagen en el archivo Dockerfile, puede seleccionar el sistema operativo y la versión en función de la etiqueta que se utiliza, como en los ejemplos siguientes:

-   Microsoft /**dotnet:2.0.0-tiempo de ejecución-jessie**

        .NET Core 2.0 runtime-only on Linux

-   Microsoft /**dotnet:2.0.0-tiempo de ejecución-nanoserver-1709** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   Microsoft /**aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[Anterior] (contenedor-framework-elección-factors.md) [siguiente] (oficial-net-docker-images.md)
