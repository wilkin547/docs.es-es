---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756120"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a>Se ha invertido el orden de las etiquetas en Activity.Tags

Ahora <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos de la lista según el orden en que se agregan, es decir, el primer elemento que se ha agregado es el primero de la lista. Este cambio se ha realizado para que coincida con la [especificación de atributos de OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos en el orden inverso al que se han agregado. Es decir, el primer elemento que se agrega es el último de la lista. A partir de .NET 5.0, se invierte el orden de los elementos y el primero que se agrega siempre es el primero de la lista.

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="recommended-action"></a>Acción recomendada

Si la aplicación tiene una dependencia en el orden de lista de <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> y va a actualizar a .NET 5.0 o una versión posterior, tendrá que cambiar esta parte del código.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
