---
ms.openlocfilehash: 07dd58c314c826c426193b829ea1f64669fb888b
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594577"
---

Los [scripts de dotnet-install](../../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del **SDK** y del **Runtime**. Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.

El valor predeterminado del script es instalar la versión más reciente del SDK de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET 3.1. Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Para instalar el entorno de ejecución de .NET en lugar del SDK, use el parámetro `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica. El comando siguiente instala el SDK de .NET 5.0.

```bash
./dotnet-install.sh -c 5.0
```

Para más información, consulte la [referencia de los scripts de dotnet-install](../../tools/dotnet-install-script.md).
