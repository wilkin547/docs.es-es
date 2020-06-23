---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602721"
---

<span data-ttu-id="2f510-101">Los [scripts de dotnet-install](../../tools/dotnet-install-script.md) se usan para las instalaciones de automatización y sin administrador del **SDK**.</span><span class="sxs-lookup"><span data-stu-id="2f510-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK**.</span></span> <span data-ttu-id="2f510-102">Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="2f510-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="2f510-103">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2f510-103">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="2f510-104">Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.</span><span class="sxs-lookup"><span data-stu-id="2f510-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="2f510-105">Para instalar .NET Core Runtime en lugar del SDK, use el parámetro `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="2f510-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime
```

<span data-ttu-id="2f510-106">Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica.</span><span class="sxs-lookup"><span data-stu-id="2f510-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="2f510-107">El siguiente comando instala el SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2f510-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="2f510-108">Para más información, consulte la [referencia de los scripts de dotnet-install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="2f510-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>
