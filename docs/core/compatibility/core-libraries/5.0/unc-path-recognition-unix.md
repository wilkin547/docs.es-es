---
title: 'Cambio importante: Reconocimiento de URI de rutas UNC en UNIX'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde ahora la clase Uri reconoce cadenas que comienzan con dos barras diagonales como rutas de acceso UNC en Unix.
ms.date: 11/01/2020
ms.openlocfilehash: 65baaad5e1be7a8f61e3e62c976fd7e28f48730f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257029"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a>Reconocimiento de URI de rutas UNC en UNIX

La clase <xref:System.Uri> ahora reconoce cadenas que comienzan con dos barras diagonales (`//`) como rutas de acceso UNC (Convención de nomenclatura universal) en sistemas operativos UNIX. Este cambio hace que el comportamiento de estas cadenas sea coherente en todas las plataformas.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales, por ejemplo `//contoso`, como rutas de acceso de archivo absolutas en sistemas operativos Unix. Pero en Windows, estas cadenas se reconocen como rutas de acceso UNC.

A partir de .NET 5, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales como rutas de acceso UNC en todas las plataformas, incluido Unix. Además, las propiedades se comportan de acuerdo con la semántica de UNC:

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> devuelve `true`.
- Las barras diagonales inversas de la ruta de acceso se reemplazan por barras diagonales. Por ejemplo, `//first\second` se convierte en `//first/second`.
- <xref:System.Uri.LocalPath?displayProperty=nameWithType> no codifica los caracteres. Por ejemplo, `//first/\uFFF0` *no* se convierte en `//first/%EF%BF%B0`.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
