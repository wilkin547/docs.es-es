---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643908"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue

El modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, que se introdujo en .NET Framework 4.7.2, no se admite en Windows Forms en .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Framework 4.7.2, el modificador de compatibilidad `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` permite al desarrollador ignorar el nuevo comportamiento de la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, que ahora devuelve una referencia al control de origen de datos. El comportamiento anterior de la propiedad era devolver `null`. Para obtener más información, consulte [Elemento \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 9)

#### <a name="recommended-action"></a>Acción recomendada

Quite el modificador. No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
