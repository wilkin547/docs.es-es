---
title: 'Cambio importante: Se ha invertido el orden de las etiquetas en Activity.Tags'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde Activity.Tags ahora almacena los elementos de la lista según el orden en que se agregan.
ms.date: 11/01/2020
ms.openlocfilehash: f37f44cbe2ea467f0962cd8971d5bf38ce958dfd
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257133"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a>Se ha invertido el orden de las etiquetas en Activity.Tags

Ahora <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos de la lista según el orden en que se agregan, es decir, el primer elemento que se ha agregado es el primero de la lista. Este cambio se ha realizado para que coincida con la [especificación de atributos de OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos en el orden inverso al que se han agregado. Es decir, el primer elemento que se agrega es el último de la lista. A partir de .NET 5, se invierte el orden de los elementos y el primero que se agrega siempre es el primero de la lista.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Si la aplicación tiene una dependencia en el orden de lista de <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> y va a actualizar a .NET 5 o una versión posterior, tendrá que cambiar esta parte del código.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
