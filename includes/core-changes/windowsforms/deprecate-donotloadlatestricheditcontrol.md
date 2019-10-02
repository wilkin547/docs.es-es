---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181808"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl

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

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
