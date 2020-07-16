---
ms.openlocfilehash: f87d0dbeda6094bd745f5b580772b1161f30d0d5
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218414"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Cambio en el carácter separador de ruta de acceso de la propiedad FullName de los objetos ZipArchiveEntry

#### <a name="details"></a>Detalles

Para las aplicaciones destinadas a .NET Framework 4.6.1 y versiones posteriores, el carácter separador de ruta de acceso ha cambiado de una barra diagonal inversa ("\\) a una barra diagonal ("/") en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName> de los objetos <xref:System.IO.Compression.ZipArchiveEntry> creados por sobrecargas del método <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A>. El cambio trae la implementación de .NET en conformidad con la sección 4.4.17.1 de la [Especificación de formato de archivo .ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) y permite que los archivos ZIP se descompriman en sistemas distintos de Windows.<br />Al descomprimir un archivo ZIP creado por una aplicación que tiene como destino una versión anterior de .NET Framework en sistemas operativos que no son de Windows, como Macintosh, no se puede conservar la estructura de directorios. Por ejemplo, en Macintosh, crea un conjunto de archivos cuyo nombre de archivo concatena la ruta de acceso del directorio, junto con cualquier carácter de barra diagonal inversa ("\\") y el nombre de archivo. Como resultado, no se conserva la estructura de directorios de archivos descomprimidos.

#### <a name="suggestion"></a>Sugerencia

El impacto de este cambio en los archivos .ZIP que se descomprimen en el sistema operativo Windows por las API en el espacio de nombres de .NET Framework <xref:System.IO?displayProperty=nameWithType> debe ser mínimo, ya que estas API pueden controlar sin problemas una barra diagonal ("/") o una barra diagonal inversa ("\\") como carácter separador de la ruta de acceso.<br />Si no quiere este cambio, puede rechazarlo mediante la adición de un valor de configuración a la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. En el ejemplo siguiente se muestra la sección `<runtime>` y el conmutador de rechazo `Switch.System.IO.Compression.ZipFile.UseBackslash`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en .NET Framework 4.6.1 y versiones posteriores pueden participar en este comportamiento si se agrega una opción de configuración a la sección [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. A continuación se muestra la sección `<runtime>` y el conmutador de inclusión `Switch.System.IO.Compression.ZipFile.UseBackslash`.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
