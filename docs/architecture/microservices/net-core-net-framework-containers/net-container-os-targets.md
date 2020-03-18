---
title: Selección del sistema operativo de destino con contenedores de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección del sistema operativo de destino con contenedores de .NET
ms.date: 01/30/2020
ms.openlocfilehash: a09e3981ece478a9795c0f27acc98d604864cdd5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501861"
---
# <a name="what-os-to-target-with-net-containers"></a>Selección del sistema operativo de destino con contenedores de .NET

Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe escoger un sistema operativo de destino específico y versiones específicas según el marco que utilice.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web autohospedado, como Kestrel, en Nano Server) que .NET Framework o .NET Core, respectivamente, podrían necesitar.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

En la Figura 3-1 se puede ver la posible versión de sistema operativo en función de la versión de .NET Framework que se utilice.

![Diagrama que muestra qué sistema operativo se debe usar con cada contenedor de .NET.](./media/net-container-os-targets/targeting-operating-systems.png)

**Figura 3-1.** Sistemas operativos de destino en función de las versiones de .NET Framework

Al implementar aplicaciones heredadas de .NET Framework, tiene que elegir como destino Windows Server Core, que es compatible con aplicaciones heredadas e IIS, pero tiene una imagen más grande. Al implementar aplicaciones de .NET Core, puede tener como destino Windows Nano Server, que está optimizado para la nube, usa Kestrel y es más pequeño y se inicia más rápido. También puede tener como destino Linux, con compatibilidad con Debian, Alpine y otros. También usa Kestrel, que es más pequeño y se inicia más rápido.

También puede crear su propia imagen de Docker en los casos en que quiera utilizar una distribución de Linux diferente o que quiera una imagen con las versiones no proporcionadas por Microsoft. Por ejemplo, puede crear una imagen con ASP.NET Core ejecutándose en los tradicionales .NET Framework y Windows Server Core, que no sería un escenario tan habitual para Docker.

> [!IMPORTANT]
> Al usar imágenes de Windows Server Core, es posible que falten algunos archivos DLL cuando se comparan con Imágenes de Windows completas. Es posible que pueda resolver este problema mediante la creación de una imagen de Server Core personalizada, agregando los archivos que faltan en el momento de la compilación de la imagen, tal como se ja mencionado en este [comentario de GitHub](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).

Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión dependiendo de la etiqueta que utilice, como en los ejemplos siguientes:

| Imagen | Comentarios |
|-------|----------|
| mcr.microsoft.com/dotnet/core/runtime:3.1 | Arquitectura múltiple de .NET Core 3.1: es compatible con Linux y Windows Nano Server en función del host de Docker. |
| mcr.microsoft.com/dotnet/core/aspnet:3.1 | Arquitectura múltiple de ASP.NET Core 3.1: es compatible con Linux y Windows Nano Server en función del host de Docker. <br/> La imagen de aspnetcore tiene algunas optimizaciones para ASP.NET Core. |
| mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim | Solo entorno de ejecución de .NET Core 3.1 en una distribución de Linux Debian |
| mcr.microsoft.com/dotnet/core/aspnet:3.1-nanoserver-1809 | Solo entorno de ejecución de .NET Core 3.1 en Windows Nano Server (Windows Server 1809) |

## <a name="additional-resources"></a>Recursos adicionales

- **Se produce un error en BitmapDecoder debido a que falta WindowsCodecsExt.dll (incidencia de GitHub)** .  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> [Anterior](container-framework-choice-factors.md)
> [Siguiente](official-net-docker-images.md)
