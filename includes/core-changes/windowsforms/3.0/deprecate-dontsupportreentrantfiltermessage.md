---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643896"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad Switch.System.Windows.Forms.DontSupportReentrantFilterMessage

El modificador de compatibilidad `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, que se introdujo en .NET Framework 4.6.1, no se admite en Windows Forms en .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Framework 4.6.1, el modificador de compatibilidad `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` soluciona las posibles excepciones <xref:System.IndexOutOfRangeException> cuando se llama al mensaje <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> con una implementación personalizada de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>. Para más información, vea [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`.

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 9)

#### <a name="recommended-action"></a>Acción recomendada

Quite el modificador. No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
