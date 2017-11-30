---
title: "Cuándo se debe elegir .NET Core para contenedores de Docker"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo se debe elegir .NET Core para contenedores de Docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7e2322bab7937c41d4659fefef11c8937d5eae7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Cuándo se debe elegir .NET Core para contenedores de Docker

La naturaleza modularidad y ligera de .NET Core resulta perfecta para contenedores. Al implementar e iniciar un contenedor, la imagen es mucho menor con .NET Core que con .NET Framework. En cambio, para usar .NET Framework para un contenedor, debe basar la imagen en la imagen de Windows Server Core, que es mucho mayor que en el Windows Nano Server o las imágenes de Linux que usan para .NET Core.

Además, .NET Core es multiplataforma, por lo que puede implementar aplicaciones de servidor con imágenes de contenedor de Linux o Windows. Sin embargo, si está utilizando tradicional .NET Framework, solo se pueden implementar imágenes basadas en Windows Server Core.

La siguiente es una explicación más detallada sobre por qué elegir .NET Core.

## <a name="developing-and-deploying-cross-platform"></a>Desarrollar e implementar todas las plataformas

Obviamente, si su objetivo es tener una aplicación (aplicación web o servicio) que se puede ejecutar en varias plataformas compatibles con Docker (Linux y Windows), la opción adecuada es .NET Core, dado que .NET Framework solo es compatible con Windows.

.NET core también admite macOS como una plataforma de desarrollo. Sin embargo, al implementar contenedores en un host Docker, que hospedan (actualmente) debe basarse en Linux o Windows. Por ejemplo, en un entorno de desarrollo, podría utilizar una VM de Linux con un equipo Mac.

[Visual Studio](https://www.visualstudio.com/) proporciona un entorno de desarrollo integrado (IDE) de Windows y admite el desarrollo de Docker. 

[Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/) es un IDE, evolución de Xamarin Studio, que se ejecuta en Mac OS y es compatible con Docker desde mediados de 2017.

También puede usar [código de Visual Studio](https://code.visualstudio.com/) (VS Code) en Mac OS, Linux y Windows. Código de VS es totalmente compatible con .NET Core, que incluye IntelliSense y la depuración. Porque el código de VS es un editor ligero, puede usar para desarrollar aplicaciones en contenedores en el Mac, junto con la CLI de Docker y la [herramientas de interfaz de línea de comandos (CLI) de .NET Core](https://docs.microsoft.com/dotnet/core/tools/?tabs=netcore2x). También puede centrarse en .NET Core con editores de terceros más como texto fundamentales, Emacs, vi y el proyecto de OmniSharp de código abierto, que proporciona compatibilidad con IntelliSense para los lenguajes de. NET. Además de los editores e IDE, puede utilizar la CLI de núcleo de .NET para todas las plataformas admitidas.

## <a name="using-containers-for-new-green-field-projects"></a>Uso de contenedores para los nuevos proyectos ("verde-field")

Los contenedores se usan normalmente junto con una arquitectura microservicios, aunque también puede usarse para que incluya las aplicaciones web o servicios que seguir cualquier modelo de arquitectura. Puede utilizar .NET Framework en los contenedores de Windows, pero la modularidad y naturaleza ligera de .NET Core resulta perfecta para crear arquitecturas de contenedores y microservicios. Al crear e implementar un contenedor, la imagen es mucho menor con .NET Core que con .NET Framework.

## <a name="creating-and-deploying-microservices-on-containers"></a>Creación e implementación de microservicios en contenedores

Podría utilizar la tradicional de .NET Framework para la creación de aplicaciones basadas en microservicios (sin contenedores) mediante el uso de procesos sin formato. De este modo, dado que .NET Framework ya está instalada y se comparte entre procesos, procesos son luz y rápidas para iniciar. Sin embargo, si usas contenedores, también se basa la imagen para .NET Framework tradicionales en Windows Server Core y sea demasiado elevada para un enfoque microservicios en contenedores.

En cambio, .NET Core son los mejores candidatos si están adoptando un sistema orientados a microservicios que se basa en los contenedores, dado que .NET Core es ligero. Además, sus imágenes de contenedor relacionados, la imagen de Linux o la imagen de Windows Nano, son eficiente y pequeños que realiza la luz de los contenedores y rápido para iniciar.

Un microservicio está pensado para ser lo más pequeño posible: para usar un claro cuando girando, tener una superficie pequeña, tener un pequeño limitado contexto, para representar un área pequeña de intereses y para poder iniciar y detener rápida. Para esos requisitos, deberá utilizar las imágenes de contenedor pequeña y rápida de crear similar a la imagen de contenedor de .NET Core.

Una arquitectura de microservicios también permite combinar tecnologías en un límite de servicio. Esto permite una migración gradual a .NET Core para microservicios nueva que funcionan junto con otros microservicios o con los servicios desarrollados con Node.js, Python, Java, GoLang u otras tecnologías.

## <a name="deploying-high-density-in-scalable-systems"></a>Implementación de alta densidad en sistemas escalables

Cuando un sistema basado en el contenedor necesita la mejor densidad posible, la granularidad y el rendimiento, .NET Core y ASP.NET Core son las mejores opciones. ASP.NET Core es hasta diez veces más rápido que ASP.NET en .NET Framework tradicionales, y lo genera otras tecnologías más habituales del sector para microservicios como servlets de Java, Go y Node.js.

Esto es especialmente importante para las arquitecturas de microservicios, donde pueda haber cientos de microservicios (contenedores) ejecutando. Con imágenes de ASP.NET Core (basadas en el tiempo de ejecución de .NET Core) en Linux o Windows Nano, puede ejecutar el sistema con un número mucho menor de los servidores o máquinas virtuales, en última instancia, guardar los costos de infraestructura y de hospedaje.


>[!div class="step-by-step"]
[Anterior] (general-guidance.md) [siguiente] (net framework-contenedor scenarios.md)
