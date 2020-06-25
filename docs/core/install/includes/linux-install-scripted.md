---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768407"
---

<span data-ttu-id="ab0c9-101">Los [scripts de dotnet-install](../../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del **SDK** y del **Runtime**.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="ab0c9-102">Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="ab0c9-103">El valor predeterminado del script es instalar la versión más reciente del SDK de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="ab0c9-104">Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="ab0c9-105">Para instalar .NET Core Runtime en lugar del SDK, use el parámetro `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="ab0c9-106">Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="ab0c9-107">El siguiente comando instala el SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="ab0c9-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="ab0c9-108">Para más información, consulte la [referencia de los scripts de dotnet-install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="ab0c9-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
