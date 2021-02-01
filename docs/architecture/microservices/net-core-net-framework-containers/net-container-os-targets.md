---
title: Selección del sistema operativo de destino con contenedores de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección del sistema operativo de destino con contenedores de .NET
ms.date: 01/13/2021
ms.openlocfilehash: b128a7b98d7f46034a56314bd8cc6b4f5731f121
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957915"
---
# <a name="what-os-to-target-with-net-containers"></a>Selección del sistema operativo de destino con contenedores de .NET

Teniendo en cuenta la diversidad de sistemas operativos que admite Docker y las diferencias entre .NET Framework y .NET 5, debe escoger un sistema operativo de destino específico y versiones concretas según el marco que utilice.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web autohospedado, como Kestrel, en Nano Server) que .NET Framework o .NET 5, respectivamente, podrían necesitar.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

En la figura 3-1, se observa la posible versión del sistema operativo en función de la versión de .NET Framework que se utilice.

![Diagrama que muestra qué sistema operativo se debe usar con cada contenedor de .NET.](./media/net-container-os-targets/targeting-operating-systems.png)

**Figura 3-1.** Sistemas operativos de destino en función de las versiones de .NET Framework

Al implementar aplicaciones heredadas de .NET Framework, tiene que elegir como destino Windows Server Core, que es compatible con aplicaciones heredadas e IIS, pero tiene una imagen más grande. Al implementar aplicaciones de .NET 5, puede tener como destino Windows Nano Server, que está optimizado para la nube, usa Kestrel, es más pequeño y se inicia más rápido. También puede tener como destino Linux, que es compatible con Debian, Alpine y otros. También usa Kestrel, que es más pequeño y se inicia más rápido.

También puede crear su propia imagen de Docker en los casos en que quiera utilizar una distribución de Linux diferente o que quiera una imagen con las versiones no proporcionadas por Microsoft. Por ejemplo, puede crear una imagen con ASP.NET Core ejecutándose en los tradicionales .NET Framework y Windows Server Core, que no sería un escenario tan habitual para Docker.

Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión dependiendo de la etiqueta que utilice, como en los ejemplos siguientes:

| Imagen | Comentarios |
|-------|----------|
| mcr.microsoft.com/dotnet/runtime:5.0 | Arquitectura múltiple de .NET 5: es compatible con Linux y Windows Nano Server en función del host de Docker. |
| mcr.microsoft.com/dotnet/aspnet:5.0 | Arquitectura múltiple de ASP.NET Core 5.0: es compatible con Linux y Windows Nano Server en función del host de Docker. <br/> La imagen de aspnetcore tiene algunas optimizaciones para ASP.NET Core. |
| mcr.microsoft.com/dotnet/aspnet:5.0-buster-slim | Solo entorno de ejecución de .NET 5 en una distribución de Linux Debian |
| mcr.microsoft.com/dotnet/aspnet:5.0-nanoserver-1809 | Solo entorno de ejecución de .NET 5 en Windows Nano Server (Windows Server 1809) |

> [!div class="step-by-step"]
> [Anterior](container-framework-choice-factors.md)
> [Siguiente](official-net-docker-images.md)
