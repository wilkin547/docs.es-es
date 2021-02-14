---
ms.openlocfilehash: 3275865cf7f4669ba7deaacea320136d02f64dda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804206"
---

<span data-ttu-id="d9666-101">Si recibe un mensaje de error similar a **No se puede encontrar el paquete {dotnet-package}** o **No se han podido instalar algunos paquetes**, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d9666-101">If you receive an error message similar to **Unable to locate package {dotnet-package}** or **Some packages could not be installed**, run the following commands.</span></span>

<span data-ttu-id="d9666-102">Hay dos marcadores de posición en el siguiente conjunto de comandos.</span><span class="sxs-lookup"><span data-stu-id="d9666-102">There are two placeholders in the following set of commands.</span></span>

- `{dotnet-package}`\
<span data-ttu-id="d9666-103">Representa el paquete de .NET que va a instalar, como `aspnetcore-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="d9666-103">This represents the .NET package you're installing, such as `aspnetcore-runtime-3.1`.</span></span> <span data-ttu-id="d9666-104">Se usa en el comando `sudo apt-get install` siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9666-104">This is used in the following `sudo apt-get install` command.</span></span>

- `{os-version}`\
<span data-ttu-id="d9666-105">Representa la versión de distribución en la que se encuentra.</span><span class="sxs-lookup"><span data-stu-id="d9666-105">This represents the distribution version you're on.</span></span> <span data-ttu-id="d9666-106">Se usa en el comando `wget` siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9666-106">This is used in the `wget` command below.</span></span> <span data-ttu-id="d9666-107">La versión de distribución es el valor numérico, como `20.04` en Ubuntu o `10` en Debian.</span><span class="sxs-lookup"><span data-stu-id="d9666-107">The distribution version is the numerical value, such as `20.04` on Ubuntu or `10` on Debian.</span></span>

<span data-ttu-id="d9666-108">Primero, pruebe a purgar la lista de paquetes:</span><span class="sxs-lookup"><span data-stu-id="d9666-108">First, try purging the package list:</span></span>

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

<span data-ttu-id="d9666-109">Después, intente volver a instalar .NET.</span><span class="sxs-lookup"><span data-stu-id="d9666-109">Then, try to install .NET again.</span></span> <span data-ttu-id="d9666-110">Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9666-110">If that doesn't work, you can run a manual install with the following commands:</span></span>
