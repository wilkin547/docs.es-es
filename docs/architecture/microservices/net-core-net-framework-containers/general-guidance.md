---
title: Orientación general
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Orientación general
ms.date: 01/13/2021
ms.openlocfilehash: 4fd2d936c524cb3e5ae463038eaffe88b459d2bd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98187956"
---
# <a name="general-guidance"></a>Orientación general

En esta sección se proporciona un resumen de cuándo es mejor elegir .NET 5 y cuándo es preferible .NET Framework. Se proporcionan más detalles acerca de estas opciones en las secciones siguientes.

Use .NET 5 con contenedores de Linux o Windows para la aplicación de servidor de Docker en contenedor en los casos siguientes:

- Tenga necesidades multiplataforma. Por ejemplo, si quiere utilizar contenedores de Linux y Windows.

- La arquitectura de la aplicación esté basada en microservicios.

- Necesite iniciar contenedores rápidamente y quiera que una pequeña superficie por contenedor alcance una mejor densidad o más contenedores por unidad de hardware con el fin de reducir costos.

En resumen, al crear nuevas aplicaciones .NET en contenedores, debe optar por .NET 5 como opción predeterminada, ya que esta opción presenta muchas ventajas y es la que mejor se adapta a la filosofía y al estilo de trabajo de los contenedores.

Otra ventaja adicional de usar .NET 5 es que puede ejecutar versiones paralelas de .NET para aplicaciones en la misma máquina. Esta ventaja es más importante para servidores o máquinas virtuales que no utilizan contenedores, porque los contenedores aíslan las versiones de .NET que necesita la aplicación. (Siempre que sean compatibles con el sistema operativo subyacente).

Use .NET Framework para la aplicación de servidor Docker en contenedor cuando:

- La aplicación ya utilice .NET Framework y dependa fuertemente de Windows.

- Es necesario usar API de Windows que no sean compatibles con .NET 5.

- Es necesario usar bibliotecas de .NET de terceros o paquetes NuGet no disponibles para .NET 5.

Utilizar .NET Framework en Docker puede mejorar sus experiencias de implementación minimizando los problemas de implementación. Este [escenario de migración mediante lift-and-shift](https://aka.ms/liftandshiftwithcontainersebook) es importante para aplicaciones en contenedor heredadas que se desarrollaron originalmente con .NET Framework, como formularios web de ASP.NET, aplicaciones web MVC o servicios de WCF (Windows Communication Foundation).

### <a name="additional-resources"></a>Recursos adicionales

- **Libro electrónico: Modernize existing .NET Framework applications with Azure and Windows Containers** (Libro electrónico: Modernización de las aplicaciones .NET Framework existentes con contenedores de Azure y de Windows)  
    <https://aka.ms/liftandshiftwithcontainersebook>

- **Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers** (Aplicaciones de ejemplo: Modernización de aplicaciones web de ASP.NET heredadas mediante contenedores de Windows)  
    <https://aka.ms/eshopmodernizing>

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](net-core-container-scenarios.md)
