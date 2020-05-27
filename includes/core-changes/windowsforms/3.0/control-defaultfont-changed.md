---
ms.openlocfilehash: 0b2d3c1383246d4259c6d906ecf9dab927f4bdb1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721343"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a>Fuente de control predeterminada cambiada a Segoe UI 9 pt

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, la propiedad <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> estaba establecida en `Microsoft Sans Serif 8 pt`. En la imagen siguiente se muestra una ventana con la fuente predeterminada.

![Fuente de control predeterminada de .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

A partir de .NET Core 3.0, la fuente predeterminada está establecida en `Segoe UI 9 pt` (la misma fuente que <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). Como resultado de este cambio, los formularios y los controles tienen un tamaño aproximadamente un 27 % mayor en razón del mayor tamaño de la nueva fuente predeterminada. Por ejemplo:

![Fuente de control predeterminada de .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Este cambio se ha realizado a fin de adaptarse a las [directrices para la experiencia de usuario de Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Debido al cambio en el tamaño de los formularios y controles, asegúrese de que la aplicación se representa correctamente.

Para conservar la fuente original, establezca la fuente predeterminada del formulario en `Microsoft Sans Serif 8 pt`. Por ejemplo:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>Categoría

- Windows Forms

#### <a name="affected-apis"></a>API afectadas

Ninguno.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
