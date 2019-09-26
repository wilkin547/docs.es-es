---
ms.openlocfilehash: 748e7f484227b6a60a2309bde185079b30fe19de
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117204"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a>ZipArchiveEntry ya no controla los archivos con tamaños de entrada incoherentes

Los archivos zip muestran tanto el tamaño comprimido como el tamaño no comprimido en el directorio central y en el encabezado local.  Los propios datos de entrada también indican su tamaño.  En .NET Core 2.2 y versiones anteriores, nunca se comprobó la coherencia de estos valores. A partir de .NET Core 3.0, ahora son.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.2 y versiones anteriores, <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> funciona correctamente aunque el encabezado local no concuerde con el encabezado central del archivo zip. Los datos se descomprimen hasta que se alcanza el final del flujo comprimido, aunque su longitud supere el tamaño de archivo sin comprimir que se muestra en el directorio central/encabezado local.

A partir de .NET Core 3.0, el método <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> comprueba que el encabezado local y el encabezado central coinciden en el tamaño comprimido y no comprimido de una entrada.  Si no coinciden, el método produce una <xref:System.IO.InvalidDataException> si el encabezado local del archivo o el tamaño de la lista de descriptores de datos que no están en desacuerdo con el directorio central del archivo zip. Al leer una entrada, los datos descomprimidos se truncan hasta el tamaño de archivo sin comprimir que se muestra en el encabezado.

Este cambio se realizó para asegurarse de que un <xref:System.IO.Compression.ZipArchiveEntry>representa correctamente el tamaño de sus datos y que solo se lee esa cantidad de datos.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Vuelva a empaquetar cualquier archivo zip que presente estos problemas.

#### <a name="category"></a>Categoría

CoreFX

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`


-->

