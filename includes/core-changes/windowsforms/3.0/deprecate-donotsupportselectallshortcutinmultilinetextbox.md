---
ms.openlocfilehash: bba74f26eafd52b966928835d5003d03af1eabdc
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720963"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad DoNotSupportSelectAllShortcutInMultilineTextBox

El modificador de compatibilidad `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`, que se introdujo en .NET Framework 4.6.1, no se admite en Windows Forms en .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Framework 4.6.1, al seleccionar la tecla de método abreviado <kbd>Ctrl</kbd> + <kbd>A</kbd> en un control <xref:System.Windows.Forms.TextBox>, se selecciona todo el texto. En .NET Framework 4.6 y en versiones anteriores, al seleccionar la tecla de método abreviado <kbd>Ctrl</kbd> + <kbd>A</kbd>, no se podía seleccionar todo el texto si las propiedades [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) y <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> estaban establecidas en `true`. El modificador de compatibilidad `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` se introdujo en .NET Framework 4.6.1 para conservar el comportamiento original. Para obtener más información, vea <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`.

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
