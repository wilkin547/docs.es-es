---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721006"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a>Cambio de acceso para AccessibleObject.RuntimeIDFirstItem

A partir de .NET Core 3.0 RC1, la accesibilidad de `AccessibleObject.RuntimeIDFirstItem` ha cambiado de `protected` a `internal`.

#### <a name="change-description"></a>Descripción del cambio

A partir de la versión preliminar 4 de .NET Core 3.0, el campo `AccessibleObject.RuntimeIDFirstItem` era `protected`. A partir de la versión 3.0 RC1 de .NET Core , ha cambiado de `protected` a `internal` para alinearse con la accesibilidad del campo en .NET Framework.

#### <a name="version-introduced"></a>Versión introducida

3.0 RC1

#### <a name="recommended-action"></a>Acción recomendada

El cambio puede afectar al usuario si ha desarrollado una aplicación .NET Core con un tipo que se deriva de <xref:System.Windows.Forms.AccessibleObject> y tiene acceso al campo `RuntimeIDFirstItem`. Si es así, puede definir una constante local de la manera siguiente:

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- No detectable a través del análisis de la API.

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->
