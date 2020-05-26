---
ms.openlocfilehash: c980b0c0be9f4d6a529baa0743dec9ac16ca0d7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721494"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad UseLegacyImages

El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, que se introdujo en .NET Framework 4.8, no se admite en Windows Forms en .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Framework 4.8, el modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages` soluciona posibles problemas de escalado de imágenes en escenarios de ClickOnce en entornos con valores altos de PPP. Cuando se establece en `true`, el modificador permite al usuario restaurar el escalado de imágenes heredadas en pantallas con valores altos de PPP cuya escala está establecida en un valor mayor que 100 %. Para obtener más información, consulte [Notas de la versión de .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) en GitHub.

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.UseLegacyImages`.

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
