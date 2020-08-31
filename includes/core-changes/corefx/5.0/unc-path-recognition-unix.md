---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720214"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a>Reconocimiento de URI de rutas UNC en UNIX

La clase <xref:System.Uri> ahora reconoce cadenas que comienzan con dos barras diagonales (`//`) como rutas de acceso UNC (Convención de nomenclatura universal) en sistemas operativos UNIX. Este cambio hace que el comportamiento de estas cadenas sea coherente en todas las plataformas.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales, por ejemplo `//contoso`, como rutas de acceso de archivo absolutas en sistemas operativos UNIX. Pero en Windows, estas cadenas se reconocen como rutas de acceso UNC.

A partir de .NET 5.0, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales como rutas de acceso UNC en todas las plataformas, incluido UNIX. Además, las propiedades se comportan de acuerdo con la semántica de UNC:

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> devuelve `true`.
- Las barras diagonales inversas de la ruta de acceso se reemplazan por barras diagonales. Por ejemplo, `//first\second` se convierte en `//first/second`.
- <xref:System.Uri.LocalPath?displayProperty=nameWithType> no codifica los caracteres. Por ejemplo, `//first/\uFFF0` *no* se convierte en `//first/%EF%BF%B0`.

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
