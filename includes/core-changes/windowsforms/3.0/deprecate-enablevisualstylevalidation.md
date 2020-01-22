---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937103"
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

- None

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
