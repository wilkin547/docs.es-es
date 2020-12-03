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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Uso de comandos de Windows PowerShell en un archivo DockerFile para configurar contenedores con Windows (basado en Docker estándar)

Con los [contenedores de Windows](/virtualization/windowscontainers/about/index), puede convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.

Para usar contenedores de Windows, simplemente debe escribir comandos de Windows PowerShell en el archivo Dockerfile, como se muestra en el ejemplo siguiente:

```dockerfile
FROM mcr.microsoft.com/windows/servercore:ltsc2019
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

En este caso, vamos a usar Windows PowerShell para instalar una imagen base de Windows Server Core, así como IIS.

Del mismo modo, también se pueden usar comandos de Windows PowerShell para configurar componentes adicionales como ASP.NET 4.x tradicional, .NET Framework 4.6 o cualquier otro software de Windows, como se muestra aquí:

```dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Anterior](visual-studio-tools-for-docker.md)
>[Siguiente](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
