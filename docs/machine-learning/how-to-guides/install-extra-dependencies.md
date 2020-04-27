---
title: Instalación de dependencias adicionales de ML.NET
description: Aprenda a instalar las bibliotecas nativas de las que dependen los paquetes de ML.NET, pero que no se instalan con los paquetes NuGet.
ms.date: 04/02/2020
author: natke
ms.author: nakersha
ms.custom: how-to
ms.openlocfilehash: c427439d0950bfea38f1d6d11af84216e0f1965f
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021845"
---
# <a name="install-extra-mlnet-dependencies"></a>Instalación de dependencias adicionales de ML.NET

En la mayoría de los casos, en todos los sistemas operativos, la instalación de ML.NET es tan simple como hacer referencia al paquete NuGet adecuado.

```bash
dotnet add package Microsoft.ML
```

Aunque, en algunos casos, existen requisitos de instalación adicionales, especialmente cuando se requieren componentes nativos. En este documento se describen los requisitos de instalación para esos casos. Las secciones se dividen por el paquete NuGet de `Microsoft.ML.*` específico que tiene la dependencia adicional.

## <a name="microsoftmltimeseries-microsoftmlautoml"></a>Microsoft.ML.TimeSeries, Microsoft.ML.AutoML

Ambos paquetes tienen una dependencia en `Microsoft.ML.MKL.Redist`, que tiene una dependencia en `libiomp`.

### <a name="windows"></a>Windows

No se requieren pasos de instalación adicionales. La biblioteca se instala cuando se agrega el paquete NuGet al proyecto.

### <a name="linux"></a>Linux

1. Instalar la clave GPG para el repositorio

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

2. Agregar el repositorio APT para MKL

    ```bash
    sudo sh -c 'echo deb https://apt.repos.intel.com/mkl all main > /etc/apt/sources.list.d/intel-mkl.list'
    ```

3. Actualizar paquetes

    ```bash
    sudo apt-get update
    ```

4. Instalar MKL

    ```bash
    sudo apt-get install <COMPONENT>-<VERSION>.<UPDATE>-<BUILD_NUMBER>
    ```

    Por ejemplo:

    ```bash
    sudo apt-get install intel-mkl-64bit-2020.0-088
    ```

    Determinar la ubicación de `libiomp.so`

    ```bash
    find /opt -name "libiomp5.so"
    ```

    Por ejemplo:

    ```output
    /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin/libiomp5.so
    ```

5. Agregue esta ubicación a la ruta de acceso de la biblioteca de carga:

    ```bash
    sudo ldconfig /opt/intel/compilers_and_libraries_2020.0.166/linux/compiler/lib/intel64_lin
    ```

### <a name="mac"></a>Mac

1. Instalar la biblioteca con `Homebrew`

    ```bash
    brew update && brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/f5b1ac99a7fba27c19cee0bc4f036775c889b359/Formula/libomp.rb && brew link libomp --force
    ```
