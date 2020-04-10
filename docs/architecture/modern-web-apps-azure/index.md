---
title: Diseño de aplicaciones web modernas con ASP.NET Core y Azure
description: Es una guía en la que se proporcionan instrucciones de un extremo a otro sobre cómo compilar aplicaciones web monolíticas con ASP.NET Core y Azure.
author: ardalis
ms.author: wiwagn
ms.date: 12/4/2019
ms.openlocfilehash: 18449ea02b7f9e89744a0f3088f80b7a51a807da
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987899"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>Diseño de aplicaciones web modernas con ASP.NET Core y Azure

![Imagen de portada de la guía Diseño de aplicaciones web modernas.](./media/index/web-application-guide-cover-image.png)

**EDICIÓN v3.1**: actualizada a ASP.NET Core 3.1

PUBLICADO POR

Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio

División de Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2020 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.

Mac y macOS son marcas comerciales de Apple Inc.

El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

Autor:

> **Steve "ardalis" Smith**: instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)

Editores:

> **Maira Wenzel**

## <a name="introduction"></a>Introducción

.NET Core y ASP.NET Core ofrecen varias ventajas con respecto al desarrollo tradicional con .NET. Debe usar .NET Core para las aplicaciones de servidor si algunos o todos los elementos siguientes son importantes para el éxito de su aplicación:

- Compatibilidad entre plataformas.

- Uso de microservicios.

- Uso de contenedores de Docker.

- Requisitos elevados de rendimiento y escalabilidad.

- Control de versiones en paralelo de versiones de .NET por aplicación en el mismo servidor.

Las aplicaciones tradicionales de .NET son compatibles con muchos de estos requisitos, pero ASP.NET Core y .NET Core se han optimizado para ofrecer una compatibilidad mejorada para los escenarios anteriores.

Cada vez más organizaciones deciden hospedar sus aplicaciones web en la nube con servicios como Microsoft Azure. Considere la posibilidad de hospedar su aplicación en la nube si los siguientes elementos son importantes para la aplicación o la organización:

- Inversión reducida en costos de centros de datos (hardware, software, espacio, utilidades, administración de servidores, etc.).

- Precios flexibles (pago en función del uso, y no por la capacidad inactiva).

- Confiabilidad extrema.

- Movilidad mejorada de la aplicación; modificación sencilla de dónde y cómo implementar la aplicación.

- Capacidad flexible; escalado o reducción vertical en función de las necesidades reales.

La compilación de aplicaciones web con ASP.NET Core, hospedadas en Azure, ofrece muchas ventajas competitivas con respecto a las alternativas tradicionales. Se ha optimizado ASP.NET Core para escenarios de hospedaje en la nube y prácticas de desarrollo de aplicaciones web modernas. En esta guía se ofrece información sobre cómo diseñar aplicaciones con ASP.NET Core para sacar el máximo provecho de estas funcionalidades.

## <a name="purpose"></a>Propósito

En esta guía se proporcionan instrucciones integrales sobre cómo compilar aplicaciones web *monolíticas* con ASP.NET Core y Azure. En este contexto, "monolíticas" hace referencia al hecho de que estas aplicaciones se implementan como una sola unidad, no como una colección de aplicaciones y servicios que interactúan.

Esta guía complementa los microservicios de .NET [" _. Arquitectura para aplicaciones .NET en contenedor_"](../microservices/index.md) más centrada en Docker, los microservicios y la implementación de contenedores para hospedar aplicaciones empresariales.

### <a name="net-microservices-architecture-for-containerized-net-applications"></a>Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor

- **Libro electrónico**  
  <https://aka.ms/MicroservicesEbook>
- **Aplicación de ejemplo**  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Los destinatarios de esta guía son principalmente desarrolladores, jefes de desarrollo y arquitectos interesados en crear aplicaciones web modernas con tecnologías y servicios de Microsoft en la nube.

Otros destinatarios secundarios son los responsables de tomar decisiones técnicas que ya están familiarizados con ASP.NET o Azure y que buscan información sobre si tiene sentido actualizar a ASP.NET Core para los proyectos nuevos o existentes.

## <a name="how-you-can-use-this-guide"></a>Cómo leer esta guía

Esta guía se ha comprimido en un documento relativamente pequeño que se centra en la creación de aplicaciones web con modernas tecnologías de .NET y Microsoft Azure. Por lo tanto, se puede leer completa para proporcionar una base de conocimiento sobre estas aplicaciones y sus consideraciones técnicas. La guía, junto con su aplicación de ejemplo, también puede servir como punto inicial o referencia. Use la aplicación de ejemplo asociada como una plantilla para las aplicaciones propias o para consultar cómo se pueden organizar los componentes de la aplicación. Consulte los principios y la cobertura de la arquitectura, las opciones tecnológicas y las consideraciones para la toma de decisiones de esta guía a la hora de sopesar estas opciones para su propia aplicación.

No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades. El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología permite garantizar una aplicación coherente de las prácticas y los patrones de diseño.

## <a name="references"></a>Referencias

- **Selección entre .NET Core y .NET Framework para aplicaciones de servidor**  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[Siguiente](modern-web-applications-characteristics.md)
