---
title: 'Cambio importante: Blazor: se ha cambiado el nombre de parámetro en el método RequestImageFileAsync'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Blazor: se ha cambiado el nombre de parámetro en el método RequestImageFileAsync.'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: bfaaa6bfe94c32fbc1a5b5b70db863d105d389b5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488265"
---
# <a name="blazor-parameter-name-changed-in-requestimagefileasync-method"></a>Blazor: se ha cambiado el nombre de parámetro en el método RequestImageFileAsync

Se ha cambiado el nombre del parámetro `maxWith` del método `RequestImageFileAsync` de `maxWith` a `maxWidth`.

## <a name="version-introduced"></a>Versión introducida

6.0 (versión preliminar 1)

## <a name="old-behavior"></a>Comportamiento anterior

El nombre del parámetro se escribe `maxWith`.

## <a name="new-behavior"></a>Comportamiento nuevo

El nombre del parámetro se escribe `maxWidth`.

## <a name="reason-for-change"></a>Motivo del cambio

El nombre del parámetro original era un error tipográfico.

## <a name="recommended-action"></a>Acción recomendada

Si usa parámetros con nombre en la API `RequestImageFile`, actualice el nombre del parámetro `maxWith` a `maxWidth`. De lo contrario, no es necesario ningún cambio.

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync`

-->
