---
title: 'Instalación de .NET en Alpine: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Alpine.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 6adaa905c400b45526ebbc3d8e2606522863eec3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970855"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-alpine"></a>Instalación del SDK y el entorno de ejecución de .NET en Alpine

En este artículo se describe cómo instalar .NET en Alpine. Cuando una versión de Alpine no es compatible, .NET deja de ser compatible con esa versión. Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install"></a>Instalar

No hay instaladores disponibles para Alpine Linux. Debe instalar .NET de una de las maneras siguientes:

- [Paquete de snaps](linux-snap.md)
- [Instalación con scripts con _install-dotnet.sh_](linux-scripted-manual.md#scripted-install)
- [Extracción binaria manual](linux-scripted-manual.md#manual-install)

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Alpine en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- El símbolo ✔️ indica que todavía se admite la versión de Alpine o de .NET.
- El símbolo ❌ indica que la versión de Alpine o de .NET no se admite en esa versión de Alpine.
- Si una versión de Alpine y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Alpine  | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|-------- |---------------|---------------|----------------|
| ✔️ 3.12 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.11 | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ 3.10 | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.9  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ 3.8  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |

Las versiones siguientes de .NET ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Dependencias

Para .NET en Alpine Linux es necesario que estén instaladas las dependencias siguientes:

- icu-libs
- krb5-libs
- libgcc
- libintl
- libssl1.1 (Alpine 3.9 o superior)
- libssl1.0 (Alpine 3.8 o inferior)
- libstdc++
- zlib

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para habilitar la finalización con tabulación para la CLI de .NET](../tools/enable-tab-autocomplete.md)
- [Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
