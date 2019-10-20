---
ms.openlocfilehash: 3d0a90a57c2b1c2759b8420e74c284668d54e9cb
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526775"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>API duplicadas quitadas de Windows Forms

En .NET Core 3.0 RC1 se han quitado una serie de API que se habían duplicado accidentalmente en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> a partir de la versión preliminar 4 de .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

La versión preliminar 4 de .NET Core 3.0 duplicó accidentalmente varios tipos en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> que ya existían en el espacio de nombres <xref:System.ComponentModel.Design?displayProperty=fullName>. A partir de .NET Core 3.0 RC1, estos tipos duplicados ya no están disponibles. En la tabla siguiente se muestran las listas del tipo original y su tipo duplicado:

|Tipo original|Tipo duplicado|
|---|---|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
|<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
|<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>Versión introducida

3.0 RC1

#### <a name="recommended-action"></a>Acción recomendada

Actualice el código para hacer referencia al tipo original, como se muestra en la columna **Tipo original** de la tabla.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- No detectable a través del análisis de la API.

<!--

### Affected APIs

- Not detectable via API analysis.

-->
