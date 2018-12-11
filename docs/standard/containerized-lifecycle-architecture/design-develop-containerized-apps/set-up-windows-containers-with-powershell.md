---
title: Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (basado en Docker estándar)
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 5e85beea0efbee6a2b6594e3a49d705505a36e1c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149398"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="d8828-103">Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (basado en Docker estándar)</span><span class="sxs-lookup"><span data-stu-id="d8828-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="d8828-104">Con [contenedores Windows](/virtualization/windowscontainers/about/index), se puede convertir las aplicaciones de Windows existentes a las imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.</span><span class="sxs-lookup"><span data-stu-id="d8828-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="d8828-105">Para utilizar contenedores de Windows, basta con escribir comandos de Windows PowerShell en el DockerFile, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8828-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="d8828-106">En este caso, nos vamos a usar Windows PowerShell para instalar una imagen base de Windows Server Core, así como IIS.</span><span class="sxs-lookup"><span data-stu-id="d8828-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="d8828-107">De forma similar, también podría usar los comandos de Windows PowerShell para configurar componentes adicionales como el tradicional de ASP.NET 4.x y .NET 4.6 o cualquier otro software de Windows, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="d8828-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="d8828-108">[Anterior](visual-studio-tools-for-docker.md)
>[Siguiente](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="d8828-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>
