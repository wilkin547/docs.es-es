---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506982"
---

<span data-ttu-id="0d425-101">Si recibe un mensaje de error similar a **No se puede encontrar el paquete {dotnet-package}** o **No se han podido instalar algunos paquetes**, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="0d425-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="0d425-102">Hay dos marcadores de posición en el siguiente conjunto de comandos.</span><span class="sxs-lookup"><span data-stu-id="0d425-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="0d425-103">Representa el paquete de .NET que va a instalar, como `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="0d425-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="0d425-104">Se usa en el comando `sudo apt-get install` siguiente.</span><span class="sxs-lookup"><span data-stu-id="0d425-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="0d425-105">Representa la versión de Linux en la que está.</span><span class="sxs-lookup"><span data-stu-id="0d425-105">This represents the Linux version you are on.</span></span> <span data-ttu-id="0d425-106">Se usa en el comando `wget` siguiente.</span><span class="sxs-lookup"><span data-stu-id="0d425-106">This is used in the `wget` command below.</span></span>

<span data-ttu-id="0d425-107">Primero, pruebe a purgar la lista de paquetes:</span><span class="sxs-lookup"><span data-stu-id="0d425-107">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="0d425-108">Después, intente volver a instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="0d425-108">Then, try to install .NET again.</span></span> <span data-ttu-id="0d425-109">Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0d425-109">If that doesn't work, you can run a manual install with the following commands:</span></span>
