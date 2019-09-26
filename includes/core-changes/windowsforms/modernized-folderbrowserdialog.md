---
ms.openlocfilehash: a7cf6210e288d3521f1df248927f0e7cfaf45cab
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119123"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Modernización de FolderBrowserDialog

El control <xref:System.Windows.Forms.FolderBrowserDialog> ha cambiado en las aplicaciones de Windows Forms para .NET Core.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, Windows Forms utiliza el siguiente cuadro de diálogo para el control <xref:System.Windows.Forms.FolderBrowserDialog>:

![FolderBrowserDialogControl en .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

En .NET Core 3.0, los usuarios de Windows Forms utilizan un control basado en COM más reciente que se presentó en Windows Vista:

![FolderBrowserDialogControl en .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

El cuadro de diálogo se actualizará automáticamente.

Si quiere conservar el cuadro de diálogo original, establezca la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> en `false` antes de mostrar el cuadro de diálogo, tal y como se muestra en el siguiente fragmento de código:

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!-- 

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->