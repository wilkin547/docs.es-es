---
title: Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (basado en Docker estándar)
description: Obtenga información sobre cómo usar PowerShell cuando se trabaja con Docker en contenedores de Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: d9c0bc28f62d44eb7471b99c63055ef43da12a69
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664710"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (basado en Docker estándar)

Con [contenedores Windows](/virtualization/windowscontainers/about/index), se puede convertir las aplicaciones de Windows existentes a las imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.

Para utilizar contenedores de Windows, basta con escribir comandos de Windows PowerShell en el DockerFile, como se muestra en el ejemplo siguiente:

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

En este caso, nos vamos a usar Windows PowerShell para instalar una imagen base de Windows Server Core, así como IIS.

De forma similar, también podría usar los comandos de Windows PowerShell para configurar componentes adicionales como el tradicional de ASP.NET 4.x y .NET 4.6 o cualquier otro software de Windows, como se muestra aquí:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Anterior](visual-studio-tools-for-docker.md)
>[Siguiente](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
