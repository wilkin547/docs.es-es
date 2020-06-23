---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602751"
---

<span data-ttu-id="1f97a-101">Si recibe un mensaje de error similar a **No se puede encontrar el paquete (netcore-package)** , ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1f97a-101">If you receive an error message similar to **Unable to locate package {netcore-package}**, run the following commands.</span></span>

<span data-ttu-id="1f97a-102">Hay dos marcadores de posición en el siguiente conjunto de comandos.</span><span class="sxs-lookup"><span data-stu-id="1f97a-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="1f97a-103">Representa el paquete de .NET Core que va a instalar, como `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="1f97a-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="1f97a-104">Se usa en el comando `sudo apt-get install` siguiente.</span><span class="sxs-lookup"><span data-stu-id="1f97a-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="1f97a-105">Representa la versión de Linux en la que está.</span><span class="sxs-lookup"><span data-stu-id="1f97a-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="1f97a-106">Se usa en el comando `wget` siguiente.</span><span class="sxs-lookup"><span data-stu-id="1f97a-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="1f97a-107">Pruebe a purgar la lista de paquetes:</span><span class="sxs-lookup"><span data-stu-id="1f97a-107">Try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

<span data-ttu-id="1f97a-108">Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f97a-108">If that doesn't work, you can run a manual install with the following commands:</span></span>
