---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181868"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>No se admite el modificador de compatibilidad Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls

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

- None

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
