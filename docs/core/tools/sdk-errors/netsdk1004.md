---
title: 'NETSDK1004: archivo de recursos no encontrado'
description: Obtenga información sobre el error NETSDK1004 del SDK de .NET, que se produce cuando no se encuentra el archivo project.assets.json.
ms.topic: error-reference
ms.date: 01/29/2021
f1_keywords:
- NETSDK1004
ms.openlocfilehash: aa01ff657143faac96baa5ae1133493516edfb1c
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206718"
---
# <a name="netsdk1004-assets-file-not-found"></a>NETSDK1004: archivo de recursos no encontrado

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

NuGet escribe un archivo llamado *project.assets.json* en la carpeta *obj* y el SDK de .NET lo usa para obtener información sobre los paquetes que se van a pasar al compilador. Este error se produce cuando no se encuentra el archivo de recursos *project.assets.json* durante la compilación. El mensaje de error es similar al ejemplo siguiente:

**NETSDK1004: No se ha encontrado el archivo de recursos "C:\ruta\a\project.assets.json". Ejecute una restauración de paquetes NuGet para generar el archivo.**

Estas son algunas posibles causas del error:

* Está ejecutando el comando `dotnet build` desde una ruta de directorio que contiene un carácter `%`. Para resolver el error, quite el carácter `%` del nombre de la carpeta y vuelva a ejecutar `dotnet build`.
* El sistema del proyecto no detectó ni restauró automáticamente un cambio en el archivo del proyecto. Para resolver el error, abra un símbolo del sistema y ejecute `dotnet restore` en el proyecto.
* Una versión anterior de Nuget.exe ha restaurado un proyecto por separado. Para resolver el error, abra un símbolo del sistema y ejecute `dotnet restore` en el proyecto.
* Un error anterior, como NETSDK1045 (la versión del SDK que está usando no es compatible con la plataforma de destino del proyecto), impedía que NuGet creara el archivo de recursos del proyecto. Para resolver el error NETSDK1004, resuelva el error anterior y, después, ejecute `dotnet restore` en el proyecto.
* La CI de App Center está compilando un proyecto con un ensamblado externo que no está en NuGet. Para resolver el error, use un paquete NuGet para el ensamblado.
* Ha agregado una carpeta de soluciones en Visual Studio con un nombre que comienza con un punto. Para resolver el error, quite el punto inicial del nombre de la carpeta.
