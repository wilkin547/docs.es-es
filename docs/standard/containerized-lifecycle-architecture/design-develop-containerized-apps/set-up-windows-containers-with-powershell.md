---
title: Usar comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (Docker estándar según)
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: d68378a12a16dd4072b381f00241e781b40c3e16
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105555"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="f68e7-103">Usar comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (Docker estándar según)</span><span class="sxs-lookup"><span data-stu-id="f68e7-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="f68e7-104">Con [contenedores de Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), puede convertir las aplicaciones de Windows existentes para las imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.</span><span class="sxs-lookup"><span data-stu-id="f68e7-104">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="f68e7-105">Para utilizar los contenedores de Windows, solo tiene que escribir comandos de Windows PowerShell en el DockerFile, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f68e7-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="f68e7-106">En este caso, vamos a usar Windows PowerShell para instalar una imagen base de Windows Server Core, así como IIS.</span><span class="sxs-lookup"><span data-stu-id="f68e7-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="f68e7-107">De forma similar, también puede usar comandos de Windows PowerShell para configurar componentes adicionales como ASP.NET tradicional 4.x y 4.6 de .NET o cualquier otro software de Windows, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="f68e7-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="f68e7-108">[Anterior](visual-studio-tools-for-docker.md)
[Siguiente](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="f68e7-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>
