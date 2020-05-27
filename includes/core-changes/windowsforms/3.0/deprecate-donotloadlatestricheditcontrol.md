---
ms.openlocfilehash: cb8c0532bb2bcfbcd619cd382f3d236b431c3480
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721612"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl

El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, que se introdujo en .NET Framework 4.7.1, no se admite en Windows Forms en .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework 4.6.2 y en versiones anteriores, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia del control RichEdit v3.0 de Win32 y, para las aplicaciones que tienen como destino .NET Framework 4.7.1, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia de RichEdit v4.1 (en *msftedit.dll*). Se introdujo el modificador de compatibilidad `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` para permitir que las aplicaciones que tienen como destino .NET Framework 4.7.1 y versiones posteriores ignoren el nuevo control RichEdit v4.1 y usen en su lugar el antiguo control RichEdit v3.

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`. Solo se admiten las nuevas versiones del control <xref:System.Windows.Forms.RichTextBox>.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 9)

#### <a name="recommended-action"></a>Acción recomendada

Quite el modificador. No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
