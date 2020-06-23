---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602721"
---

Los [scripts de dotnet-install](../../tools/dotnet-install-script.md) se usan para las instalaciones de automatización y sin administrador del **SDK**. Puede descargar el script de <https://dot.net/v1/dotnet-install.sh>.

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Para instalar la versión actual, que puede no ser una versión (LTS), use el parámetro `-c Current`.

```bash
./dotnet-install.sh -c Current
```

Para instalar .NET Core Runtime en lugar del SDK, use el parámetro `--runtime`.

```bash
./dotnet-install.sh -c Current --runtime
```

Para instalar una versión específica, modifique el parámetro `-c` para indicar la versión específica. El siguiente comando instala el SDK de .NET Core 3.1.

```bash
./dotnet-install.sh -c 3.1
```

Para más información, consulte la [referencia de los scripts de dotnet-install](../../tools/dotnet-install-script.md).
