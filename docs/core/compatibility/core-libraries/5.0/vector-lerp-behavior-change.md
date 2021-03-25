---
title: 'Cambio importante: Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde la implementación de Vector2.Lerp y Vector4.Lerp ha cambiado para tener en cuenta correctamente un error de redondeo de punto flotante.
ms.date: 11/01/2020
ms.openlocfilehash: a7014c30f2b102dc9a19e9a58f97b7c0ed8cd648
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257003"
---
# <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a>Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp

La implementación de <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> ha cambiado para tener en cuenta correctamente un error de redondeo de punto flotante.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> se implementaban como `value1 + (value2 - value1) * amount`. Pero debido a un error de redondeo de punto flotante, este algoritmo no siempre devuelve `value2` cuando `amount` es `1.0f`.

En .NET 5 y versiones posteriores, la implementación usa el mismo algoritmo que <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, que es `(value1 * (1.0f - amount)) + (value2 * amount)`. Este algoritmo tiene en cuenta correctamente el error de redondeo. Ahora, cuando `amount` es `1.0f`, el resultado es precisamente `value2`. El algoritmo actualizado también permite optimizar libremente el algoritmo mediante <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> cuando está disponible.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción. Pero si quiere mantener el comportamiento anterior, puede implementar una función `Lerp` propia que use el algoritmo anterior de `value1 + (value2 - value1) * amount`.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
