---
ms.openlocfilehash: e0d0a680915f14c2d33f1864ad5ad05aff3dde5f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393894"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a>HTTP: las constantes HeaderNames se han cambiado a static readonly

A partir de ASP.NET Core 3.0 Preview 5, los campos de <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> se han cambiado de `const` a `static readonly`.

Para obtener información, vea [aspnet/AspNetCore#9514](https://github.com/aspnet/AspNetCore/issues/9514).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Estos campos solían ser `const`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Ahora estos campos son `static readonly`.

#### <a name="reason-for-change"></a>Motivo del cambio

El cambio:

* Impide que los valores se inserten en los límites de los ensamblados, lo que permite corregirlos según sea necesario.
* Permite comprobaciones de igualdad de referencia más rápidas.

#### <a name="recommended-action"></a>Acción recomendada

Vuelva a compilar para la versión 3.0. El código fuente que use estos campos de las maneras siguientes ya no podrá hacerlo:

* Como un argumento de atributo
* Como un objeto `case` en una instrucción `switch`
* Al definir otra instancia de `const`

Para solucionar el cambio importante, use constantes de nombre de encabezado autodefinidas o literales de cadena.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
