---
title: 'NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos'
description: Procedimiento para resolver el problema de la falta de un destino en un archivo de recursos.
author: sfoslund
ms.topic: error-reference
ms.date: 12/17/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: e3e7389adf6a9a715d44661a5f7cbae5efe299e4
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678165"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a>NETSDK1005 y NETSDK1047: Falta el destino del archivo de recursos

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

Cuando el SDK de .NET emite el error NETSDK1005 o NETSDK1047, falta información sobre una de las plataformas de destino en el archivo de recursos del proyecto. NuGet escribe un archivo llamado *project.assets.json* en la carpeta *obj* y el SDK de .NET lo usa para obtener información sobre los paquetes que se van a pasar al compilador. En .NET 5, NuGet agregó un nuevo campo denominado `TargetFrameworkAlias`, por lo que las versiones anteriores de MSBuild o NuGet generan un archivo de recursos sin el nuevo campo. Para obtener más información, vea [error NETSDK1005](https://developercommunity.visualstudio.com/content/problem/1248649/error-netsdk1005-assets-file-projectassetsjson-doe.html).

Estas son algunas acciones que puede realizar y que pueden resolver el error:

* Asegúrese de que está usando la versión 16.8 o posterior de MSBuild y la versión 5.8 o posterior de NuGet y restaure el proyecto después de actualizar las herramientas. Si usa la versión 5.8 o posterior de NuGet, debe usar Visual Studio 2019, versión 16.8 o posterior; MSBuild, versión 16.8 o posterior, y el SDK de .NET 5.0 o posterior.

* Si obtiene el error durante la compilación de un proyecto en Visual Studio 2019 por primera vez después de instalar la versión 16.8 o después de cambiar la plataforma de destino del proyecto, vuelva a compilar el proyecto por segunda vez.

* Elimine la carpeta *obj* antes de compilar el proyecto.

* Asegúrese de que el valor de destino que falta está incluido en la propiedad `TargetFrameworks` del proyecto.
