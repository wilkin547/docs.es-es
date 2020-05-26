---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721690"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad EnableVisualStyleValidation

No se admite el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` en Windows Forms en .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 9)

#### <a name="recommended-action"></a>Acción recomendada

Quite el modificador. No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- Ninguna

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
