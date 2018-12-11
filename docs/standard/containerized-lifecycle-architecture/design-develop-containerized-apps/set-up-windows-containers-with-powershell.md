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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar los contenedores de Windows (basado en Docker estándar)

Con [contenedores Windows](/virtualization/windowscontainers/about/index), se puede convertir las aplicaciones de Windows existentes a las imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.

Para utilizar contenedores de Windows, basta con escribir comandos de Windows PowerShell en el DockerFile, como se muestra en el ejemplo siguiente:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

En este caso, nos vamos a usar Windows PowerShell para instalar una imagen base de Windows Server Core, así como IIS.

De forma similar, también podría usar los comandos de Windows PowerShell para configurar componentes adicionales como el tradicional de ASP.NET 4.x y .NET 4.6 o cualquier otro software de Windows, como se muestra aquí:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Anterior](visual-studio-tools-for-docker.md)
>[Siguiente](../docker-devops-workflow/index.md)
