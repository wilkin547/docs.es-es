---
title: Instrucciones generales
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Instrucciones generales
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a>Instrucciones generales

En esta sección se proporciona un resumen de cuándo se debe elegir .NET Core o .NET Framework. Se proporcionan más detalles acerca de estas opciones en las secciones siguientes.

Debe utilizar .NET Core, con Linux o contenedores de Windows para la aplicación de servidor en contenedores de Docker cuando:

-   Tenga necesidades multiplataforma. Por ejemplo, desea utilizar contenedores de Windows y Linux.

-   La arquitectura de la aplicación se basa en microservicios.

-   Debe iniciar contenedores rápido y desea una pequeña superficie por contenedor para lograr una mejor densidad o más contenedores por unidad de hardware con el fin de reducir los costos.

En resumen, al crear nuevas aplicaciones de .NET en contenedores, se debe considerar .NET Core como la opción predeterminada. Tiene muchas ventajas y mejor se adapte a la filosofía de contenedores y el estilo de trabajo.

Otra ventaja adicional del uso de .NET Core es que puede ejecutar en paralelo versiones de .NET para aplicaciones en el mismo equipo. Esta ventaja es más importante para servidores o máquinas virtuales que no usan contenedores, porque contenedores aislar las versiones de .NET que necesita la aplicación. (Siempre que sean compatibles con el sistema operativo subyacente.)

Debe utilizar .NET Framework, con los contenedores de Windows, para la aplicación de servidor en contenedores de Docker cuando:

-   Actualmente, la aplicación utiliza .NET Framework y tiene fuertes dependencias en Windows.

-   Debe usar las API de Windows que no son compatibles con .NET Core.

-   Debe usar las bibliotecas .NET de terceros o paquetes de NuGet que no están disponibles para .NET Core.

Uso de .NET Framework en Docker puede mejorar sus experiencias de implementación minimizar los problemas de implementación. Esto [ *escenario "Levantar y mover"* ](https://aka.ms/liftandshiftwithcontainersebook) es importante para containerizing aplicaciones heredadas que se desarrollaron originalmente con .NET Framework tradicionales, como formularios Web Forms de ASP.NET, MVC web WCF (o aplicaciones Servicios de Windows Communication Foundation).

### <a name="additional-resources"></a>Recursos adicionales

-   **libro electrónico: modernizar las aplicaciones existentes de .NET Framework con contenedores de Windows y Azure**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **Aplicaciones de ejemplo: modernización de las aplicaciones web ASP.NET heredadas mediante el uso de contenedores de Windows**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (net-core-contenedor-scenarios.md)
