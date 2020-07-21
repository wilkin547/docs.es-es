---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281318"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a>Cambio de comportamiento de Vector2.Lerp y Vector4.Lerp

La implementación de <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> ha cambiado para tener en cuenta correctamente un error de redondeo de punto flotante.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> y <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> se implementaban como `value1 + (value2 - value1) * amount`. Pero debido a un error de redondeo de punto flotante, este algoritmo no siempre devuelve `value2` cuando `amount` es `1.0f`.

En .NET 5.0 y versiones posteriores, la implementación usa el mismo algoritmo que <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, que es `(value1 * (1.0f - amount)) + (value2 * amount)`. Este algoritmo tiene en cuenta correctamente el error de redondeo. Ahora, cuando `amount` es `1.0f`, el resultado es precisamente `value2`. El algoritmo actualizado también permite optimizar libremente el algoritmo mediante <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> cuando está disponible.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 7)

#### <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción. Pero si quiere mantener el comportamiento anterior, puede implementar una función `Lerp` propia que use el algoritmo anterior de `value1 + (value2 - value1) * amount`.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
