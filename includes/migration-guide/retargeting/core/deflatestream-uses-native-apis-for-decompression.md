---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614725"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream usa las API nativas para la descompresión

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.2, la implementación de la descompresión en la clase `T:System.IO.Compression.DeflateStream` ha cambiado para usar las API nativas de Windows de forma predeterminada. Normalmente, esto da como resultado una mejora considerable del rendimiento. En todas las aplicaciones de .NET que tienen como destino la versión 4.7.2 de .NET Framework o una versión posterior se usa la implementación nativa. Es posible que este cambio provoque algunas diferencias de comportamiento, como las siguientes:

- Los mensajes de excepción pueden ser diferentes. Pero el tipo de excepción que se inicia sigue siendo el mismo.
- Algunas situaciones especiales, por ejemplo no tener memoria suficiente para completar una operación, se pueden administrar de otra manera.
- Hay diferencias conocidas para el análisis del encabezado de gzip (Nota: Solo se ve afectado `GZipStream` establecido para la descompresión):
- Se pueden iniciar excepciones al analizar encabezados no válidos en momentos diferentes.
- La implementación nativa exige que los valores para algunas marcas reservadas dentro del encabezado de gzip (es decir, [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) se establezcan según la especificación, lo que puede provocar que se inicie una excepción donde anteriormente se ignoraban los valores no válidos.

#### <a name="suggestion"></a>Sugerencia

Si la descompresión con las API nativas ha afectado negativamente el comportamiento de la aplicación, puede descartar esta característica si agrega el modificador `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` a la sección `runtime` del archivo app.config y lo establece en `true`:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
