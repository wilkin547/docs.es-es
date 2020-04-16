---
title: Instalación de dependencias adicionales de ML.NET
description: Aprenda a instalar las bibliotecas nativas de las que dependen los paquetes de ML.NET, pero que no se instalan con los paquetes NuGet.
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: 0b870542706c065295d48205b7780e568e267ab6
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888279"
---
# <a name="install-extra-mlnet-dependencies"></a><span data-ttu-id="6fc19-103">Instalación de dependencias adicionales de ML.NET</span><span class="sxs-lookup"><span data-stu-id="6fc19-103">Install extra ML.NET dependencies</span></span>

<span data-ttu-id="6fc19-104">En la mayoría de los casos, en todos los sistemas operativos, la instalación de ML.NET es tan simple como hacer referencia al paquete NuGet adecuado.</span><span class="sxs-lookup"><span data-stu-id="6fc19-104">In most cases, on all operating systems, installing ML.NET is as simple as referencing the appropriate NuGet package.</span></span>

```bash
dotnet add package Microsoft.ML
```

<span data-ttu-id="6fc19-105">Aunque, en algunos casos, existen requisitos de instalación adicionales, especialmente cuando se requieren componentes nativos.</span><span class="sxs-lookup"><span data-stu-id="6fc19-105">In some cases though, there are additional installation requirements, particularly when native components are required.</span></span> <span data-ttu-id="6fc19-106">En este documento se describen los requisitos de instalación para esos casos.</span><span class="sxs-lookup"><span data-stu-id="6fc19-106">This document describes the installation requirements for those cases.</span></span> <span data-ttu-id="6fc19-107">Las secciones se dividen por el paquete NuGet de `Microsoft.ML.*` específico que tiene la dependencia adicional.</span><span class="sxs-lookup"><span data-stu-id="6fc19-107">The sections are broken down by the specific `Microsoft.ML.*` NuGet package that has the additional dependency.</span></span>

## <a name="microsoftmltimeseries-microsoftmlautoml"></a><span data-ttu-id="6fc19-108">Microsoft.ML.TimeSeries, Microsoft.ML.AutoML</span><span class="sxs-lookup"><span data-stu-id="6fc19-108">Microsoft.ML.TimeSeries, Microsoft.ML.AutoML</span></span>

<span data-ttu-id="6fc19-109">Ambos paquetes tienen una dependencia en `Microsoft.ML.MKL.Redist`, que tiene una dependencia en `libiomp`.</span><span class="sxs-lookup"><span data-stu-id="6fc19-109">Both of these packages have a dependency on `Microsoft.ML.MKL.Redist`, which has a dependency on `libiomp`.</span></span>

### <a name="windows"></a><span data-ttu-id="6fc19-110">Windows</span><span class="sxs-lookup"><span data-stu-id="6fc19-110">Windows</span></span>

<span data-ttu-id="6fc19-111">No se requieren pasos de instalación adicionales.</span><span class="sxs-lookup"><span data-stu-id="6fc19-111">No extra installation steps required.</span></span> <span data-ttu-id="6fc19-112">La biblioteca se instala cuando se agrega el paquete NuGet al proyecto.</span><span class="sxs-lookup"><span data-stu-id="6fc19-112">The library is installed when the NuGet package is added to the project.</span></span>

### <a name="linux"></a><span data-ttu-id="6fc19-113">Linux</span><span class="sxs-lookup"><span data-stu-id="6fc19-113">Linux</span></span>

1. <span data-ttu-id="6fc19-114">Instalar la clave GPG para el repositorio</span><span class="sxs-lookup"><span data-stu-id="6fc19-114">Install the GPG key for the repository</span></span>

    ```bash
    sudo bash
    # <type your user password when prompted.  this will put you in a root shell>
    # cd to /tmp where this shell has write permission
    cd /tmp
    # now get the key:
    wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now install that key
    apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    # now remove the public key file exit the root shell
    rm GPG-PUB-KEY-INTEL-SW-PRODUCTS-2019.PUB
    exit
    ```

2. <span data-ttu-id="6fc19-115">Agregar el repositorio APT para MKL</span><span class="sxs-lookup"><span data-stu-id="6fc19-115">Add the APT Repository for MKL</span></span>

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. <span data-ttu-id="6fc19-116">Actualizar paquetes</span><span class="sxs-lookup"><span data-stu-id="6fc19-116">Update packages</span></span>

    ```bash
    sudo apt-get update
    ```

4. <span data-ttu-id="6fc19-117">Instalar MKL</span><span class="sxs-lookup"><span data-stu-id="6fc19-117">Install MKL</span></span>

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    <span data-ttu-id="6fc19-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fc19-118">For example:</span></span>

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    <span data-ttu-id="6fc19-119">Determinar la ubicación de `libiomp.so`</span><span class="sxs-lookup"><span data-stu-id="6fc19-119">Determine the location of `libiomp.so`</span></span>

    ```bash
    find /opt -name "libiomp5.so"
    ```

    <span data-ttu-id="6fc19-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fc19-120">For example:</span></span>

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. <span data-ttu-id="6fc19-121">Agregue esta ubicación a la ruta de acceso de la biblioteca de carga:</span><span class="sxs-lookup"><span data-stu-id="6fc19-121">Add this location to the load library path:</span></span>

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_li
    ```

### <a name="mac"></a><span data-ttu-id="6fc19-122">Mac</span><span class="sxs-lookup"><span data-stu-id="6fc19-122">Mac</span></span>

1. <span data-ttu-id="6fc19-123">Instalar la biblioteca con `Homebrew`</span><span class="sxs-lookup"><span data-stu-id="6fc19-123">Install the library with `Homebrew`</span></span>

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```
