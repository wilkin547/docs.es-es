---
title: Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar contenedores con Windows (basado en Docker estándar)
description: Obtenga información sobre cómo usar PowerShell al trabajar con Docker en contenedores de Windows.
ms.date: 08/06/2020
ms.openlocfilehash: d65538c821a848d83915e715ee3a02990b40e836
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681254"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="0b54f-103">Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar contenedores con Windows (basado en Docker estándar)</span><span class="sxs-lookup"><span data-stu-id="0b54f-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="0b54f-104">Con los [contenedores de Windows](/virtualization/windowscontainers/about/index), puede convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.</span><span class="sxs-lookup"><span data-stu-id="0b54f-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="0b54f-105">Para usar contenedores de Windows, simplemente debe escribir comandos de Windows PowerShell en el archivo Dockerfile, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b54f-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="0b54f-106">En este caso, vamos a usar Windows PowerShell para instalar una imagen base de Windows Server Core, así como IIS.</span><span class="sxs-lookup"><span data-stu-id="0b54f-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="0b54f-107">Del mismo modo, también se pueden usar comandos de Windows PowerShell para configurar componentes adicionales como ASP.NET 4.x tradicional, .NET Framework 4.6 o cualquier otro software de Windows, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="0b54f-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET Framework 4.6 or any other Windows software, as shown here:</span></span>

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="0b54f-108">[Anterior](visual-studio-tools-for-docker.md)
>[Siguiente](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="0b54f-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>
