---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302727"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a>Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos

<xref:System.Numerics.Vector%601?displayProperty=nameWithType> ahora inicia siempre una excepción <xref:System.NotSupportedException> para los parámetros de tipo no admitidos.

#### <a name="change-description"></a>Descripción del cambio

Antes, los miembros de <xref:System.Numerics.Vector%601> no siempre iniciaban una excepción <xref:System.NotSupportedException> cuando `T` era un [tipo no admitido](#unsupported-types). La excepción no se iniciaba siempre debido a las rutas de acceso de código que permitían la aceleración de hardware. Por ejemplo, `Vector<bool> + Vector<bool>` devolvía `default` en lugar de iniciar una excepción en plataformas que no tienen aceleración de hardware, como ARM32. En el caso de los tipos no admitidos, los miembros <xref:System.Numerics.Vector%601> exhibían un comportamiento incoherente en distintas plataformas y configuraciones de hardware.

A partir de .NET 5.0, los miembros <xref:System.Numerics.Vector%601> siempre inician una excepción <xref:System.NotSupportedException> en todas las configuraciones de hardware cuando `T` no es un tipo admitido.

##### <a name="unsupported-types"></a>Tipos no admitidos

Los tipos admitidos del parámetro de tipo de <xref:System.Numerics.Vector%601> son:

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

Los tipos admitidos no han cambiado, pero pueden cambiar en el futuro.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

No utilice un tipo no admitido como parámetro de tipo de <xref:System.Numerics.Vector%601>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Numerics.Vector%601?displayProperty=fullName> y todos sus miembros

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
