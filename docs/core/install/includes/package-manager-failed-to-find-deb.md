---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132954"
---

<span data-ttu-id="76837-101">Si recibe un mensaje de error similar a **No se puede encontrar el paquete {netcore-package}** o **No se han podido instalar algunos paquetes**, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="76837-101">If you receive an error message similar to **Unable to locate package {netcore-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="76837-102">Hay dos marcadores de posición en el siguiente conjunto de comandos.</span><span class="sxs-lookup"><span data-stu-id="76837-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="76837-103">Representa el paquete de .NET Core que va a instalar, como `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="76837-103">This represents the .NET Core package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="76837-104">Se usa en el comando `sudo apt-get install` siguiente.</span><span class="sxs-lookup"><span data-stu-id="76837-104">This is used in the `sudo apt-get install` command below.</span></span>

- `{os-version}`\
<span data-ttu-id="76837-105">Representa la versión de Linux en la que está.</span><span class="sxs-lookup"><span data-stu-id="76837-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="76837-106">Se usa en el comando `wget` siguiente.</span><span class="sxs-lookup"><span data-stu-id="76837-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="76837-107">Primero, pruebe a purgar la lista de paquetes:</span><span class="sxs-lookup"><span data-stu-id="76837-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="76837-108">Después, intente instalar .NET Core de nuevo.</span><span class="sxs-lookup"><span data-stu-id="76837-108">Then, try to install .NET Core again.</span></span> <span data-ttu-id="76837-109">Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="76837-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
