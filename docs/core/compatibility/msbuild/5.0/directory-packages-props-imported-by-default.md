---
title: 'Cambio importante: Los archivos Directory.Packages.props se importan de forma predeterminada'
description: Obtenga información sobre el cambio importante de .NET 5.0 por el que los archivos .props de NuGet importan de forma automática un archivo denominado Directory.Packages.props si se encuentra en la carpeta del proyecto o en cualquiera de sus antecesores.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760153"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a>Los archivos Directory.Packages.props se importan de forma predeterminada

Los archivos *.props* de NuGet importan de forma automática un archivo denominado *Directory.Packages.props* si se encuentra en la carpeta del proyecto o en cualquiera de sus antecesores.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, podía tener un archivo con el nombre *Directory.Packages.props* en el archivo del proyecto y el archivo *.props* de NuGet no lo importaría de forma automática en tiempo de compilación.

A partir de .NET 5.0, este tipo de archivo *se importa* automáticamente si existe en la carpeta del proyecto o en cualquiera de sus antecesores. Si tiene un archivo con este nombre en la carpeta del proyecto, esta importación automática podría cambiar el comportamiento de la compilación. Por ejemplo, el archivo no se importaba y ahora se importará, o bien el orden del momento de la importación se podría cambiar si lo importa de forma específica.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha realizado para admitir el [control de versiones de paquetes centrales](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) para NuGet.

## <a name="recommended-action"></a>Acción recomendada

Cambie el nombre del archivo *Directory.Packages.props* existente si no se debe importar de forma automática.

## <a name="affected-apis"></a>API afectadas

N/D

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
