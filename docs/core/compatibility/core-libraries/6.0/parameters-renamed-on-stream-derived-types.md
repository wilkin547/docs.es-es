---
title: 'Cambio importante: Cambio de nombres de parámetro en tipos derivados de Stream'
description: Obtenga información sobre el cambio importante de .NET 6.0 en las bibliotecas .NET básicas, en las que se han cambiado algunos nombres de parámetro en métodos de tipos derivados de Stream.
ms.date: 03/04/2021
ms.openlocfilehash: c685fae6a7ed20ea47815d5f89a4e066c75e1178
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260015"
---
# <a name="some-parameters-in-stream-derived-types-are-renamed"></a>Se ha cambiado el nombre de algunos parámetros en tipos derivados de Stream.

En .NET 6, se ha cambiado el nombre de algunos parámetros de los métodos de los tipos derivados de <xref:System.IO.Stream?displayProperty=fullName> para que coincidan con la clase base.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, varios tipos derivados de <xref:System.IO.Stream> invalidan los métodos, pero utilizan nombres de parámetro diferentes a los que usa el tipo base. Por ejemplo, el parámetro de matriz de bytes de <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> se denomina `array`, mientras que el argumento correspondiente en el método de la clase base se denomina `buffer`.

En .NET 6, todos los tipos que derivan de <xref:System.IO.Stream?displayProperty=fullName> para los que los nombres de parámetro no coincidían se han ajustado conforme al tipo base mediante el uso de los mismos nombres de parámetro que el tipo base.

## <a name="version-introduced"></a>Versión introducida

6.0 (versión preliminar 1)

## <a name="reason-for-change"></a>Motivo del cambio

Hay varias razones para el cambio:

- Si se pasaba un argumento no válido y se producía una excepción, esa excepción podía contener el nombre del parámetro base o el nombre del parámetro derivado, dependiendo de la implementación. Dado que puede que el autor de llamada haya estado usando un tipo de referencia como base o como tipo derivado, no es posible que el nombre del argumento en la excepción sea siempre correcto.
- Tener distintos nombres de parámetro dificulta la validación coherente del comportamiento en todas las implementaciones de <xref:System.IO.Stream>.
- .NET 6 agrega un método público en <xref:System.IO.Stream> para validar los argumentos y los métodos deben tener un nombre de parámetro coherente para usar.

## <a name="recommended-action"></a>Acción recomendada

El efecto de este cambio importante es mínimo:

- Para los archivos binarios existentes, su impacto se limita al código que usa la reflexión para examinar los nombres de parámetro en los tipos derivados afectados.
- En el código fuente, su impacto se limita al código que usa parámetros con nombre para invocar métodos en el tipo de flujo derivado usando una variable de tipo como ese tipo derivado.

En ambos casos, la acción recomendada es usar el nombre de parámetro base de forma coherente.

## <a name="affected-apis"></a>API afectadas

- <xref:System.IO.BufferedStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.BufferedStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.DeflateStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.Compression.GZipStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.IO.FileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.FileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.IO.FileStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.IO.FileStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.Read(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.Write(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>
- <xref:System.Net.Sockets.NetworkStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.IO.Compression.DeflateStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.DeflateStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.DeflateStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.DeflateStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.DeflateStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.GZipStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.GZipStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.Compression.GZipStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.GZipStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.Compression.GZipStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.Compression.GZipStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.IO.BufferedStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.BufferedStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.FileStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.FileStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.IO.FileStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.IO.FileStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.BeginRead(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.Net.Sockets.NetworkStream.BeginWrite(System.Byte[],System.Int32,System.Int32,System.AsyncCallback,System.Object)`
- `M:System.Net.Sockets.NetworkStream.Read(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.ReadAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`
- `M:System.Net.Sockets.NetworkStream.Write(System.Byte[],System.Int32,System.Int32)`
- `M:System.Net.Sockets.NetworkStream.WriteAsync(System.Byte[],System.Int32,System.Int32,System.Threading.CancellationToken)`

-->
