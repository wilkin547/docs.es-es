---
title: Puesta al día del runtime para implementaciones de aplicaciones autocontenidas de .NET Core.
description: Obtenga información sobre los cambios de dotnet publish para implementaciones autocontenidas.
author: KathleenDollard
ms.date: 05/31/2018
ms.openlocfilehash: 22385c7b5d2bf87755fd51cd6268d21fe3431c74
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740786"
---
# <a name="self-contained-deployment-runtime-roll-forward"></a>Puesta al día del runtime de implementación autocontenida

Las [implementaciones de aplicaciones autocontenidas](index.md) de .NET Core incluyen las bibliotecas de .NET Core y el runtime de .NET Core. A partir del SDK de .NET Core 2.1 (versión 2.1.300), una implementación de aplicación autocontenida [publica el runtime con la revisión superior en el equipo](https://github.com/dotnet/designs/pull/36). De forma predeterminada, el comando [`dotnet publish`](../tools/dotnet-publish.md) para una implementación autocontenida selecciona la versión más reciente instalada como parte del SDK en el equipo de publicación. Esto permite que la aplicación implementada se ejecute con las revisiones de seguridad (y otras correcciones) disponibles en el momento de usar el comando `publish`. La aplicación debe volver a publicarse para obtener una nueva revisión. Para crear una aplicación autocontenida, se especifica `-r <RID>` en el comando `dotnet publish` o se especifica el [identificador de runtime (RID)](../rid-catalog.md) en el archivo de proyecto (csproj o vbproj) o en la línea de comandos.

## <a name="patch-version-roll-forward-overview"></a>Información general sobre la puesta al día de una versión de revisión

[`restore`](../tools/dotnet-restore.md), [`build`](../tools/dotnet-build.md) y [`publish`](../tools/dotnet-publish.md) son comandos de `dotnet` que se pueden ejecutar por separado. La opción de runtime forma parte de la operación `restore`, no de `publish` ni de `build`. Si se llama a `publish`, se elegirá la versión de revisión más reciente. Si se llama a `publish` con el argumento `--no-restore`, podría no obtenerse la versión de revisión deseada porque es posible que un `restore` anterior no se haya ejecutado con la directiva de publicación de la nueva aplicación autocontenida. En este caso, se genera un error de compilación con un texto similar al siguiente:

  "El proyecto se restauró usando Microsoft.NETCore.App versión 2.0.0, pero con la configuración actual, la versión 2.0.6 se usará en su lugar. Para resolver este problema, asegúrese de que se usa la misma configuración para la restauración y para operaciones posteriores tales como compilar o publicar. Normalmente este problema puede producirse si la propiedad RuntimeIdentifier se establece durante la compilación o publicación, pero no durante la restauración".

> [!NOTE]
> `restore` y `build` pueden ejecutarse implícitamente como parte de otro comando, como `publish`. Cuando se ejecutan implícitamente como parte de otro comando, se les proporciona contexto adicional para que se produzcan los artefactos correctos. Cuando se usa el comando `publish` con un runtime (por ejemplo, `dotnet publish -r linux-x64`), la parte implícita `restore` restaura los paquetes para el runtime de linux-x64. Si se llama a `restore` explícitamente, no se restauran los paquetes de runtime de forma predeterminada, dado que carece del contexto.

## <a name="how-to-avoid-restore-during-publish"></a>Cómo evitar la restauración durante la publicación

Ejecutar `restore` como parte de la operación `publish` puede no ser adecuado para su escenario. Para evitar `restore` durante `publish` al crear aplicaciones autocontenidas, haga lo siguiente:

- Establezca la propiedad `RuntimeIdentifiers` en una lista separada por punto y coma de todos los [RID](../rid-catalog.md) que se van a publicar.
- Establezca la propiedad `TargetLatestRuntimePatch` en `true`.

## <a name="no-restore-argument-with-dotnet-publish-options"></a>Argumento no-restore con opciones de dotnet publish

Si quiere crear aplicaciones autocontenidas y [aplicaciones dependientes del marco de trabajo](index.md) con el mismo archivo de proyecto, y además quiere utilizar el argumento `--no-restore` con `dotnet publish`, elija una de las opciones siguientes:

1. Preferir el comportamiento dependiente del marco de trabajo. Si la aplicación depende del marco de trabajo, este es el comportamiento predeterminado. Si la aplicación es autocontenida y puede usar un runtime local 2.1.0 sin revisiones, establezca `TargetLatestRuntimePatch` en `false` en el archivo de proyecto.

2. Preferir el comportamiento autocontenido. Si la aplicación es autocontenida, este es el comportamiento predeterminado. Si la aplicación depende del marco de trabajo y requiere que esté instalada la revisión más reciente, establezca `TargetLatestRuntimePatch` en `true` en el archivo de proyecto.

3. Para tomar el control explícito del marco de trabajo del runtime, establezca `RuntimeFrameworkVersion` en la versión de revisión específica en el archivo de proyecto.
