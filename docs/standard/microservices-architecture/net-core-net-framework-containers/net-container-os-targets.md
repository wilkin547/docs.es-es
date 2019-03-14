---
title: Selección del sistema operativo de destino con contenedores de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección del sistema operativo de destino con contenedores de .NET
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 9e1d07e48d88376efb5fbdbdadc999c8dcd5082d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374913"
---
# <a name="what-os-to-target-with-net-containers"></a>Selección del sistema operativo de destino con contenedores de .NET

Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe escoger un sistema operativo de destino específico y versiones específicas según el marco que utilice.

Para Windows, puede usar Windows Server Core o Nano Server de Windows. Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web autohospedado, como Kestrel, en Nano Server) que .NET Framework o .NET Core, respectivamente, podrían necesitar.

Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).

En la Figura 3-1 se puede ver la posible versión de sistema operativo en función de la versión de .NET Framework que se utilice.

![Al implementar aplicaciones heredadas de .NET Framework que tienen como destino Windows Server Core, compatible con aplicaciones heredadas e IIS, tiene una imagen más grande. Al implementar aplicaciones de .NET Core, puede tener como destino Windows Nano Server, que está optimizado para la nube, usa Kestrel y es más pequeño y se inicia más rápido. También puede tener como destino Linux, con compatibilidad con Debian, Alpine y otros. También usa Kestrel y es más pequeño y se inicia más rápido.](./media/image1.png)

**Figura 3-1.** Sistemas operativos de destino en función de las versiones de .NET Framework

También puede crear su propia imagen de Docker en los casos en que quiera utilizar una distribución de Linux diferente o que quiera una imagen con las versiones no proporcionadas por Microsoft. Por ejemplo, puede crear una imagen con ASP.NET Core ejecutándose en los tradicionales .NET Framework y Windows Server Core, que no sería un escenario tan habitual para Docker.

Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión dependiendo de la etiqueta que utilice, como en los ejemplos siguientes:

<table>
<thead>
<tr class="header">
<th>Imagen</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr>
<td>microsoft/dotnet:2.2-runtime</td>
<td>Arquitectura múltiple de .NET Core 2.2: es compatible con Linux y Windows Nano Server en función del host de Docker.</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.2-aspnetcore-runtime</td>
<td><p>Arquitectura múltiple de .NET Core 2.2: es compatible con Linux y Windows Nano Server en función del host de Docker.</p>
<p>La imagen de aspnetcore tiene algunas optimizaciones para ASP.NET Core.</p></td>
</tr>
<tr class="even">
<td>microsoft/dotnet:2.2-aspnetcore-runtime-alpine</td>
<td>.NET Core 2.2 solo en tiempo de ejecución en una distribución de Alpine Linux</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803</td>
<td>.NET Core 2.2 solo en tiempo de ejecución en Windows Nano Server (Windows Server 1803)</td>
</tr>
</tbody>
</table>

> [!div class="step-by-step"]
> [Anterior](container-framework-choice-factors.md)
> [Siguiente](official-net-docker-images.md)