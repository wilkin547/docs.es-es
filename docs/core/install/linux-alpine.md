---
title: 'Instalación de .NET Core en Alpine: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Alpine.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 92753933cbcedae28867b66293d1044f700d7baa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324825"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a>Instalación del SDK de .NET Core o .NET Core Runtime en Alpine

En este artículo se explica cómo instalar .NET Core en Alpine. Cuando una versión de Alpine no es compatible, .NET Core deja de ser compatible con esa versión. Pero estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

No hay instaladores para Alpine. Debe usar el [script de instalación](#scripted-install) o seguir las instrucciones de [instalación manual](#manual-install).

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Alpine en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- Una ✔️ indica que todavía se admite la versión de Alpine o de .NET Core.
- Una ❌ indica que la versión de Alpine o de .NET Core no se admite en esa versión de Alpine.
- Cuando una versión de Alpine y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Alpine                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 (versión preliminar) |
|--------------------------|---------------|---------------|----------------|
| ✔️ 3.12  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ 3.11  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ 3.10  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ 3.9   | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ 3.8   | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |

Las siguientes versiones de .NET Core ya no se admiten, aunque sus descargas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Dependencias

.NET Core en Alpine Linux exige que estén instaladas las siguientes dependencias:

- icu-libs
- krb5-libs
- libintl
- libssl1.1 (Alpine 3.9 o superior)
- libssl1.0 (Alpine 3.8)
- libstdc++
- lttng-ust
- numactl (opcional)
- zlib

## <a name="scripted-install"></a>Instalación con script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalación manual

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Pasos siguientes

- [Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
