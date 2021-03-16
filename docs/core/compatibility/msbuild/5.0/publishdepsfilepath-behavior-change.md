---
title: 'Cambio importante: Cambio de comportamiento de PublishDepsFilePath'
description: Obtenga información sobre el cambio importante en .NET 5 en el que la propiedad PublishDepsFilePath de MSBuild está vacía para las aplicaciones de un solo archivo.
ms.date: 09/17/2020
ms.openlocfilehash: 3a32f733ceaa2a24eb55d5e89f2eb1791c277f0d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256509"
---
# <a name="publishdepsfilepath-behavior-change"></a>Cambio de comportamiento de PublishDepsFilePath

La propiedad `PublishDepsFilePath` de MSBuild está vacía para las aplicaciones de archivo único. Además, en el caso de las aplicaciones que no son de archivo único, es posible que el archivo *deps.json* no se copie en el directorio de salida hasta después en la compilación.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la propiedad `PublishDepsFilePath` de MSBuild es la ruta de acceso al archivo *deps.json* de la aplicación en el directorio de salida para las aplicaciones que no son de archivo único, y una ruta de acceso en el directorio intermedio para las aplicaciones de archivo único.

A partir de .NET 5, `PublishDepsFilePath` está vacío para las aplicaciones de archivo único y una nueva propiedad `IntermediateDepsFilePath` especifica la ubicación de *deps.json* en el directorio intermedio. Además, en el caso de las aplicaciones que no son de archivo único, es posible que el archivo *deps.json* no se copie en el directorio de salida (es decir, la ruta de acceso especificada por `PublishDepsFilePath`) hasta después en la compilación.

## <a name="reason-for-change"></a>Motivo del cambio

Este cambio se ha realizado por dos motivos:

- Debido a la refactorización de la lógica de publicación para admitir [aplicaciones de archivo único mejoradas](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) en .NET 5.

- En las aplicaciones de archivo único, para protegerse de los destinos que intentan volver a escribir el archivo *deps.json* después de que *deps.json* ya se haya agrupado, por lo que no afecta a la aplicación de forma silenciosa. Por este motivo, `PublishDepsFilePath` está vacía para las aplicaciones de archivo único.

## <a name="recommended-action"></a>Acción recomendada

Los destinos que reescriben el archivo *deps.json* deberían hacerlo por lo general mediante la propiedad `IntermediateDepsFilePath`.

## <a name="affected-apis"></a>API afectadas

N/D

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
