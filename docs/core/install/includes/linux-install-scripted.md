---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768407"
---

Los [scripts de dotnet-install](../../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del **SDK** y del **Runtime**. Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.

El valor predeterminado del script es instalar la versión más reciente del SDK de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Para instalar .NET Core Runtime en lugar del SDK, use el parámetro `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica. El siguiente comando instala el SDK de .NET Core 3.1.

```bash
./dotnet-install.sh -c 3.1
```

Para más información, consulte la [referencia de los scripts de dotnet-install](../../tools/dotnet-install-script.md).
