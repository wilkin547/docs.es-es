---
ms.openlocfilehash: 540eebd957ce8ce0928db2bd8317cb220cba30bb
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031776"
---

<span data-ttu-id="bed0e-101">Los [scripts de dotnet-install](../../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del **SDK** y del **Runtime**.</span><span class="sxs-lookup"><span data-stu-id="bed0e-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="bed0e-102">Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="bed0e-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="bed0e-103">El valor predeterminado del script es instalar la versión más reciente del SDK de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="bed0e-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="bed0e-104">Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="bed0e-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="bed0e-105">Para instalar el entorno de ejecución de .NET en lugar del SDK, use el parámetro `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="bed0e-105">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="bed0e-106">Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica.</span><span class="sxs-lookup"><span data-stu-id="bed0e-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="bed0e-107">El comando siguiente instala el SDK de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="bed0e-107">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="bed0e-108">Para más información, consulte la [referencia de los scripts de dotnet-install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="bed0e-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
