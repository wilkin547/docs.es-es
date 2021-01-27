---
ms.openlocfilehash: 27c6353f8f71254a505b434921f4b1e61e64cdda
ms.sourcegitcommit: 2b878d7011306b215dbf3d5dc9c1e78355a6dcd5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "98758169"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="e7e96-101">Modernización de FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="e7e96-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="e7e96-102">El control <xref:System.Windows.Forms.FolderBrowserDialog> ha cambiado en las aplicaciones de Windows Forms para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e7e96-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e7e96-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e7e96-103">Change description</span></span>

<span data-ttu-id="e7e96-104">En .NET Framework, Windows Forms utiliza el siguiente cuadro de diálogo para el control <xref:System.Windows.Forms.FolderBrowserDialog>:</span><span class="sxs-lookup"><span data-stu-id="e7e96-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl en .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="e7e96-106">En .NET Core 3.0, Windows Forms usa un control basado en COM más reciente que se presentó en Windows Vista:</span><span class="sxs-lookup"><span data-stu-id="e7e96-106">In .NET Core 3.0, Windows Forms uses a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl en .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="e7e96-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e7e96-108">Version introduced</span></span>

<span data-ttu-id="e7e96-109">3.0</span><span class="sxs-lookup"><span data-stu-id="e7e96-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e7e96-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e7e96-110">Recommended action</span></span>

<span data-ttu-id="e7e96-111">El cuadro de diálogo se actualizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e7e96-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="e7e96-112">Si quiere conservar el cuadro de diálogo original, establezca la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> en `false` antes de mostrar el cuadro de diálogo, tal y como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="e7e96-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="e7e96-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="e7e96-113">Category</span></span>

<span data-ttu-id="e7e96-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7e96-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e7e96-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e7e96-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

#### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
