---
title: 'Cambio importante: Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760165"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a>Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.

Los nuevos tipos `Microsoft.JSInterop.JSObjectReference` y `Microsoft.JSInterop.JSInProcessObjectReference` introducidos en ASP.NET Core 5.0 RC1 se han marcado como `internal`.

## <a name="version-introduced"></a>Versión introducida

5.0 RC2

## <a name="old-behavior"></a>Comportamiento anterior

Se puede obtener una referencia `JSObjectReference` a partir de una llamada de interoperabilidad de JavaScript mediante `IJSRuntime`. Por ejemplo:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a>Comportamiento nuevo

`JSObjectReference` utiliza el modificador de acceso [internal](../../../../csharp/language-reference/keywords/internal.md). En su lugar, se debe usar la interfaz `public` de `IJSObjectReference`. Por ejemplo:

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

`JSInProcessObjectReference` también se marcó como `internal` y se ha reemplazado por `IJSInProcessObjectReference`.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio hace que la característica de interoperabilidad de JavaScript sea más coherente con otros patrones de Blazor. `IJSObjectReference` es análogo a `IJSRuntime` en que sirve para un propósito similar y tiene métodos y extensiones similares.

## <a name="recommended-action"></a>Acción recomendada

Reemplace las apariciones de `JSObjectReference` y `JSInProcessObjectReference` por `IJSObjectReference` y `IJSInProcessObjectReference`, respectivamente.

## <a name="affected-apis"></a>API afectadas

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
