---
ms.openlocfilehash: e10b5168d59edd56ff549a3a1e3a09d023fe5e28
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556229"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad DoNotLoadLatestRichEditControl

El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyImages`, incorporado en .NET Framework 4.7.1, no se admite en Windows Forms en .NET Core ni .NET 5.0 y posterior.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework 4.6.2 y versiones anteriores, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia de RichEdit v3.0 de Win32 y, en las aplicaciones que tienen como destino .NET Framework 4.7.1, el control <xref:System.Windows.Forms.RichTextBox> crea una instancia de RichEdit v4.1 (en *msftedit.dll*). El modificador de compatibilidad `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` se incorporó para permitir que las aplicaciones que tienen como destino .NET Framework 4.7.1 y versiones posteriores omitan el nuevo control RichEdit v4.1 y, en su lugar, usen el antiguo control RichEdit v3.

En .NET Core y .NET 5.0 y versiones posteriores no se admite el modificador `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl`. Solo se admiten las nuevas versiones del control <xref:System.Windows.Forms.RichTextBox>.

#### <a name="version-introduced"></a>Versión introducida

3.0

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
