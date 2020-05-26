---
ms.openlocfilehash: e1c55eab0b968daab7322350e201b49149e63215
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721492"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad AllowUpdateChildControlIndexForTabControls

El modificador de compatibilidad `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` se admite en Windows Forms en .NET Framework 4.6 y en versiones posteriores, pero no se admite en Windows Forms a partir de .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework 4.6 y en versiones posteriores, al seleccionar una pestaña, se reordena su colección de controles. El modificador de compatibilidad `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` permite a una aplicación omitir esta reordenación cuando no se desea este comportamiento.

En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls`.

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
