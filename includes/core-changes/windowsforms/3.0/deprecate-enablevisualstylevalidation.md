---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556221"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad EnableVisualStyleValidation

El modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` no se admite en Windows Forms en .NET Core ni .NET 5.0 y posterior.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.

En .NET Core y .NET 5.0 y posterior no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.

#### <a name="version-introduced"></a>Versión introducida

3.0

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
