---
ms.openlocfilehash: e6bb1d53cbe1883b8faef75bd22942bd4f65a5e6
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181764"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad Switch.System.Windows.Forms.EnableVisualStyleValidation

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

- None

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
