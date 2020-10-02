---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077597"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.

Los nuevos tipos `Microsoft.JSInterop.JSObjectReference` y `Microsoft.JSInterop.JSInProcessObjectReference` introducidos en ASP.NET Core 5.0 RC1 se han marcado como `internal`.

#### <a name="version-introduced"></a>Versión introducida

5.0 RC2

#### <a name="old-behavior"></a>Comportamiento anterior

Se puede obtener una referencia `JSObjectReference` a partir de una llamada de interoperabilidad de JavaScript mediante `IJSRuntime`. Por ejemplo:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a>Comportamiento nuevo

`JSObjectReference` utiliza el modificador de acceso [internal](../../../../docs/csharp/language-reference/keywords/internal.md). En su lugar, se debe usar la interfaz `public` de `IJSObjectReference`. Por ejemplo:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` también se marcó como `internal` y se ha reemplazado por `IJSInProcessObjectReference`.

#### <a name="reason-for-change"></a>Motivo del cambio

El cambio hace que la característica de interoperabilidad de JavaScript sea más coherente con otros patrones de Blazor. `IJSObjectReference` es análogo a `IJSRuntime` en que sirve para un propósito similar y tiene métodos y extensiones similares.

#### <a name="recommended-action"></a>Acción recomendada

Reemplace las apariciones de `JSObjectReference` y `JSInProcessObjectReference` por `IJSObjectReference` y `IJSInProcessObjectReference`, respectivamente.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
