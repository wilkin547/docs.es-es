---
title: Cuándo elegir .NET Core para contenedores de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Cuándo elegir .NET Core para contenedores de Docker
ms.date: 01/30/2020
ms.openlocfilehash: 8d25cf58c48aac137ba91300515bdb72a7eb648d
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507278"
---
# <a name="when-to-choose-net-core-for-docker-containers"></a>Cuándo elegir .NET Core para contenedores de Docker

La naturaleza modular y ligera de .NET Core resulta perfecta para contenedores. Al implementar e iniciar un contenedor, su imagen es mucho más pequeña con .NET Core que con .NET Framework. En cambio, al usar .NET Framework para un contenedor, debe basar su imagen en la imagen de Windows Server Core, que es mucho más pesada que las imágenes de Nano Server de Windows o Linux que se usan para .NET Core.

Además, .NET Core es multiplataforma, por lo que puede implementar aplicaciones de servidor con imágenes de contenedor de Linux o Windows. Pero, si está utilizando el tradicional .NET Framework, solo puede implementar imágenes basadas en Windows Server Core.

A continuación, le ofrecemos una explicación más detallada sobre por qué elegir .NET Core.

## <a name="developing-and-deploying-cross-platform"></a>Desarrollo e implementación multiplataforma

Obviamente, si su objetivo es tener una aplicación (servicio o aplicación web) que se pueda ejecutar en diferentes plataformas compatibles con Docker (Linux y Windows), la opción adecuada es .NET Core, puesto que .NET Framework solo es compatible con Windows.

.NET Core también admite macOS como plataforma de desarrollo. Pero, al implementar contenedores en un host Docker, el host debe estar (actualmente) basado en Linux o Windows. Por ejemplo, en un entorno de desarrollo, podría utilizar una máquina virtual Linux que se ejecutara en un equipo Mac.

[Visual Studio](https://www.visualstudio.com/vs/) proporciona un entorno de desarrollo integrado (IDE) para Windows y admite el desarrollo en Docker.

[Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/) es un IDE, una evolución de Xamarin Studio, que se ejecuta en macOS y admite el desarrollo de aplicaciones basadas en Docker. Debe ser la opción preferida para los desarrolladores que trabajan en equipos Mac y que también deseen usar un IDE eficaz.

También puede usar [Visual Studio Code](https://code.visualstudio.com/) en macOS, Linux y Windows. Visual Studio Code es totalmente compatible con .NET Core, incluidos IntelliSense y la depuración. Como VS Code es un editor ligero, puede usarlo para desarrollar aplicaciones en contenedor en la máquina junto con la interfaz de la línea de comandos de Docker y la [CLI de .NET Core](../../../core/tools/index.md). También puede utilizar .NET Core con la mayoría de editores de terceros, como Sublime, Emacs, vi y el proyecto OmniSharp de código abierto, que también es compatible con IntelliSense.

Además de los editores e IDE, puede utilizar la [CLI de .NET Core](../../../core/tools/index.md) en todas las plataformas admitidas.

## <a name="using-containers-for-new-green-field-projects"></a>Uso de contenedores para nuevos proyectos (green field)

Normalmente los contenedores se usan en combinación con una arquitectura de microservicios, aunque también se pueden usar para contener servicios o aplicaciones web que siguen cualquier patrón de arquitectura. Aunque puede usar .NET Framework en contenedores de Windows, la modularidad y ligereza de .NET Core lo convierten en la opción perfecta para los contenedores y las arquitecturas de microservicio. Al crear e implementar un contenedor, su imagen es mucho más pequeña con .NET Core que con .NET Framework.

## <a name="create-and-deploy-microservices-on-containers"></a>Creación e implementación de microservicios en contenedores

Puede utilizar el tradicional .NET Framework para crear aplicaciones basadas en microservicios (sin contenedores) mediante el uso de procesos sin formato. De este modo, como .NET Framework ya está instalado y se comparte entre procesos, los procesos son ligeros y rápidos al iniciarse. Pero, si usa contenedores, la imagen del tradicional .NET Framework también se basa en Windows Server Core y esto hace que sea demasiado pesada para una opción de microservicios en contenedores. Sin embargo, los equipos también han estado buscando oportunidades para mejorar la experiencia de los usuarios de .NET Framework. Recientemente, el tamaño de las [imágenes de contenedor de Windows Server Core se ha reducido un 40 %](https://devblogs.microsoft.com/dotnet/we-made-windows-server-core-container-images-40-smaller).

Por otra parte, .NET Core es la mejor opción si ha adoptado un sistema orientado a microservicios que se basa en contenedores, puesto que .NET Core es ligero. Además, sus imágenes de contenedor relacionadas, ya sean de Linux o de Windows Nano Server, son eficientes y pequeñas, lo que hace que los contenedores sean ligeros y rápidos al iniciarse.

Un microservicio está pensado para ser lo más pequeño posible: que sea ligero al acelerar, que tenga una superficie pequeña, que tenga un pequeño contexto limitado (comprobar DDD, [diseño basado en dominios](https://en.wikipedia.org/wiki/Domain-driven_design)), que represente una pequeña área de problemas y que se pueda iniciar y detener rápidamente. Para cumplir con estos requisitos, le recomendamos que utilice imágenes de contenedor pequeñas y fáciles de ejemplificar, como la imagen de contenedor de .NET Core.

Una arquitectura de microservicios también le permite mezclar tecnologías en un límite de servicio. Esto permite migrar gradualmente a .NET Core microservicios nuevos que funcionan junto con otros microservicios o con servicios desarrollados con Node.js, Python, Java, GoLang u otras tecnologías.

## <a name="deploying-high-density-in-scalable-systems"></a>Implementación de alta densidad en sistemas escalables

Cuando en un sistema basado en contenedores se necesita la mejor densidad, granularidad y rendimiento posibles, .NET Core y ASP.NET Core son las mejores opciones. ASP.NET Core es hasta diez veces más rápido que ASP.NET en el tradicional .NET Framework y lidera otras tecnologías para microservicios populares del sector, como servlets de Java, Go y Node.js.

Esto es especialmente importante para las arquitecturas de microservicios, donde podría tener cientos de microservicios (contenedores) en funcionamiento. Con imágenes de ASP.NET Core (basadas en el tiempo de ejecución de .NET Core) en Linux o Windows Nano, puede ejecutar el sistema con un número mucho menor de servidores o máquinas virtuales, con lo que, en última instancia, ahorra en costos de infraestructura y hospedaje.

>[!div class="step-by-step"]
>[Anterior](general-guidance.md)
>[Siguiente](net-framework-container-scenarios.md)
