---
title: Diseño de aplicaciones web modernas con ASP.NET Core y Azure
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Introducción
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 280f7af11d71739b39e86299a5e1223bb6664f4c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>Diseño de aplicaciones web modernas con ASP.NET Core y Azure

![imagen de portada](./media/cover.jpg)


.NET Core y ASP.NET Core ofrecen varias ventajas con respecto al desarrollo tradicional con .NET. Debe usar .NET Core para las aplicaciones de servidor si algunos o todos los elementos siguientes son importantes para el éxito de su aplicación:

-   Compatibilidad entre plataformas

-   Uso de microservicios

-   Uso de contenedores de Docker

-   Requisitos elevados de rendimiento y escalabilidad

-   Control de versiones en paralelo de versiones de .NET por aplicación en el mismo servidor

Las aplicaciones tradicionales de .NET son compatibles con estos requisitos, pero ASP.NET Core y .NET Core se han optimizado para ofrecer una compatibilidad mejorada para los escenarios anteriores.

Cada vez más organizaciones deciden hospedar sus aplicaciones web en la nube con servicios como Microsoft Azure. Considere la posibilidad de hospedar su aplicación en la nube si los siguientes elementos son importantes para la aplicación o la organización:

-   Inversión reducida en costos de centros de datos (hardware, software, espacio, utilidades, etc.)

-   Precios flexibles (pago en función del uso, y no por la capacidad inactiva)

-   Confiabilidad extrema

-   Movilidad mejorada de la aplicación; modificación sencilla de dónde y cómo implementar la aplicación

-   Capacidad flexible; escalado o reducción vertical en función de las necesidades reales

La compilación de aplicaciones web con ASP.NET Core, hospedadas en Microsoft Azure, ofrece numerosas ventajas competitivas con respecto a las alternativas tradicionales. Se ha optimizado ASP.NET Core para escenarios de hospedaje en la nube y prácticas de desarrollo de aplicaciones web modernas. En esta guía se ofrece información sobre cómo diseñar aplicaciones con ASP.NET Core para sacar el máximo provecho de estas funcionalidades.

## <a name="purpose"></a>Propósito

En esta guía se proporcionan instrucciones de un extremo a otro sobre cómo compilar aplicaciones web monolíticas con ASP.NET Core y Azure.

Esta guía es complementaria a "*Diseño y desarrollo de aplicaciones basadas en contenedores y microservicios con .NET*", que se centra más en Docker, los microservicios y el desarrollo de contenedores para hospedar aplicaciones empresariales.

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a>Diseño y desarrollo de aplicaciones basadas en contenedores y microservicios con .NET
> - **Libro electrónico**  
> <http://aka.ms/MicroservicesEbook>
> - **Aplicación de ejemplo**  
> <http://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Los destinatarios de esta guía son principalmente desarrolladores, jefes de desarrollo y arquitectos interesados en crear aplicaciones web modernas con tecnologías y servicios de Microsoft en la nube.

Otros destinatarios secundarios son los responsables de tomar decisiones técnicas que ya están familiarizados con ASP.NET o Azure y que buscan información sobre si tiene sentido actualizar a ASP.NET Core para los proyectos nuevos o existentes.

## <a name="how-you-can-use-this-guide"></a>Cómo leer esta guía

Esta guía se ha comprimido en un documento relativamente pequeño que se centra en la creación de aplicaciones web con modernas tecnologías de .NET y Microsoft Azure. Por lo tanto, se puede leer completa para proporcionar una base de conocimiento sobre estas aplicaciones y sus consideraciones técnicas. La guía, junto con su aplicación de ejemplo, también puede servir como punto inicial o referencia. Use la aplicación de ejemplo asociada como una plantilla para las aplicaciones propias o para consultar cómo se pueden organizar los componentes de la aplicación. Consulte los principios y la cobertura de la arquitectura, las opciones tecnológicas y las consideraciones para la toma de decisiones de esta guía a la hora de sopesar estas opciones para su propia aplicación.

No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades. El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología ayudará a garantizar una aplicación coherente de las prácticas y los patrones de diseño.

## <a name="references"></a>Referencias
- **Selección entre .NET Core y .NET Framework para aplicaciones de servidor**  
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
[Siguiente] (modern-web-applications-characteristics.md)
