---
title: Cambios importantes de MSBuild
description: Se enumeran los cambios importantes de MSBuild en .NET Core 2.1 - 3.1.
ms.date: 02/22/2021
ms.openlocfilehash: 03fcd9807a83c4f679dc659b009c857e351b9b2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105648"
---
# <a name="msbuild-breaking-changes-in-net-core-21---31"></a>Cambios importantes de MSBuild en .NET Core 2.1 - 3.1

En esta página se documentan los siguientes cambios importantes:

| Cambio importante | Versión introducida |
| - | - |
| [Las compilaciones en tiempo de diseño solo devuelven referencias de paquete de nivel superior](#design-time-builds-only-return-top-level-package-references) | 3.1 |
| [Cambio de nombre de archivo de manifiesto del recurso](#resource-manifest-file-name-change) | 3.0 |
| [Herramientas de proyecto ahora incluidas en el SDK](#project-tools-now-included-in-sdk) | 2.1 |

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE [design-time-builds-return-top-level-package-refs](../../../includes/core-changes/msbuild/3.1/design-time-builds-return-top-level-package-refs.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](../../../includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [DotNetCliToolReference project elements removed for bundled tools](../../../includes/core-changes/msbuild/2.1/dotnetclitoolreference.md)]

***
